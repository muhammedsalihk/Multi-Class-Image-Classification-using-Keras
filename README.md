# Multi Class Image Classification using Keras

## Introduction
In image classification, we train a deep neural network to predict the labels/class of on what the image contains. In this project, we are building a model to classify the objects in the CIFAR-10 dataset which contains 50000 training images from 10 different classes.

## Methodology
The dataset contains 50000 numbered images (from 1 to 50000) and a csv file with information on the class that each image belongs to. In keras, image data can be easily setup and also augmented for classification problem using the ImageDataGenerator class if the images are stored in the following format.

![Image 1](https://github.com/muhammedsalihk/Multi-Class-Image-Classification-using-Keras/blob/master/Images/Image%201.png)

So the first step in the project was to create three directories for the train, test and dev set in the required format. This was done using a python script that extracted the class of the image from the dataframe (created using the csv file) and then arranging the files in the required directory structure using packages like glob2 and shutil.

Following that multiple neural network architectures were tried and tuned for performance based on the accuracy score obtained on the train and validation sets. Some architectures were based on pretrained VGG-16 and VGG-19 models, and some were fully custom built. The evaluation metric used was accuracy score. And based on the performance on the test and val sets, we could identify the issues that our current model was facing (say high bias or high variance), and appropriate additions were made. Say when there was a high bias problem, a deeper or complex neural network had to be used, and regularisation or dropout layers had to be used when the problem was high variance.

Finally, the best NN architecutre was selected based on its performance on the test set.

## Results
Out of the models we tried, the network that gave the best performance and its accuracy score on the test, train and dev sets are given below.

![Model](https://github.com/muhammedsalihk/Multi-Class-Image-Classification-using-Keras/blob/master/Images/Model.png)

**Model Performance**

| Set  | Score |
| ------------- | ------------- |
| Test  | 0.823  |
| Train | 0.948 |
| Val   | 0.806  |

We can see that the model is having a high variance problem. There is definitely a scope for further improvement in the performance by using techniques like data augmentation, L2 regularisation, dropout etc.
