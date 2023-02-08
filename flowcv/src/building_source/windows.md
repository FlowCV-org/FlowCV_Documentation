# Building On Windows

* [Building with CLion](#building-with-clion-ide)
* [Building with Visual Studio and CMake GUI](#building-with-cmake-and-visual-studio-gui-method)
* [Building with Visual Studio and CMake cmd line](#building-with-cmake-and-visual-studio-command-line-method)


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


### Building With CMake and Visual Studio (GUI Method)

---

1. Download [CMake for Windows](https://cmake.org/download/)
2. Run CMake GUI

Now set the build path and source directory:

![set paths](../images/win_cmake_set1.jpg)

Now Add Entry for the build type:

![build type](../images/win_cmake_release.jpg)

After adding the entry press the Configure button, set the checkboxes for which executable you want to build

Then press Configure again and then Generate

![config build](../images/win_cmake_configure.jpg)

3. Once complete it will generate a Visual Studio solution file in the Build dir that you can load: OpenCV_Dataflow_Framework.sln
4. After opening the solution file in Visual Studio then build solution

---

### Building With CMake and Visual Studio (Command Line Method)

---

1. cd to the source path
2. mkdir Build
3. cd Build
4. run the following command (Change the build options as desired):
```commandline
cmake .. -DBUILD_EXAMPLES=OFF -DBUILD_EDITOR=ON -DBUILD_ENGINE=ON -DBUILD_PLUGINS=ON -DCMAKE_BUILD_TYPE=Release
```
5. open Visual Studio project: OpenCV_Dataflow_Framework.sln
6. Build Project

---


### OpenCV Download

The CMake build script should automatically download and extract the pre-compiled binaries during the build initialization but if for some reason you run into an issue you can download and extract the file manually.

[OpenCV 4.5.5](https://github.com/opencv/opencv/releases/download/4.5.5/opencv-4.5.5-openvino-dldt-2021.4.2-vc16-avx2.zip)

add the following build setting to CMake (change path to your extracted location):
```commandline
-DOpenCV_DIR=c:\path\to\extracted\opencv\files
```
