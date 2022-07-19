# Creating A Plugin

To use the FlowCV SDK in your external project for making your own plugin simply add the following line to your CMake initialization options:

```cmake
-DFlowCV_DIR=\path\to\your\flowcv\sdk\location
```

Add this to your CMakeLists.txt file:
```cmake
find_package( FlowCV REQUIRED )
```

Add these to your add_library section:
```cmake
    ${FlowCV_SRC}
    ${IMGUI_SRC}
    ${DSPatch_SRC}
```

Add this to the target_link_libraries section:
```cmake
    ${OpenCV_LIBS}
```

You can either use the [plugin template](https://github.com/circuitsforfun/OpenCV_Dataflow_Framework/tree/main/Templates/Plugin) file as a starting point or use the [PluginMaker.py](../template_tool.md) python script to generate a more ready to go starting point.

A few key things to understand when creating your own plugin:

In the plugin initialization function you need to set some info for your plugin:
```c++
SetComponentName_("Plugin_Name");
SetComponentCategory_(Category::Category_Other);
SetComponentAuthor_("Author");
SetComponentVersion_("0.0.0");
```

Initialize the global instance counter for your plugin and increment it:
```c++
SetInstanceCount(global_inst_counter);
global_inst_counter++;
```

Then set the number, name and type of inputs and outputs:
```c++
// 1 inputs
SetInputCount_( 1, {"in"}, {IoType::Io_Type_CvMat} );

// 1 outputs
SetOutputCount_( 1, {"out"}, {IoType::Io_Type_CvMat} );
```

All of the image/data processing that happens on the Flow processing thread will happen in the Process_ method, this is where you will create all of your OpenCV or other processing functionality and output any of the results:
```c++
void PluginName::Process_( SignalBus const& inputs, SignalBus& outputs )
```

You can grab the pointer to the input like this:
```c++
auto in1 = inputs.GetValue<cv::Mat>(0);
```

Check that the pointer is valid before using it.

It is also recommended in the case of cv::Mat to also check to make sure the Mat object is not empty before attempting to process any image data.

Then if you are planning to do any operations that will modify the input image you should first copy it to a local buffer or use an OpenCV operation where the resulting output will be put into the local buffer. Do not attempt to modify the input image pointer buffer directly as other nodes may also be using it in parallel and you will get undesirable effects if you modify it while it's in use.

Next is GUI Section, this is where you first tell FlowCV if your plugin has any kind of interface associated with it:
```c++
bool PluginName::HasGui(int interface)
```

The current types are:
```c++
GuiInterfaceType_Controls,
GuiInterfaceType_Main,
GuiInterfaceType_Other
```

* Controls is for any of the standard properties that will show up in the properties panel for your node when selected.
* Main is for any standalone/separate window interface you want to create for your node for example like the Viewer node
* Other is anything doesn't fit the first two options.

Next is the Update GUI method for actually drawing your interface:
```c++
void PluginName::UpdateGui(void *context, int interface)
```

FlowCV will pass in the current ImGui context and what type of interface it is requesting to be drawn

First you need to set the context:
```c++
auto *imCurContext = (ImGuiContext *)context;
ImGui::SetCurrentContext(imCurContext);
```

Then you can test for which interface it is and draw your conrols/UI:
```c++
    if (interface == (int)FlowCV::GuiInterfaceType_Controls) {

    }
```
Inside the if statement you can use all of the standard ImGui functionality to implement your interface.

When creating controls it is recommended to use the CreateControlString helper function for naming controls to avoid naming conflicts.

ImGui keeps track of all UI controls by their control name so if you have different nodes with the same control name or even the same name within the same node it will have issues updating and working if there is a name conflict.

So for example to create an ImGui:Checkbox control do something like this:
```c++
ImGui::Checkbox(CreateControlString("Enable Setting", GetInstanceName()).c_str(), &setting_boolean);
```

That will create the control with the string you specify and then also get the instance name (node name + instance count) and append that to your control using a hidden string option so your control has a unique name. Keep in mind it could still be possible to have the same name within your node so be careful about how you name the actual control portion.

Next you have the section for Getting and Setting the state, this is used by the node editor when loading and saving flow graphs as well as for copying and pasting nodes.

```c++
std::string AprilTagPlugin::GetState()
```

and

```c++
void AprilTagPlugin::SetState(std::string &&json_serialized)
```

in these methods you will use standard JSON creation and parse to get and set the required state key value pairs.

for example if I wanted to save a parameter in the GetState method I would do something like this:
```c++
using namespace nlohmann;

json state;

state["border_size"] = border_size_;

std::string stateSerialized = state.dump(4);

return stateSerialized;
```

and to load/set that parameter in the SetState method:
```c++
using namespace nlohmann;

json state = json::parse(json_serialized);

if (state.contains("border_size"))
    border_size_ = state["border_size"].get<int>();
```

Check out some of the included [Plugins](https://github.com/circuitsforfun/OpenCV_Dataflow_Framework/tree/main/Plugins) to see more examples of how everything works
