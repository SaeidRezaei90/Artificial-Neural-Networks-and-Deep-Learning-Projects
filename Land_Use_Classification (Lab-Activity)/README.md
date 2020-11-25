First Activity of Artificial Neural Networks and Deep Learning [course](http://chrome.ws.dei.polimi.it/index.php?title=Artificial_Neural_Networks_and_Deep_Learning).
=
- Academic year 2020-2021
- 1st semester of 2st year
- [Politecnico di Milano](https://www.polimi.it/)

________________________
 Group member:
 -
> - Saeid Rezaei

________________________

# Land Use classification using Convolutional Neural Network

## Description
The Purpose of this Project is to classify land use image using [*Convolutional Neural Network*](https://cs231n.github.io/convolutional-networks/). The dataset used for this project is the [UC Merced dataset](https://drive.google.com/file/d/18mva7AbCzf-rHpW5SEzpVDtoXAcVD5Mf/view?usp=sharing), which consists of 21 land use classes. The structure of the data set is as following:

    - UCMerced_LandUse/
        - training/
            - agricultural/
                - img1, img2, …, imgN
            - …
            - parkinglot/ 
                - img1, img2, ... , imgN
        - validation/
            - agricultural/
                - img1, img2, …, imgN
            - …
            - parkinglot/ 
                - img1, img2, ... , imgN
        - test/
            - agricultural/
                - img1, img2, …, imgN
            - …
            - parkinglot/ 
                - img1, img2, ... , imgN
                
 To read the images, we first upload the zipped image file in the Google Drive and then mount to the Drive and import the image file to the project, like following:
 ```python
from google.colab import drive
drive.mount('/content/drive')
!unzip '/content/drive/My Drive/UCMerced_LandUse.zip'
```

This project is developed by using Python3.6, [Tensorflow](http://tensorflow.org) as a backend and [Keras](http://keras.io/) as powerful level deep learning library.

## Libraries used in the project
```python

import numpy as np
import os
import keras
import tensorflow as tf
from keras.models import Sequential
from keras.layers import Dense, Dropout, Activation, Flatten
from keras.layers import Conv2D, MaxPooling2D
from tensorflow.keras.preprocessing.image import ImageDataGenerator
from tensorflow.keras.applications.VGG16 import vgg16
import time
import matplotlib.pyplot as plt
from google.colab import drive
```
## Model Training 
We implement a transfer learning approach using a pre-trained model `VGG16` that has been pre-trained on ImageNet. We also use finetuning to tune some weights.
Important Parameters:
- Model = VGG16
- Batch Size = 32
- Learning rate = 1e-4
- Number of epoch = 30
- Training/Validation split = 80/20%
- Image Augmentation + normalisation

## Approache analysis
1) After studying the train set, it was observed that the dataset consisted images of 256x256 pixels. All the image in the dataset contains only 1 object (class) and so there was no image segmentation.
2) The train dataset is divided into 3 subcategory, training, validation and test, which each one contains 21 subfolders corresponding to 21 classes.
3) We use a pre-trained transfer learning technique for training and validation on the model. The [`VGG16`](https://keras.io/api/applications/vgg/#vgg16-function) model, was used as the base model. The weights for the `VGG16` model, trained on the `imagenet` dataset were loaded on the model.
4) We set the `include_top` parameter of `VGG16` to False, it means that all fully connected layers were removed from the VGG16 model and a new fully connected network was defined with a few layers.
5) To prevent `overfitting`, we use `dropout` with a coefficint 0.4, `GlobalAveragePooling2D` and `Earlystopping`.
6) `ImageDataGenerator` is used in order to increase the amount of data by adding slightly modified version of the images.
7) A `Callbacks` set is defined with parameters such as `Earlystopping`, `reduce_learning_rate`, `Modelcheckpoint` and `Tensorboard`.

## Test results
`model.evaluate` is used to verify the accuracy of the model.
```python
eval_out = model.evaluate(x=test_dataset,
                          steps=len(test_gen),
                          verbose=0)
eval_out
```
test loss, test accuracy: [0.06702920794487, 0.9809523820877075]
