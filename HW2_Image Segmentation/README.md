# Image Segmentation project
________________________
### [Artificial Neural Networks and Deep Learning course](http://chrome.ws.dei.polimi.it/index.php?title=Artificial_Neural_Networks_and_Deep_Learning)
- Academic year 2020-2021
- 1st semester of 2nd year
- [Politecnico di Milano](https://www.polimi.it/)

________________________
 Group members:
 -
 - Saeid Rezaei
 - Abdolvakil Fazli


________________________
## Problem description
In this assignment the task of multiclass semantic segmentation for Bipbip dataset drawn from the first round of [ACRE Cascade Competition](https://competitions.codalab.org/competitions/27176) is being studied. ACRE is the Agri-food Competition for Robot Evaluation, part of the METRICS project funded by the European Union’s Horizon 2020 research and innovation program under grant agreement No 871252. Autonomous robots compete to demonstrate their ability to perform agricultural tasks (such as removing weeds or surveying crops down to individual-plant resolution).  The same network, maybe with a little bit of different parameters or fine tunings, can be used for other type of the datasets (PEAD, ROSEAU, WeedElec) in the competition.

________________________
## Data Description

### Dataset Details
Basically, we are given some images of different classes, and different kinds, and the task is to write a segmentation algorithm such that a robot can perform accurate separation from weed/crop classification. The dataset is composed of images captured by different sensors in different moments and are about two kinds of crops: haricot and maize. Images in the dataset are divided into different folders based on the team that acquired the image, i.e., Bipbip, Pead, Roseau, Weedelec. For each team, we have two different sub-folders named as the type of crop present in the images, i.e., Haricot and Mais. Finally, for each crop, we provide the captured RGB images, in the Images folder, and the corresponding ground-truth segmentations, in the Masks folder. A aptured RGB image and its corresponding ground-truth is shown as following:
 <p float="left">
  <img src="Bipbip_haricot_im_00321.jpg" width="500" />
  <img src="Bipbip_haricot_im_00321.png" width=500 /> 
</p>

### Dataset Structure
Two folders:
```
- training/
    -Bipbib
       -Haricot
           -Images
              - img1, img2, ... , imgN
           -Masks
              - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
    -Pead
       -Haricot
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
    -Roseau
       -Haricot
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
    -Weedelec
       -Haricot
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
           -Masks
               - img1, img2, ... , imgN
      - img1, img2, ... , imgN
    
- test_Dev/
    -Bipbib
       -Haricot
           -Images
              - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
    -Pead
       -Haricot
           -Images
               - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
    -Roseau
       -Haricot
           -Images
               - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN
    -Weedelec
       -Haricot
           -Images
               - img1, img2, ... , imgN
       -Mais
           -Images
               - img1, img2, ... , imgN

```
