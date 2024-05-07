# Neural-Networks-Project---Gesture-Recognition
This project is made to recognize the hand gestures using the CNN(Convolutional Neural Network) which is then can be used for automation of the home appliances.

# Table of Contents
# General Information

## Problem Statement

Imagine you are working as a data scientist at a home electronics company which manufactures state of the art smart televisions. You want to develop a cool feature in the smart-TV that can recognise five different gestures performed by the user which will help users control the TV without using a remote.

The gestures are continuously monitored by the webcam mounted on the TV. Each gesture corresponds to a specific command:

Gesture Corresponding Action

- Thumbs Up - Increase the volume.
- Thumbs Down - Decrease the volume.
- Left Swipe -'Jump' backwards 10 seconds.
- Right Swipe -'Jump' forward 10 seconds.
- Stop - Pause the movie.

Each video is a sequence of 30 frames (or images).

# Dataset
The training data consists of a few hundred videos categorised into one of the five classes. Each video (typically 2-3 seconds long) is divided into a sequence of 30 frames(images). These videos have been recorded by various people performing one of the five gestures in front of a webcam - similar to what the smart TV will use. The data is in a zip file. The zip file contains a 'train' and a 'val' folder with two CSV files for the two folders. These folders are in turn divided into subfolders where each subfolder represents a video of a particular gesture. Each subfolder, i.e. a video, contains 30 frames (or images). Note that all images in a particular video subfolder have the same dimensions but different videos may have different dimensions. Specifically, videos have two types of dimensions - either 360x360 or 120x160 (depending on the webcam used to record the videos). Each row of the CSV file represents one video and contains three main pieces of information - the name of the subfolder containing the 30 images of the video, the name of the gesture and the numeric label (between 0-4) of the video.

# Neural Network Used

## 3D Convolutional Neural Network
A 3D Convolutional Neural Network (CNN) is a deep learning algorithm that uses 3D convolutions to extract features from spatio-temporal data, such as videos or medical imaging. It can capture both spatial and temporal dependencies in the data, making it useful for tasks such as action recognition or disease diagnosis.

## CNN+GRU Models
- CNN will act as the feature extractor
- GRU will help us with the TimeSeries prediction of the images
- ConvGRU class is extension of ModelClass with a different architecture CNN+GRU
- Base Model with few conv2D- BatchNorm - maxPool ordered layers
- Using GRU instead of LSTM to avoid more parameters, as we want to deploy on mobile applications and smart TV.

## MobileNet + GRU
MobileNet is a type of convolutional neural network architecture designed for efficient computation on mobile devices. On the other hand, GRU (Gated Recurrent Unit) is a type of recurrent neural network (RNN) architecture that is commonly used for sequential data processing, such as natural language processing or time series prediction.

# Results

## MobileNet(with complete training over all the layers) + GRU
- Model17 -> MobileNet(with complete training over all the layers) + GRU -> epoch 21st Model -> Validation accuracy 98% -> validation loss 0.0980
- Total params: 3,693,253
- Trainable params: 3,669,317
- Non-trainable params: 23,936
- The validation loss is way lesser ~0.0980 than the conv3D Model with 0.5910
- The accuracy is 98% which is remarkable than Conv3D model with 84%
- Trainable params are almost thrice but a 42MB model is not a huge model when compared to CNNs which end up in GBs.
- Models in MBs are easily deployable on smart devices.

# Contact
Created by [@GowthamiGanga] - feel free to contact me!

