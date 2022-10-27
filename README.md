## Semantic Segmentation Of Waste Images Using U-Net

Solid waste management is a universal issue that matters to every single person in the world. Poorly managed waste is contaminating the world’s oceans, clogging drains and causing flooding, transmitting 
diseases, increasing respiratory problems from burning, harming animals that consume waste unknowingly. Waste segregation is the first step in a waste management plan that will help the environment. For many 
business, the most common form of segregation is separating out recyclable waste such as paper, plastic and glass from landfill and biodegradable waste. Effective segregation of wastes means that less waste goes to landfill which makes it cheaper and better for people and the 
environment.

#### Objective

The problem with manual method of waste collection and segregation is that it is prone to human errors. Most of the workers are not educated and cannot differentiate among the different varieties of waste objects 
thus the segregation is not very effective. Thus segregation of waste by automated machines are a better and faster solution. Thus the objective of this project is to perform semantic segmentation of waste objects from images which 
can be solution of localizing waste based on images taken and make the work of waste segregation easier. For the semantic segmentation the MJU-Waste dataset (https://github.com/realwecan/mju-waste) with 2475 RGBD images has been used where 
each image is annotated with a pixel wise waste object mask and we tried implementing U-Net an extension of an encoder-decoder fully convolutional network.

#### MJU-Dataset
In order to train the U-Net model for performing semantic segmentation the MJU waste dataset [2] 
has been used that has 2475 RGBD images each annotated with a pixel wise waste object mask. It is 
comprised of 2475 indoor trash images manually annotated in the form of an instance mask. It allows 
two-class semantic segmentation of waste and background. For each color image, the co-registered 
depth image captured using an RGBD camera is provided. The objects are hand-held and situated 
mostly in the center of the image.

##### A glimpse of the dataset is shown below:
![image](https://user-images.githubusercontent.com/67185084/192427434-5363196d-b544-4130-a03f-33a0db25a12d.png)

#### Block Diagram

![image](https://user-images.githubusercontent.com/67185084/192424166-6fa4a121-6901-44ac-a9c3-25606eda7557.png)
The block diagram depicts the various phases in which the project work was carried out. All the steps 
starting from finding an appropriate dataset till training the final U-Net model with ResNet 34 backbone and 
making final prediction of segmented masks have been highlighted in the following block diagram.

### RESULTS AND DISCUSSION
##### The pixel accuracy graph for the three backbones
![image](https://user-images.githubusercontent.com/67185084/192427719-1f83ace1-5bae-4937-a5d8-4de37fb3de7e.png)

##### Training and validation loss for the three backbones
![image](https://user-images.githubusercontent.com/67185084/198282979-e35f218f-4854-439d-8ce7-1ec5d4c1a1d5.png)
![image](https://user-images.githubusercontent.com/67185084/198283045-09420ec0-8345-4baa-b784-132d722085dd.png)


#### IoU 
Intersection over Union is a common evaluation metrics for semantic segmentation. It is a term used to describe the extent of overlap of two images. The greater the region of overlap, the greater the IoU. It is 
very important metric to evaluate how the mode is performing the segmentation task.[31] If IoU is close to 1 
then we can say that our model perfectly anticipated object. If IoU is close to 0 or 0 then we can say that our 
model did not predict object coordinates at all.
#####Code for IoU-
![image](https://user-images.githubusercontent.com/67185084/192429651-4c578a36-50ee-469a-8271-1fe2e5388be7.png)
##### Table

CNN Architecture	Backbone	    IoU (Intersection over Union)
U-Net	            ResNet 18	             40.49

U-Net	            ResNet 34	             63.01

U-Net	            ResNet 50	             27.88

### Final Result Of prediction

![image](https://user-images.githubusercontent.com/67185084/192426003-e61b9f33-4f9a-4500-ad32-7e9b041cdcc6.png)

