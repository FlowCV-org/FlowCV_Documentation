# DNN - Segmentation

Semantic segmentation will create a color coded mask for each recognized class, the classes and colors are defined in separate files with correlating indices.

Colors are defined as RGB with values separated by spaces.

Example classes file:
```text
Unlabeled
Road
Sidewalk
Building
```

Example color file:
```text
0 0 0
128 64 128
244 35 232
70 70 70
```

---

See [Deep Learning in OpenCV](https://github.com/opencv/opencv/wiki/Deep-Learning-in-OpenCV) for information about supported frameworks and supported layers.

Some tested models with parameters:

| Model                                                                            | Config           | Classes                                                                                               | Colors                              | Size (W x H) | Mean    | Scale   | RGB   |
|----------------------------------------------------------------------------------|------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------|--------------|---------|---------|-------|
| [ENet model](https://www.dropbox.com/s/tdde0mawbi5dugq/Enet-model-best.net?dl=1) | no config file   | [enet classes](https://raw.githubusercontent.com/opencv/opencv/4.x/samples/data/dnn/enet-classes.txt) | [enet colors](./enet-colors.txt)    | 512 x 256    | 0, 0, 0 | 0.00392 | true  |
| [FCN8s model](http://dl.caffe.berkeleyvision.org/fcn8s-heavy-pascal.caffemodel)  | [FCN8s config](https://raw.githubusercontent.com/opencv/opencv_extra/4.x/testdata/dnn/fcn8s-heavy-pascal.prototxt) | [pascal classes](./pascal-classes.txt)    | [pascal colos](./pascal-colors.txt) | 500 x 500    | 0, 0, 0 | 1.0     | false |

