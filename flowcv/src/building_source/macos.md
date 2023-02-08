# Build On OSX

First install system dependencies

You'll need [home-brew](https://brew.sh) to install the packages

Once you have home-brew installed then run the following commands to install the package dependencies
```commandline
brew install glfw3
brew install glew
brew install cmake
```

Download [OpenVino Toolkit](https://www.intel.com/content/www/us/en/developer/tools/openvino-toolkit/download.html) version 2022.1

Follow the installation instructions

After install run the OpenVino OpenCV Installer script:
```commandline
/opt/intel/openvino_2022/extras/scripts/download_opencv.sh
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
cmake .. -DBUILD_EXAMPLES=ON \
-DBUILD_EDITOR=ON \
-DBUILD_ENGINE=ON \
-DBUILD_PLUGINS=ON \
-DOpenCV_DIR=/opt/intel/openvino_2022/extras/opencv/cmake
cmake --build . --config Release j 8
```

_** replace -j 8 with your number of CPUs you want to utilize for compiling_


