# EmoPlayer
Detecting emotions

 Collecting data

    Facial expression detection in Fisherface works with the help of trained models. Reason behind this is to allow user to take dataset according to their use. Suppose if we take a huge amount of dataset of around 25-30k it will give nice accuracy no doubt but if the situation is like that the user of the devices are a few people. Now in such condition if we take some precise dataset with around 400-450 images as input releted to the user then it will also give good accuracy with the benefit of less amount of dataset and less storage on memory to operate. As well as small memory of data give output fast which result in quick response time. Here we first tried with Cohn-Kanade dataset then we made some classification in the as our need make it to train our model.
   
 Loading and saving trained model

For training, We have used Fisherface method of cv2 library.

 
For training data model we have make a python code which grab all the classified images from folders and map it with it’s emotion. These data we at an instance stored in dictionary and then use .train method to train model.

 
To save the model for later use we have implemented .save method.
   
Now at the detection time first we have load model in memory using .read method.
 
Prediction of result is based on the prediction and confidence value which .predict method return.
 
Haarcascade model

Haarcascade model is precise face detection trained model which is provided by Open-cv. It return the co-ordinates in terms of (x, y) at (left, bottom) of face frame and it’s width and height from those co-ordinates.
 
As here in the .detectMultiScale() method it is capable of detect multiple faces and it return an array of all the faces(co-ordinates) as an element.   
The arguments has set according to the threshold what we need for our checking purpose. We have set it such like it doesn’t affect our model accuracy.

Result Calculation
In our model we have not stick on one image for testing, While the code will run it will take around 10 images in a short time(1-2 sec) and for all those images it will compute result and according to the average value of that it will give result. Apart from that we have make two codes one work on single face at a time while another work with multiple faces in the image.


Machine Learning

 Fisherface ML algorithm
    Fisherface algorithm is an algorithm which work on the basis of LDA and PCA concepts. Linear discriminant analysis (LDA) is a supervised Learning method of machine learning. Now supervised Learning is that where we use such data whose answer is also given to the model to learn it. It work on the concept of dimensionality reduction. Which reduce the execution time among classification.
Principal Component Analysis (PCA) is a one kind of conversion from correlated variables to uncorrelated in the form of mathematical values.
It is mostly used for the observing data and from that by some probabilistic calculation generate models. The flow of Fisherface is like it takes classified images then it will reduce the dimension of the data and by calculating it’s statistical value according the given categories it stores numeric values in .xml file. While prediction it also calculate the same for given image and compare the value with the computed dataset values and give according result with confidence value.  

 Resizing images
    Whatever the image we have chosen for dataset it mostly related to the size which can give an precise output. The size is chosen such like the model can able to easily distinguish face from image by haarcascade model. And the size what we get from real time scan is not always same as data (very less difference) so, We resize it to the exact model data size. In our case we have chosen 350*350.
 
Here In this method, we have implemented the cropping of image by given parameters of haarcascade by clahe_image[] and use of cv2’s method .resize() to the given size. Finally, We have stored those images in dictionary and after some count(=10) take it to check result.

 Gray scaling images

It was the need for the method and because of it’s contrast and shaded face, it result in benefit for algorithm to get output.

Face detection

 
As the given in the code grab_face() methods uses to get the images and do all operation and finally return cropped ,grayed face value in dictionary.


Train and predict methods
 
This code is use to get prediction and confidence value for given amount of image. Then get the max function with obtained output and final result is shown to the user.



Playing music

 Detected emotions
We have implemented the linking of python with javascript through eel library. Which provide us the privilege to access python methods from js as well as vice versa. Here the striating flow will be in python code as the library is implemented in python then it transfer the control to html, JS. And according to the result we show emoticons.
     
   Sad     happy  angry neutral
According to which we can classify emotion directory for playing song we have chosen this 4 emotions.

Methods for playing songs

In JavaScript file we have implemented too much methods for the switching of song.
1.	Queue
2.	Based on Emotion
3.	Random
In the first one as queue works it has been implemented. In second one we call python code to get emotion from user’s facial expression and according to that chosen next song which is also randomly and played it. In third one we directly used random function and all the methods are dynamic it can handle as change in number of songs accordingly.

 HTML, CSS and JS concepts for online music player.
As we know the css give a great look to communicate and through JS we can interact with user and not look like complicated program run at console and it also give user privilege to choose any song to play.
 



