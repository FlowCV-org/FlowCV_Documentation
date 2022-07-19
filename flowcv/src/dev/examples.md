# Example Projects

Aside from the Node Editor and the various internal and external nodes the repo also comes with a few example projects to further illustrate how the FlowCV framework can be used to process computer vision workflows or create your own application using the included UI libraries and wrappers.

1. [Headless Processing Engine](#1-headless-processing-engine)
2. [OpenCV DataFlow Test](#2-opencv-dataflow-test)


### 1. Headless Processing Engine

---

This example is used as a way to run flows without the UI in cases where you want to deploy your computer vision processing solution to a target platform for production or testing that may not have a display interface configured.

Check out the [Processing Engine](../proc/engine.md) Section for specific details on how to use it.

#### Code Overview

---

Create a command line parser using [TCLAP](http://tclap.sourceforge.net/) library:
```c++
CmdLine cmd("Data Flow Processing Engine", ' ', APP_VERSION);
ValueArg<std::string> flow_file_arg("f", "flow", "Flow File", true, "", "string");
cmd.add(flow_file_arg);
cmd.parse(argc, argv);
```

Instantiate the Flow Manager class:
```c++
FlowCV::FlowCV_Manager flowMan;
```

Recursively load plugins from the plugin folder if it exists:
```c++
if (std::filesystem::exists(pluginDir))
    flowMan.plugin_manager_->LoadPlugins(pluginDir.c_str());
```

Load a flow graph file, exit if there is an error:
```c++
if (!flowMan.LoadState(flow_file_arg.getValue().c_str())) {
    cout << "Error Loading Flow File" << endl;
    return EXIT_FAILURE;
}
```

Initiate signal handling to exit gracefully in event of a ctrl+c or ctrl+x
```c++
Init_Signal();
```

Start the flow processing thread:
```c++
flowMan.StartAutoTick();
```

Wait in loop while flow processing is happening
```c++
while(!g_bTerminate) {
    this_thread::sleep_for(chrono::seconds(1));
}
```

If terminated and loop exits, then stop background processing thread and exit the application
```c++
flowMan.StopAutoTick();

return EXIT_SUCCESS;
```

---

### 2. OpenCV Dataflow Test

---

This example shows the follow things:
* how to initialize the manager
* find/load plugins
* iterate all loaded plugins
  * print out node info
* iterate all internal nodes
  * print out node info
* create some nodes and wire them together
* iterate over the active flow graph (get all node instances and connections)
* create a dockspace UI with some parameter controls and viewers

#### Code Overview

---

Use FlowCV namespace and instantiate FlowCV Manager:
```c++
using namespace FlowCV;
FlowCV_Manager flowMan;
```

Recursively load plugins from the plugin folder if it exists:
```c++
if (std::filesystem::exists(pluginDir))
    flowMan.plugin_manager_->LoadPlugins(pluginDir.c_str());
```

Iterate over all of the plugins and print out information about the plugin node:
```c++
uint32_t pCount = flowMan.plugin_manager_->PluginCount();
std::cout << "External Plugin Count: " << pCount << std::endl;
std::cout << "Plugin List: " << std::endl;
auto categories = getCategories();
for (int i = 0; i < pCount; i++) {
    NodeDescription plgNodeDesc;
    if (flowMan.plugin_manager_->GetPluginDescription(i, plgNodeDesc)) {
        std::cout << "--------------------------------" << std::endl;
        std::cout << "    Name: " << plgNodeDesc.name << std::endl;
        std::cout << "    Category: " << categories[plgNodeDesc.category] << std::endl;
        std::cout << "    Author: " << plgNodeDesc.author << std::endl;
        std::cout << "    Version: " << plgNodeDesc.version << std::endl;
        std::cout << "    Inputs: " << plgNodeDesc.input_count << std::endl;
        std::cout << "    Outputs: " << plgNodeDesc.output_count << std::endl;
        std::cout << "--------------------------------" << std::endl;
    }
}
std::cout << std::endl;
```

Iterate over all of the internal nodes and print out information about the node:
```c++
uint32_t iCount = flowMan.int_node_manager_->IntNodeCount();
std::cout << "Internal Node Count: " << iCount << std::endl;
std::cout << "Node List: " << std::endl;
for (int i = 0; i < iCount; i++) {
    NodeDescription intNodeDesc;
    if (flowMan.int_node_manager_->GetIntNodeDescription(i, intNodeDesc)) {
        std::cout << "--------------------------------" << std::endl;
        std::cout << "    Name: " << intNodeDesc.name << std::endl;
        std::cout << "    Category: " << categories[intNodeDesc.category] << std::endl;
        std::cout << "    Author: " << intNodeDesc.author << std::endl;
        std::cout << "    Version: " << intNodeDesc.version << std::endl;
        std::cout << "    Inputs: " << intNodeDesc.input_count << std::endl;
        std::cout << "    Outputs: " << intNodeDesc.output_count << std::endl;
        std::cout << "--------------------------------" << std::endl;
    }
}
std::cout << std::endl;
```

Create a few nodes:
```c++
uint64_t capId = flowMan.CreateNewNodeInstance("Video_Capture");
uint64_t blurId = flowMan.CreateNewNodeInstance("Blur");
uint64_t viewId = flowMan.CreateNewNodeInstance("Viewer");
uint64_t viewId2 = flowMan.CreateNewNodeInstance("Viewer");
uint64_t writeId = flowMan.CreateNewNodeInstance("Video_Writer");
```

Set initial state of the Blur node by creating a JSON object and setting some parameter key value pairs:
```c++
nlohmann::json blurState;
blurState["lock_h_v"] = true;
blurState["blur_mode"] = 1;
blurState["blur_amt_h"] = 5.0f;
NodeInfo ni;
if (flowMan.GetNodeInfoById(blurId, ni))
    ni.node_ptr->SetState(blurState.dump());
```

Set initial state of the video capture node using a JSON object:
```c++
nlohmann::json camState;
camState["src_index"] = 1;
camState["src_mode"] = 2;
if (flowMan.GetNodeInfoById(capId, ni)) {
    ni.node_ptr->SetState(camState.dump());
}
```

Wire up the connections between the various nodes:
```c++
flowMan.ConnectNodes(capId, 0, blurId, 0);
flowMan.ConnectNodes(blurId, 0, viewId, 0);
flowMan.ConnectNodes(capId, 0, viewId2, 0);
flowMan.ConnectNodes(blurId, 0, writeId, 0);
```

Print information about the current active nodes and their connections to each other:
```c++
PrintNodeConnectionInfo(flowMan);
```

Initialize the ImGui Wrapper class and create a Test Gui interface:
```c++
ImGuiWrapper imgui;
imgui.Init(1280, 720, "Test GUI");
ImGuiIO &io = ImGui::GetIO();
```

Start the flow processing thread:
```c++
flowMan.StartAutoTick();
```

Main loop for UI Handling:
```c++
while(!imgui.ShouldClose()) {
    ...
}
```

Poll events and start new frame:
```c++
  ImGuiWrapper::PollEvents();
  ImGuiWrapper::NewFrame();
```

Start ImGui dockspace:
```c++
  ImGuiWrapper::StartDockSpace(true);
  ImGuiID dockspace_id = ImGui::GetID("InvisibleWindowDockSpace");
```

Create an example main menu bar with some basic load/save functionality:
```c++
  if (ImGui::BeginMainMenuBar())
  {
      if (ImGui::BeginMenu("File"))
      {
          if (ImGui::MenuItem("Load", "CTRL+L")) {
              flowMan.StopAutoTick();
              flowMan.LoadState("./simple_test.flow");
              flowMan.StartAutoTick();
          }
          if (ImGui::MenuItem("Save", "CTRL+S")) {flowMan.SaveState("./simple_test.flow");}
          ImGui::Separator();
          if (ImGui::MenuItem("Exit", "CTRL+Q")) { break; }
          ImGui::EndMenu();
      }
      if (ImGui::BeginMenu("Edit"))
      {
          if (ImGui::MenuItem("Undo", "CTRL+Z")) {}
          if (ImGui::MenuItem("Redo", "CTRL+Y", false, false)) {}  // Disabled item
          ImGui::Separator();
          if (ImGui::MenuItem("Cut", "CTRL+X")) {}
          if (ImGui::MenuItem("Copy", "CTRL+C")) {}
          if (ImGui::MenuItem("Paste", "CTRL+V")) {}
          ImGui::EndMenu();
      }
      ImGui::EndMainMenuBar();
  }
```

Process properties UI for each node to display their properties in the property panel:
```c++
  ImGui::SetNextWindowDockID(dock_id_prop, ImGuiCond_FirstUseEver);
  ImGui::Begin("Properties");
  for (int i = 0; i < flowMan.GetNodeCount(); i++) {
      if (flowMan.NodeHasUI(i, GuiInterfaceType_Controls)) {
          NodeInfo nInfo;
          if (flowMan.GetNodeInfoByIndex(i, nInfo)) {
              std::string param_name = nInfo.desc.name;
              param_name += "_";
              param_name += std::to_string(nInfo.node_ptr->GetInstanceCount());
              if (ImGui::CollapsingHeader(param_name.c_str(), ImGuiTreeNodeFlags_DefaultOpen)) {
                  flowMan.ProcessNodeUI(i, imgui.GetImGuiCurrentContext(), GuiInterfaceType_Controls);
              }
              ImGui::Separator();
          }
      }
  }
  ImGui::End();
```

Process Main UI for each node that has a Main User Interface:
```c++
  for (int i = 0; i < flowMan.GetNodeCount(); i++) {
      if (flowMan.NodeHasUI(i, GuiInterfaceType_Main)) {
          NodeInfo nInfo;
          if (flowMan.GetNodeInfoByIndex(i, nInfo)) {
              if (nInfo.desc.name == "Viewer")
                  ImGui::SetNextWindowDockID(dock_main_id, ImGuiCond_FirstUseEver);
              flowMan.ProcessNodeUI(i, imgui.GetImGuiCurrentContext(), GuiInterfaceType_Main);
          }
      }
  }
```

End frame and update UI Draw events:
```c++
  ImGuiWrapper::FrameEnd();
  imgui.Update();
```

If closing, stop background processing thread before exiting:
```c++
flowMan.StopAutoTick();
```

