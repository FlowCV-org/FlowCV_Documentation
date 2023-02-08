# DNN - Human Pose

Human pose estimation will estimate the skeletal pose of the human body and/or hand(s) depending on the model and mode. Some models also support multi-person or multi-hand estimation.


---

See [Deep Learning in OpenCV](https://github.com/opencv/opencv/wiki/Deep-Learning-in-OpenCV) for information about supported frameworks and supported layers.

Some tested models with parameters:

| Model                                                                                                             | Config                                                                                                                                               | Mode | Size (W x H) | Mean      | Scale   | RGB   |
|-------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------|--------------|-----------|---------|-------|
| [OpenPose COCO model](http://posefs1.perception.cs.cmu.edu/OpenPose/models/pose/coco/pose_iter_440000.caffemodel) | [OpenPose COCO config](https://raw.githubusercontent.com/CMU-Perceptual-Computing-Lab/openpose/master/models/pose/coco/pose_deploy_linevec.prototxt) | COCO | 368 x 368    | 0, 0, 0   | 0.00392 | false |
| [OpenPose MPII model](http://posefs1.perception.cs.cmu.edu/OpenPose/models/pose/mpi/pose_iter_160000.caffemodel)  | [OpenPose MPII config](https://raw.githubusercontent.com/opencv/opencv_extra/4.x/testdata/dnn/openpose_pose_mpi_faster_4_stages.prototxt)            | MPII | 368 x 368    | 0, 0, 0   | 0.00392 | false |
| [OpenPose Hand model](http://posefs1.perception.cs.cmu.edu/OpenPose/models/hand/pose_iter_102000.caffemodel)      | [OpenPose Hand config](https://raw.githubusercontent.com/CMU-Perceptual-Computing-Lab/openpose/master/models/hand/pose_deploy.prototxt)              | HAND | 368 x 368    | 0, 0, 0   | 0.00392 | false |

