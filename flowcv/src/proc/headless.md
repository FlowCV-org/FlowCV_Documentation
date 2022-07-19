# Running A Flow In Headless Mode

Example Run:
```commandline
Processing_Engine.exe -f face_detection.flow
```

Example Output:
```commandline
Data Flow Processing Engine - v0.1.0

Loading Plugins...
Looking for Plugins in: E:\Dev_Tmp\OpenCV_Dataflow_Framework\Build\Plugins
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\CsvFile.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\ImageLoader.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\ImageWriter.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\Openvino_Plugins\\Head_Face_Emotion.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\Openvino_Plugins\\Pose_Estimation_2D.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\OscSend.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\RealSense\\Realsense_Camera.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\SerialSend.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\ShapeColorizer.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\ShapeCounter.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\SimpleBlobTracker.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\TcpSend.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\UdpSend.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\VideoCapture.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\VideoLoader.fp"
"E:\\Dev_Tmp\\OpenCV_Dataflow_Framework\\Build\\Plugins\\VideoWriter.fp"
16 Plugin(s) Loaded
Loading Flow File: face_detection.flow
Adding Node Instance (Internal): Viewer, 1001
Adding Node Instance (Plugin): Video_Capture, 2001
Adding Node Instance (Plugin): Head_Face_Emotion, 3001
Flow State Loaded, 3 Nodes Loaded and Configured
Flow Processing Started
```

