# Framing_Testing_Reconstruction
>This is test code for video to frame conversion, detection of real or fake images in frames and reconstruction of video in .avi format with probability of realness and fakeness of faces in video.
## Table of Contents
* [Technology used](#technology-used)
* [Required pretrained models](#required-pretrained-model)
* [Algorithm](#algorithm)
## Technology used
>1. Tensorflow
>2. keras
>3. dlib
## Required pretrained model 
>1. **For face detection:**
*https://github.com/davisking/dlib-models/raw/master/mmod_human_face_detector.dat.bz2*
>2. **Inception v3:**
>Inceptionv3 is a convolutional neural network for assisting in image analysis and object detection, and got its start as a module for Googlenet. It is the third edition of Google's Inception Convolutional Neural Network, originally introduced during the ImageNet Recognition Challenge. Just as ImageNet can be thought of as a database of classified visual objects, Inception helps classification of objects in the world of computer vision.
![](https://miro.medium.com/max/700/1*gqKM5V-uo2sMFFPDS84yJw.png)
><br/>With 42 layers deep, the computation cost is only about 2.5 higher than that of GoogLeNet, and much more efficient than that of VGGNet.
## Algorithm
>Algorithm can be subdivided into 3 main steps as follows:
>1. Framing
>2. Prediction
>3. Reconstruction
### Framing
>Video from dataset is converted into frames & frames are saved as .jpg files.
### Prediction
>Pretrained face detection model is used for detecting faces. The model takes list of images & returns 2D mmod rectangles.With the help of this model, human faces are detected
>& using coordinates of rectangles returned by model frames are cropped, resized & data normalization is performed.Output is predicted for each frame. Rectangles around faces, probability of whether faces are real or fake are inserted in the frame and the frame is stored in folder. For prediction, transfer learning is used with base model **Inception v3**.
### Reconstruction
>All the frames are stored in an image array. Image array is further processed to form a video (.avi format). 
<br/>The process is repeated for all videos in dataeset.

 


