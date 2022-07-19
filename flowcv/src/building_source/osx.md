# Build On OSX

First install system dependencies

You'll need [home-brew](https://brew.sh) to install the packages

Once you have home-brew installed then run the following commands to install the package dependencies
```commandline
brew install opencv
brew install glfw3
brew install glew
brew install cmake
```

### Building With CLion IDE

---

1. Open Project/Folder
2. In Settings Panel in CMake section create a Release Build
3. For CMake options set the following to ON or OFF based on what you want to build:
    * -DBUILD_EXAMPLES=ON
    * -DBUILD_EDITOR=ON
    * -DBUILD_ENGINE=ON
    * -DBUILD_PLUGINS=ON
4. Then build all in release

---


### Building With XCode

---

Open a terminal and cd to the repo directory

Then Run (Change build options as needed):
```commandline
mkdir Build
cd Build
cmake -G "Xcode" -DBUILD_EXAMPLES=ON -DBUILD_EDITOR=ON -DBUILD_ENGINE=ON -DBUILD_PLUGINS=ON ..
make
```

Once the XCode project has been created open it in XCode

Set the active scheme to ALL_BUILD:

![all_build](../images/osx_set_all_build.png)

Now select Edit Scheme:

![edit_scheme](../images/osx_edit_scheme.png)

In the Edit Scheme Dialog change build configuration to Release:

![build release](../images/osx_edit_release.png)

Close the dialog and then Build:

![build](../images/osx_build.png)

