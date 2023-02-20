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

3. Click on the impulse design seciton to start process out input images. The image is resize to 32x32 by fitting it to shortest axists. A processing block to normalise the image and recuding color depth is added. A pre-trained model from edge impulse is also added to reduce the training time in later stage.
![image](https://user-images.githubusercontent.com/118173890/220204536-901c424f-cbe5-4625-875d-56d901f2c973.png)

4. Click on image under impulse design section. Change the color depth to greyscale and save the parameter. 
   ![image](https://user-images.githubusercontent.com/118173890/220204655-ab0fb9d1-6a30-43f0-bc83-9c59537e4520.png)
   Afterwards, it click the genetate feature to generate the feature of the 3 different types of vegetabel image we uploaded.
   ![image](https://user-images.githubusercontent.com/118173890/220205084-6b3579e3-73e5-48c2-a131-8e0e58fba992.png)

5. Go to the next section "transfer learning" under the same impulse design section, change the nural network setting to 100 training cycle, 0.0005 learn rate and 60% of variation set size. We need to make sure the trainign cycle is high enough and the learn rate is low to make sure we can get get to the bottom of the loss function and having a much higher accuracy as possible. Then click on start training to start training the model. After finish training, we can observe the accuracy and loss of our model from the training result. 
   ![image](https://user-images.githubusercontent.com/118173890/220205644-89dc05d0-a876-4dea-a0ba-e38a3aae12c0.png)

6. After finish training
