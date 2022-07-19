# Nodes

Currently Implemented Nodes (Many more to come)

## Internal Nodes:
| Name                   | Description                                                                | OpenCV Info                                                                                                                 |
|------------------------|----------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------|
| Abs_Diff               | Absolute difference between two inputs                                     | [absdiff](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga6fef31bc8c4071cbc114a758a2b79c14)                  |
| Add                    | Sum of two inputs                                                          | [add](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga10ac1bfb180e2cfda1701d06c24fdbd6)                      |
| Add_Weighted           | Weighted sum of two inputs                                                 | [addWeighted](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#gafafb2513349db3bcff51f54ee5592a19)              |
| Background_Subtraction | Background/Foreground segmentation                                         | [BackgroundSubtractor](https://docs.opencv.org/4.2.0/d7/df6/classcv_1_1BackgroundSubtractor.html)                           |
| Bitwise                | Bitwise logic operators                                                    | [Bitwise](https://docs.opencv.org/4.2.0/d2/d18/group__core__hal__interface__logical.html)                                   |
| Blob_Detector          | Extract blobs from image                                                   | [SimpleBlobDetector](https://docs.opencv.org/4.2.0/d0/d7a/classcv_1_1SimpleBlobDetector.html)                               |
| Blur                   | Blurs an image using various methods                                       | [blur](https://docs.opencv.org/4.2.0/d4/d86/group__imgproc__filter.html#ga8c45db9afe636703801b0b2e440fce37)                 |
| Canny                  | Finds edges using Canny algorithm                                          | [Canny](https://docs.opencv.org/4.2.0/dd/d1a/group__imgproc__feature.html#ga04723e007ed888ddf11d9ba04e2232de)               |
| Color_Correct          | Simple color correction controls                                           |                                                                                                                             |
| Color_Reduce           | Simple color reduction filter                                              |                                                                                                                             |
| Contours               | Finds contours in a binary image                                           | [findContours](https://docs.opencv.org/4.2.0/d3/dc0/group__imgproc__shape.html#gadf1ad6a0b82947fa1fe3c3d497f260e0)          |
| Convert_Color          | Convert from one color space to another                                    | [cvtColor](https://docs.opencv.org/4.2.0/d8/d01/group__imgproc__color__conversions.html#ga397ae87e1288a81d2363b61574eb8cab) |
| Copy_Make_Border       | Forms a border around an image                                             | [copyMakeBorder](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga2ac1049c2c3dd25c2b41bffe17658a36)           |
| Crop                   | Crop a region of interest                                                  | [roi](https://docs.opencv.org/4.2.0/d1/d9d/classcv_1_1MatOp.html#a4a39d30a977f213f196420244fe1708b)                         |
| DCT                    | Discrete Cosine Transform                                                  | [dct](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga85aad4d668c01fbd64825f589e3696d4)                      |
| DFT                    | Discrete Fourier Transform                                                 | [dft](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#gadd6cf9baf2b8b704a11b5f04aaf4f39d)                      |
| Divide                 | division of two inputs                                                     | [divide](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga6db555d30115642fedae0cda05604874)                   |
| Draw_Date_Time         | Draw date/time overlay on image                                            |                                                                                                                             |
| Draw_JSON              | Draw JSON data key/values on image                                         |                                                                                                                             |
| Draw_Number            | Draw node number output on image                                           |                                                                                                                             |
| Draw_Text              | Draw text on image                                                         | [putText](https://docs.opencv.org/4.2.0/d6/d6e/group__imgproc__draw.html#ga5126f47f883d730f633d74f07456c576)                |
| Get_Optimal_DFT_Size   | Gets optimal DFT size for image                                            | [getOptimalDFTSize](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga6577a2e59968936ae02eb2edde5de299)        |
| Get_Size               | Get image resolution and outputs Int array                                 |                                                                                                                             |
| Histogram              | Viewer for Histogram plot                                                  |                                                                                                                             |
| Hough_Circles          | Finds circles in grayscale image using Hough transform                     | [HoughCircles](https://docs.opencv.org/4.2.0/dd/d1a/group__imgproc__feature.html#ga47849c3be0d0406ad3ca45db65a25d2d)        |
| Json_Viewer            | Viewer to view JSON data stream                                            |                                                                                                                             |
| Laplacian              | Calculates the Laplacian of an image                                       | [Laplacian](https://docs.opencv.org/4.2.0/d4/d86/group__imgproc__filter.html#gad78703e4c8fe703d479c1860d76429e6)            |
| Magnitude              | Calculates magnitude of two inputs                                         | [magnitude](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga6d3b097586bca4409873d64a90fe64c3)                |
| Max                    | Biggest finite value                                                       | [max](https://docs.opencv.org/4.2.0/d7/dcc/group__core__utils__softfloat.html#ga6361d683afa3e472e06a0c2e80984f00)           |
| Mean                   | Average (mean) of individual input array channels                          | [mean](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga191389f8a0e58180bb13a727782cd461)                     |
| Min                    | Smallest normalized value                                                  | [min](https://docs.opencv.org/4.2.0/d7/dcc/group__core__utils__softfloat.html#ga2473116e9ce9a101a7e6ed53753df9b6)           |
| Morphology             | Performs advanced morphological transformations                            | [morphologyEx](https://docs.opencv.org/4.2.0/d4/d86/group__imgproc__filter.html#ga67493776e3ad1a3df63883829375201f)         |
| Multiply               | Calculates the per-element scaled product of two inputs                    | [multiply](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga979d898a58d7f61c53003e162e7ad89f)                 |
| Normalize              | Normalize the value range of input array                                   | [normalize](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga87eef7ee3970f86906d69a92cbf064bd)                |
| Resize                 | Resize an image                                                            | [resize](https://docs.opencv.org/4.2.0/da/d54/group__imgproc__transform.html#ga47a974309e9102f5f08231edc7e7529d)            |
| Rnd_Noise              | Generate random noise image                                                | [randu](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga1ba1026dca0807b27057ba6a49d258c0)                    |
| Scale_Abs              | Scale, calc abs value and convert to 8-bit                                 | [convertScaleAbs](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#ga3460e9c9f37b563ab9dd550c4d8c4e7d)          |
| Scharr                 | Calculates first x or y derivative using Scharr operator                   | [Scharr](https://docs.opencv.org/4.2.0/d4/d86/group__imgproc__filter.html#gaa13106761eedf14798f37aa2d60404c9)               |
| Sobel                  | Calculates first, second, third or mixed derivartives using Sobel operator | [Sobel](https://docs.opencv.org/4.2.0/d4/d86/group__imgproc__filter.html#gacea54f142e81b6758cb6f375ce782c8d)                |
| Subtract               | Calculate per-element difference between two inputs                        | [subtract](https://docs.opencv.org/4.2.0/d2/de8/group__core__array.html#gaa0f00d98b4b5edeaeb7b8333b2de353b)                 |
| Threshold              | Applies a fixed-level threshold to each input array element                | [threshold](https://docs.opencv.org/4.2.0/d7/d1b/group__imgproc__misc.html#gae8a4a146d1ca78c626a53577199e9c57)              |
| Transform              | Translate, Scale and/or Rotate an image                                    |                                                                                                                             |
| Viewer                 | 2D Image Viewer                                                            | [viewer](./viewer.md)                                                                                                       |
| Depth_Viewer_3D        | 3D Pointcloud Viewer                                                       | [viewer 3D](./viewer3D.md)                                                                                                  |

## Included Plugins:
| Name | Description                                                   | Info                                                                                              |
|------|---------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| CSV_File     | Write JSON generated data to CSV files                        |                                                                                                          |
| Image_Loader    | Load individual image files                                   | [imread](https://docs.opencv.org/4.2.0/d4/da8/group__imgcodecs.html#ga288b8b3da0892bd651fce07b3bbd3a56)  |
| Image_Writer    | Write individual image files                                  | [imwrite](https://docs.opencv.org/4.2.0/d4/da8/group__imgcodecs.html#gabbc7ef1aa2edfaa87772f1202d67e0ce) |
| OSC_Send     | Send OSC network data                                         |                                                                                                          |
| Serial_Send | Send data over serial connection                              |                                                                                                          |
| Shape_Colorizer | Colorize shapes                                               |                                                                                                          |
| Shape_Counter   | Count shapes                                                  |                                                                                                          |
| Simple_Blob_Tracker | Very simplistic 2D blob motion tracker                        |                                                                                                          |
| TCP_Send        | Send data over TCP network connection                         |                                                                                                          |
| UDP_Send        | Send data over UDP network connection                         |                                                                                                          |
| Video_Capture    | Capture images from web camera or other video capture devices | [VideoCapture](https://docs.opencv.org/4.2.0/d8/dfe/classcv_1_1VideoCapture.html)                        |
| Video_Loader    | Load images from video files                                  | [VideoCapture](https://docs.opencv.org/4.2.0/d8/dfe/classcv_1_1VideoCapture.html)                        |
| Video_Writer    | Save processed video stream to video file                     | [VideoWriter](https://docs.opencv.org/4.2.0/dd/d9e/classcv_1_1VideoWriter.html)                                                                                          |


## Extra Plugins (separate repos):
| Name | Description                | Info                                                                                                               |
|------|----------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Head_Face_Emotion     | OpenVino - detect head, facial landmarks, head pose and emotions | [OpenVino Head Face Emotion Detector](https://docs.openvino.ai/2022.1/omz_demos_interactive_face_detection_demo_cpp.html) |
| Pose_Estimation_2D     | OpenVino - 2D human pose estimation | [OpenVino Pose Estimation](https://docs.openvino.ai/2022.1/omz_demos_human_pose_estimation_demo_cpp.html)                 |
| Realsense_Camera     | RealSense 3D camera support | [libRealSense](https://github.com/IntelRealSense/librealsense)                                                            |
| NDI_Receiver     | NDI video stream receiver  | [NDI](https://www.ndi.tv/)                                                                                                |
| NDI_Sender                 | NDI video stream sender    | [NDI](https://www.ndi.tv/)                                                                                                |
| AprilTag_Detector                 | Simple april tag detector  | [AprilTag](https://april.eecs.umich.edu/software/apriltag)                                                                |

