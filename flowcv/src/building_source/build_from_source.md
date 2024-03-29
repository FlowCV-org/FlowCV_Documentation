# Build From Source

### System Requirements:
* C++ 17 Compiler:
  * Windows 10+ (64-bit): Visual Studio 2019 or 2022
  * Ubuntu 18+: gcc 8+ (technically you could use gcc 7 but see note below)
  * macOS 12+: XCode 13+
* CMake 3.20+
* On Ubuntu and macOS you will need OpenCV 4.1+ library package installed

_** in gcc 7 std::filesystem is implemented in std::experimental::filesystem so the code won't work without some changes to the includes and namespaces involving std::filesystem_


### Clone the Repo

The documentation is added as a submodule, it is not required for any of the build steps so if you don't want the documentation source you don't need to clone recursively.

**_Make sure you have [LFS installed and enabled](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage), some of the various binary files (icons, images, etc.) are stored using LFS._**

```commandline
git clone https://github.com/FlowCV-org/FlowCV.git
```

if you do want the documentation source:
```commandline
git clone --recursive https://github.com/FlowCV-org/FlowCV.git
```

For platform specific build instructions use the links below

### Building for specific platforms

- [Windows](windows.md)
- [Linux](linux.md)
- [MacOS](macos.md)


