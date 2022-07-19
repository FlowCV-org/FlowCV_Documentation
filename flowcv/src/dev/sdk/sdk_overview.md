# SDK Overview

The FlowCV SDK is located in the FlowCV_SDK folder within the repo and can be referenced from outside projects when creating your own custom plugins for FlowCV.

The directory structure is as follows:

```
FlowCV_SDK
│   FlowCVConfig.cmake              - Main FlowCV CMake config file  
│
└───CMake
│   │   [various cmake config files]
│   │   ...
│   
└───include                         - FlowCV include files
│   │   ...
│   
└───src                             - FlowCV source files
│   │   ...
│   
└───third-party                     - Various third-party libraries
│   │
│   └───dspatch                     - DSPatch Dataflow Framework
│   │
│   └───FileBrowser                 - Simple ImGui File Browser library
│   │
│   └───imgui                       - ImGui - Immediate Mode Graphical User Interface library
│   │
│   └───imgui_wrapper               - Wrapper class for common ImGui functions
│   │
│   └───implot                      - Simple ImGui Graphical Plot library
│   │
│   └───json                        - Great JSON library
│   │
│   └───node-editor                 - ImGui based node editor library
│   │
│   └───tclap                       - Command line argument parser library
```

I tried to keep the amount of dependencies as small as possible to keep the overall project small and to make it quicker and easier to build.

The included third-party libraries are either relatively small or have been modified from their original code/repo so it was decided to just add them directly to this repo instead of as sub-modules and for the convenience of keeping everything self-contained.

OpenCV on the other hand is fairly large so on Windows the CMake build script will automatically download the pre-built binaries and development source needed for building this project from source.

On other operating system you will need to pre-install the necessary dependencies first before building, see the [building from source](../../building_source/build_from_source.md) section for more details.

Check out the [Plugins](plugin.md) section for more details on using the SDK to build your own plugin.


