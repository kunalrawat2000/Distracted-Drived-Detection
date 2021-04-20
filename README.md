# Distracted-Driver-Detection
The objective of this work is to successfully predict the likelihood of what a driver is doing in each of the pictures in the dataset.

## Motivation
  According to WHO 1.3 million people die every year in road accidents.In many cases it is been reported that cause of accidents were due to driver been distracted.<br>
  There are many advanced systems developed by big organizations like Tesla and Google.So our main motive to build an efficient, robust, cost-effective and fast model, which can monitor the driver’s actions.<br>

## Dataset
Dataset For this project taken from Kaggle – (State Farm Distracted Driver Detection).<br>
The dataset contains 22424 images as train data and 79726 images as test data.<br><br>

The 10 classes to predict are:
- c0: safe driving
- c1: texting - right
- c2: talking on the phone - right
- c3: texting - left
- c4: talking on the phone - left
- c5: operating the radio
- c6: drinking
- c7: reaching behind
- c8: hair and makeup
- c9: talking to passenger


![dataset ddd](https://user-images.githubusercontent.com/54204821/115225562-d8ecdf00-a12b-11eb-8dfa-880e593a93bc.png)


## Our work
**Approaches used** – Feature Extractor and Fine-Tuned VGG16.<br>
  1. **Feature Extractor** - Feature extraction involves reducing the number of resources required to describe a large set of data.<br>
        - In this we have used the n-1 layers of VGG16 to predict the last layer of it using the flattened image vector
        - The last layer thus achieved is a dense feature representation for a particular image
        - Passing this layer feature through a Global Average Pooling Layer and a further dense softmax layer for each of 10 classes

  2. **Fine-Tuned VGG16** - Fine-tuning takes a model that has already been trained for a particular task and then fine-tuning or tweaking it to make it perform a second similar task.<br> 
        - In this  we are going to load a VGG16 model, without top Fully connected layers, with its trained weights
        - Then we are going add Fully Connected Layers on top of Global Average Pooling layer with  3 Dense layers and 2  dropout layers on top of VGG16 CNN model to avoid overfitting

## Winner(Accuracy)
1. Finetuning - 97%
2. Feature Extraction - 90%

## Result/Output
Used finetuned vgg16 for prediction since the accuracy is higher.
![ezgif com-gif-maker](https://user-images.githubusercontent.com/54204821/115232674-a2679200-a134-11eb-8cac-68e01cfa5b02.gif)
<br>
**Note**:- The gif is not much clear because there is limit of gif in github that is why i reduced the size and the video is not much clear.



