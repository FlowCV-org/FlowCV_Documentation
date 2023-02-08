# Building On Linux

First install system dependencies (skip any of the ones you already have installed):
```commandline
sudo apt-get update
sudo apt-get install build-essential
sudo apt-get install libglfw3
sudo apt-get install libglfw3-dev
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


### Building From Command Line

---

if you already have CMake installed but it's < version 3.20, then first remove the old one:
```commandline
sudo apt remove --purge cmake
```

then run:
```commandline
sudo snap install cmake --classic
```

Now you're ready to build

cd to the source dir then (Change build options as needed):
```commandline
mkdir Build
cd Build
cmake .. -DBUILD_EXAMPLES=ON \
-DBUILD_EDITOR=ON \
-DBUILD_ENGINE=ON \
-DBUILD_PLUGINS=ON \
-DOpenCV_DIR=/opt/intel/openvino_2022/extras/opencv/cmake
cmake --build . --config Release -j 8
```

_** replace -j 8 with your number of CPUs you want to utilize for compiling_

