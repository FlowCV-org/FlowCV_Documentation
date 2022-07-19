# Code Overview

I'm not going to cover every directory and file in this overview but I will go over a few of the key areas.

The directory structure is organized as follows:

```
project
│   README.md  
│
└───CMake
│   │   [various cmake config files]
│   │   ...
│   
└───Editor_UI
│   │
│   └───Common
│   │   │   entry.cpp               - Location of Editor Application main
│   │   │   ...
│   │
│   └───Node_Editor
│       │   node_editor.cpp         - Editor UI code
│       │   ...
│   
└───Examples
│   │   Headless_Process_Engine     - Application for running flows in headless processing mode
│   │   OpenCV_Dataflow_Test        - Simple example showing how to use the dataflow framework to build processing applications
│   
└───FlowCV_SDK
│   │   [SDK Files and Folders]     - The core FlowCV SDK for building applications or plugins
│   │   ...
│   
└───Internal_Nodes
│   │   [Various Internal Nodes]    - The core OpenCV functionality nodes
│   │   ...
│   
└───Managers
│   │   FlowCV_Manager.cpp          - A simple management class to keep track of node instances, connections and processing
│   │   Internal_Node_Manager.cpp   - A class for registering and handling internal node instances
│   │   Plugin_Manager.cpp          - A class for registering and handling external node plugins
│   │   ...
│   
└───Plugins
│   │   [Various Plugin Nodes]      - External node plugins to extend FlowCV functionality
│   │   ...
│   
└───Templates
│   │   Internal_Node               - A template for creating new internal nodes
│   │   Plugin                      - A template for creating new plugin nodes
│   
└───third-party
│   │   [various third-party dependecies]
│   │   ...
│   
└───Tools
    │   PluginMaker.py              - Python script to help automate the creation of new nodes
```

