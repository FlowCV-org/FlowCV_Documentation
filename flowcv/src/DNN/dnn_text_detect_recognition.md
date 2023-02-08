# DNN - Text Detection and Recognition

Text detection and recognition nodes can detect where text is in an image and then provide the output with bounding box position and text string.

Pass the output of text detection into the input of text recognition to enable the full process.

---

See [Deep Learning in OpenCV](https://github.com/opencv/opencv/wiki/Deep-Learning-in-OpenCV) for information about supported frameworks and supported layers.

Some tested models with parameters:

Text Detection:

| Model                                                                                               | Size (W x H) | Mean                   | Scale    | RGB  |
|-----------------------------------------------------------------------------------------------------|--------------|------------------------|----------|------|
| [DB_IC15_resnet50](https://drive.google.com/uc?export=dowload&id=17_ABp79PlFt9yPCxSaarVc_DKTmrSGGf) | 1280 x 736   | 122.68, 116.67, 104.01 | 0.00392  | true |
| [DB_IC15_resnet18](https://drive.google.com/uc?export=dowload&id=1vY_KsDZZZb_svd5RT6pjyI8BS1nPbBSX) | 1280 x 736   | 122.68, 116.67, 104.01 | 0.00392  | true |
| [DB_TD500_resnet50](https://drive.google.com/uc?export=dowload&id=19YWhArrNccaoSza0CfkXlA8im4-lAGsR)| 736 x 736    | 122.68, 116.67, 104.01 | 0.00392  | true |
| [DB_TD500_resnet18](https://drive.google.com/uc?export=dowload&id=1sZszH3pEt8hliyBlTmB-iulxHP1dCQWV)| 736 x 736    | 122.68, 116.67, 104.01 | 0.00392  | true |

Text Recognition:

| Model          | Vocabulary                                                                                                          | Size (W x H) | Mean                | Scale     | RGB   |
|----------------|---------------------------------------------------------------------------------------------------------------------|--------------|---------------------|-----------|-------|
| [crnn](https://drive.google.com/uc?export=dowload&id=1ooaLR-rkTl8jdpGy1DoQs0-X0lQsB6Fj)       | [alphabet 36](https://drive.google.com/uc?export=dowload&id=1oPOYx5rQRp8L6XQciUwmwhMCfX0KyO4b)                      | 100 x 32     | 127.5, 127.5, 127.5 | 0.0078431 | false |
| [crnn cs](https://drive.google.com/uc?export=dowload&id=12diBsVJrS9ZEl6BNUiRp9s0xPALBS7kt)    | [alphabet 94](https://drive.google.com/uc?export=dowload&id=1oKXxXKusquimp7XY1mFvj9nwLzldVgBR)                      | 100 x 32     | 127.5, 127.5, 127.5 | 0.0078431 | true  |
| [crnn cs CN](https://drive.google.com/uc?export=dowload&id=1is4eYEUKH7HR7Gl37Sw4WPXx6Ir8oQEG) | [alphabet 3944 Chinese characters](https://drive.google.com/uc?export=dowload&id=18IZUUdNzJ44heWTndDO6NNfIpJMmN-ul) | 100 x 32     | 127.5, 127.5, 127.5 | 0.0078431 | true  |
