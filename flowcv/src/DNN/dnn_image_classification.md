# DNN - Image Classification

Image classification will recognize and classify the contents of an image along with the confidence value.

---

See [Deep Learning in OpenCV](https://github.com/opencv/opencv/wiki/Deep-Learning-in-OpenCV) for information about supported frameworks and supported layers.

Some tested models with parameters:

| Model                                                                                                                                                          | Config                                                                                                                 | Classes                | Size (W x H) | Mean          | Scale | RGB   |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|------------------------|-----------|---------------|-------|-------|
| [SqueezeNet Model](https://raw.githubusercontent.com/DeepScale/SqueezeNet/b5c3f1a23713c8b3fd7b801d229f6b04c64374a5/SqueezeNet_v1.1/squeezenet_v1.1.caffemodel) | [SqueezeNet ProtoTxt](https://raw.githubusercontent.com/opencv/opencv_extra/4.x/testdata/dnn/squeezenet_v1.1.prototxt) | [Classification Txt](https://raw.githubusercontent.com/opencv/opencv/4.x/samples/data/dnn/classification_classes_ILSVRC2012.txt) | 227 x 227 | 0, 0, 0       | 1.0   | false |
| [GoogleNet Model](http://dl.caffe.berkeleyvision.org/bvlc_googlenet.caffemodel)                                                                                | [GoogleNet ProtoTxt](https://raw.githubusercontent.com/opencv/opencv_extra/4.x/testdata/dnn/bvlc_googlenet.prototxt)   | [Classification Txt](https://raw.githubusercontent.com/opencv/opencv/4.x/samples/data/dnn/classification_classes_ILSVRC2012.txt) | 224 x 224 | 104, 117, 123 | 1.0   | false |


