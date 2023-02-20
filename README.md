# Milestone-5 "Vegetable classification using STM32"

## Group Members
1. Alvin Chan Chin Khai
2. Beh Jun Long


## Table of contents
[1.0 Previous works](#Previous-works)
<br>
[2.0 Use Cases](#Use-Cases)
<br>
[3.0 System Architecture](#system-architecture)
<br>
[4.0 Online Platform and Software used](#Online-Platform-and-Software-used)
<br>
[5.0 Built and train model using Edge Impulse](#Built-and-train)

<a name="Previous-works"/></a>
## 1.0 Previous works
 - [High performance vegetable classification from images based on AlexNet deep learning model](https://ijabe.org/index.php/ijabe/article/view/2690/pdf)
 - [Improved Classification Approach for Fruits and Vegetables Freshness Based on Deep Learning](https://www.mdpi.com/1424-8220/22/21/8192/pdf)
 
 <a name="Use-Cases"/></a>
## 2.0 Use Cases
 - It can be used in the vegetable industries for non-destructive sorting and robotic harvesting.
 - It may also help children and visually impaired people in classifying fruits.
 - Helps to improve supermarket grocery self-checkouts.

<a name="system-architecture"/></a>
## 3.0 System Architecture
![image](https://user-images.githubusercontent.com/118173890/220200205-cc964e4b-51b1-4306-b3ae-a3d52933ead0.png)


<a name="Online-Platform-and-Software-used"/></a>
## 4.0 Online Platform and Software used

 - STM32CubeIDE \- advanced C/C++ development platform with peripheral configuration, code generation, code compilation, and debug features for STM32
 
 - Edge Impulse \- machine learning platform
 
 - STM32Cube.AI \- used to convert pre-trained neural networks into optimized code for STM32 microcontrollers


<a name="Built-and-train"/></a>
## 4.0 Built and train model using Edge Impulse

1. Download the vegetable image from the Kaggle website for training purposes.
   https://www.kaggle.com/datasets/misrakahmed/vegetable-image-dataset?resource=download
   
2. After creating a new project in Edge Impulse, click on upload data aquisition -> upload data to upload the training images. Click on the choose file and select 100 image from the dataset we downloaded before. Select the automatically split into training and testing to let the system split the images into 2 category of training and testing images. Select label and enter the image class type that we uploaded such as "beans". Upload the data after make sure everything is correct. Repeat the step until all the type of vegetable that we wanted to classify is uplodaed which in this case is another 2 class of "broccoli and cabbage".
   ![image](https://user-images.githubusercontent.com/118173890/220202714-969842c8-cc43-4d5c-9ca0-40b48646ec69.png)

3. Click on the impulse design seciton to start process out input images. The image is resize to 32x32 by fitting it to shortest axists. 
   ![image](https://user-images.githubusercontent.com/118173890/220204422-8db9b2ee-b168-46f9-9d5b-558962472c6c.png)

   A processing block to normalise the image and recuding color depth is added.
   ![image](https://user-images.githubusercontent.com/118173890/220204260-b96efca3-4577-4918-8082-10f62820f589.png)
   
   A pre-trained model from edge impulse is also added to reduce the training time in later stage.
   ![image](https://user-images.githubusercontent.com/118173890/220204380-87d54fda-f692-4f4e-9593-a11706abf5aa.png)


