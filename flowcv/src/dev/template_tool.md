# Template Tool

The template tool helps automate the process of creating new internal or external (plugin) nodes.

You run it using python with the follow options:
```commandline
Usage: PluginMaker.py [options]

Options:
  -h, --help            show this help message and exit
  -n NAME, --name=NAME  Specify New Plugin Name
  -a AUTHOR, --author=AUTHOR
                        Specify The Plugin Author
  -v VERSION, --ver=VERSION
                        Specify Plugin Version: 0.1.0
  -d ADD, --add=ADD     Add to Main CMake Project File
  -c CATEGORY, --category=CATEGORY
                        Specify Plugin Category: Source, Filter, etc.
  -i INPUTS, --inputs=INPUTS
                        Specify Number of Inputs with CSV Names: in,in,in
  -o OUTPUTS, --outputs=OUTPUTS
                        Specify Number of Outputs with CSV Names:
                        out,color,depth
  -p ITYPE, --intype=ITYPE
                        Specify Input Type, must match number of inputs (use
                        -l 1 for list): 1,2,4
  -t OTYPE, --outtype=OTYPE
                        Specify Output Type, must match number of outputs (use
                        -l 1 for list): 1,2,4
  -l LIST, --list=LIST  Set to 1 to get List of Categories and I/O Types (use
                        -l 1 for list)
  -e EXT, --ext=EXT     Create Internal or External Component, default 1, set
                        to 0 for Internal
```

For external plugin nodes you can use the -d option to have it automatically add the new plugin to the CMake build list.

For internal nodes it will automatically add the #include to the internal_nodes.hpp file, if you make a mistake or want to delete the node source files you will have to edit internal_nodes.hpp manually to remove the inlude statement.

