First Activity of Artificial Neural Networks and Deep Learning [course](http://chrome.ws.dei.polimi.it/index.php?title=Artificial_Neural_Networks_and_Deep_Learning).
=
- Academic year 2020-2021
- 1st semester of 2st year
- [Politecnico di Milano](https://www.polimi.it/)

________________________
 Group members:
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
                
 To read the images, we first upload the images in the Google Drive and then mount to the Drive and import the image file to the project, like following:
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
from keras.models import Sequential
from keras.layers import Dense, Dropout, Activation, Flatten
from keras.layers import Conv2D, MaxPooling2D
import time
import matplotlib.pyplot as plt
from google.colab import drive
```
## Model Training 
We implement a transfer learning approach using a pre-trained model `VGG16` that has been pre-trained on ImageNet.
Parameters:
- Model = VGG16
- Batch Size = 32
- Training/Validation split = 80/20%
- Image Augmentation + normalisation (ImageNet)

Approaches

### This project is related during the Artificial Neural Networks and Deep Learning [course](http://chrome.ws.dei.polimi.it/index.php?title=Artificial_Neural_Networks_and_Deep_Learning).
The goal of this project is to find a model that assign the corresponding class to the given images. There are 21 different classes. We will do this with the Convolutional Neural Network.
The UC Merced Land Use Dataset is used as the dataset in this project. you can download the data set [here](https://drive.google.com/file/d/18mva7AbCzf-rHpW5SEzpVDtoXAcVD5Mf/view?usp=sharing)
