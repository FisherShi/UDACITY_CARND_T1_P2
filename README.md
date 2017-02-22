[image1]: ./data_summary.png "data summary"
[image2]: ./data_augmentation.png "data augmentation"
[image3]: .test_result.png "test result"
[image4]: .test_result2.png "test on new images"


# UDACITY Traffic Sign Classifier

## The Goal of this Project

The goal of this project is to use deep neural networks and convolutional neural networks to classify traffic signs. 

## Summary

In summary, I complete this project by:  

1. Explore, summarize and visualize the data set
2. Preprocess and generate augmented data
3. Design, train and test a model architecture
4. Use the model to make predictions on new images

The project repo from Udacity can be found [here](https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project)

Data set used in this project is from [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). 

## Data Set Summary & Exploration

The code for this step is contained in section _Step 1: Dataset Exploration_ of the IPython notebook _Traffic_Signs_Recognition.ipny_. Summary of the dataset:

* Number of training examples = 39209
* Number of testing examples = 12630
* Image data shape = (32, 32)
* Image data size flat= 1024
* Number of classes = 43

Here is an exploratory visualization of the dataset showing the histogram of classes:

![alt text][image1]

## Preprocesing & Data Augmentation

The code for this step is contained in section _Step 2: Preprocesing & Data Augmentation_ of the IPython notebook.

Techniques used to preprocess the data:
* Use label binarize function from sklearn to one-hot encode the y_train; 
* Turned colored images into grayscale by converting the images to YUV channels and only leave the Y channel (the paper provided for this project suggests that although counter-intuitive,the grayscal images can provide better results than the RGB images); 
* Normalized the grayscale images to prevent over compensating a correction in one weight dimension while undercompensating in another; 
* Reshaped X_train, X_test to flatten the images
