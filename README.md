# Embedded Traffic Sign Detection
## About
The target of this project is to create a Neural Network for Traffic Sign Detection, 
which can exectued on an embedded device 
(e.g. Smartphone, Raspberry PI + Google Coral TPU, Nvidia Jetson Nano). 
The first step will be the recognition only for speed limit signs. 
As NN architecture pre-trained SSD was selected, because of it's good performance especially on embedded devices.
The pre-trained NN is a [SSD MobileNet V2 FPN-Lite](https://hub.tensorflow.google.cn/tensorflow/ssd_mobilenet_v2/fpnlite_640x640/1), 
which was trained with the [COCO](https://cocodataset.org/#home) object detection dataset. 
The resulting network will be converted to TensorFlow Lite, to execute it on the target. 

## Dataset
As a dataset the [GTSDB](https://benchmark.ini.rub.de/gtsdb_dataset.html) was used. 
Unfortunately this dataset is not very big and contains a lot of images with very small traffic signs. 
TODO: extend the training with the [BTSD](https://btsd.ethz.ch/shareddata/) or create a synthetic dataset.  

## Current State
The current recognition performance is quite poor. 
The reason for that is probably the very small size of most of the traffic signs from the GTSDB. 
If the traffic sign is bigger, it get's detected but most often wrong classified. 


## Refrences
The implementation of this project is inspired by the 
[Eager Few Shot Object Detection Colab](https://github.com/tensorflow/models/blob/master/research/object_detection/colab_tutorials/eager_few_shot_od_training_tf2_colab.ipynb)
example from TensorFlow. 

