
[//]: # (Image References)

[image1]: ./camera_cal/chessboard_undistorted.png "Undistorted Chessboard"
[image2]: ./camera_cal/test_img_undistorted.png "undistorted test image"
[image3]: ./test_img_binary.png "Binary Example"
[image4]: ./test_img_warped.png "Warp Example"
[image5]: ./test_img_polyfit.png "Fit Visual"
[image6]: ./test_img_output.png "Output"
[video1]: ./project_video.mp4 "Video"


# UDACITY Traffic Sign Classifier

## The Goal of this Project

The goal of this project is to use deep neural networks and convolutional neural networks to classify traffic signs. 

## Summary

In summary, I complete this project by:  

1. Explore, summarize and visualize the data set
2. Design, train and test a model architecture
3. Use the model to make predictions on new images
4. Analyze the softmax probabilities of the new images

The project repo from Udacity can be found [here](https://github.com/udacity/CarND-Traffic-Sign-Classifier-Project)

Data set used in this project is from [German Traffic Sign Dataset](http://benchmark.ini.rub.de/?section=gtsrb&subsection=dataset). 

## Data Set Summary & Exploration

The code for this step is contained in section _Step 1: Dataset Exploration_ of the IPython notebook. Summary of the dataset:

* Number of training examples = 39209
* Number of testing examples = 12630
* Image data shape = (32, 32)
* Image data size flat= 1024
* Number of classes = 43

Here is an exploratory visualization of the dataset. Here is a histogram showing the distribution of classes:

