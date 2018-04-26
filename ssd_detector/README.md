## SSD: Single Shot MultiBox Detector for traffic scenario

arXiv:1512.02325

Keras implementation obtained from https://github.com/pierluigiferrari/ssd_keras and adapted to deal with video.

The main file is 'detect_vehicles_from_video.py' which has two parameters as follows:

* Path of the video
* folder to save the detections of each frame. For instance, /home/user/destination/
Also, it is important to change the weight file path and the path where is going to save the update weight.

Requirements:

* Python 2
* Numpy
* TensorFlow
* Keras 2
* OpenCV 2