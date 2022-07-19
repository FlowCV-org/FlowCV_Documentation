# Processing Engine

The Processing Engine is a headless processing application used to deploy flow graphs for production or testing on target platforms where you either don't have an active display/monitor or you don't want the extra overhead of the GUI engine running for final deployment.

Usage:
```commandline
Processing_Engine.exe  -f <string> [--] [--version] [-h]


Where:

   -f <string>,  --flow <string>
     (required)  Flow File

   --,  --ignore_rest
     Ignores the rest of the labeled arguments following this flag.

   --version
     Displays version information and exits.

   -h,  --help
     Displays usage information and exits.
```

See [Headless Example](headless.md) for more info.


