# Installation

For easy installation use one of the pre-compiled binary install packages available in the [github release section](https://github.com/FlowCV-org/FlowCV/releases)

## Windows

---

* Download setup file
* Run the setup exe and follow the prompts


## Ubuntu

---

* Download the debian package
* The run command in folder with deb package: ```sudo apt install ./flowcv-app-0.1.0-ubuntu.deb```
  * If you're missing dependencies you can run: ```sudo apt --fix-broken install```


## macOS

---

First install system dependencies

You'll need [home-brew](https://brew.sh) to install the packages

Once you have home-brew installed then run the following commands to install the package dependencies
```commandline
brew install opencv
brew install glfw3
brew install glew
brew install cmake
```

* Download MacOS DMG Package
* Double Click on DMG file
* Open Mounted DMG
* Drag FlowCV_Editor to Applications

If you get an error when launching you may need to modify the Privacy settings for Input Monitoring

Open Privacy Settings in System Settings:

![privacy settings](../images/macos_privacy_setting.png)

Unlock Input Monitoring and Enable FlowCV_Editor:

![input monitoring](../images/macos_privacy_input.png)



