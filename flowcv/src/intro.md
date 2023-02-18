# Introduction

### What Is FlowCV?

---

FlowCV at its core is a free open source dataflow framework for computer vision processing workflows.

[![Intro Video](images/flowcv_ui.jpg)](https://www.youtube.com/watch?v=-4Yosc7vefo "Node Editor - Intro Video")

**Key Features:**
* Free and Open Source
* Intuitive User Interface
* OpenCV Integration
* Highly Performant C++ Code
* Plugin SDK to Easily Extend Functionality
* Cross Platform Compatability

The advantage of the dataflow framework is that it allows you to quickly create complex directed graph
processing flows that can branch and run in parallel to maximize processing resources and throughput.

![node example](images/nodes_01.jpg)

To make the creation of these workflows easy and intuitive there is a node graph editor user interface.
The editor allows you to easily create new nodes, connect the various inputs and outputs, adjust settings and send the resulting data over the network, for example to an embedded control system for automation, robotics or for data collection.

Once you're done creating your flow graph you can deploy it for production on your platform of choice
using the headless processing application.


### Why Was FlowCV Created?

---

The short answer is that nothing like it existed and I've been wanting something like this for several years now
so I decided to just write it myself and offer it as open source in the hopes that others will find it useful and
help contribute to its development so it can become even better and more useful, much like [OpenCV](https://opencv.org/)
itself which FlowCV is dependent on.

The longer answer is that I think a dataflow framework approach to computer vision is a great way to quickly
prototype OpenCV solutions. You can quickly build out workflows and experiment with different nodes and go
through various settings to see the results, all in real-time without writing a single line of code.
With other software out there taking a similar approach such as Unreal Blueprints, 
Houdini, Nuke, Touch Designer and Blender Geometry Nodes, my hope is that FlowCV will one day reach a similar level
of adoption and popularity and be used for everything from  education to deployment in production quality applications.

FlowCV is still in the very very early stages of development, there is still a lot of work to be done from testing
to implementing many more nodes and continuing to make improvements to the editor application.
Please consider helping by using the application and providing feedback.

If you are a developer and want to help contribute to its development please see the section on becoming a
[contributor](dev/contribute.md)
