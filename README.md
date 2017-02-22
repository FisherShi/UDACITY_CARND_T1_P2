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

In terms of data augmentation, I generated additional training data by transforming the original images. Some examples below:

![alt text][image2]

## Model Architecture

The code for this step is contained in section _Step 3: Model Architecure_ of the IPython notebook.

In terms of model structure, I started with 1 conv layer + 1 fully connected layer (classification layer), and the best result was ~78% validation accuracy; then 2 conv layers + 1 FCL, best accuracy: ~83%; then 2 conv layers + 2 FCL, best accuracy: 97%. for filter size, I tried 33 and 55, for number of filters, I tried 16, 32, 64 for each conv layer; for number of nurons in the 1st fully connected layer, I tried 128 and 256. The final model has 2 conv layers, 1 flattern layer, and 2 fully connceted layers. 

To train the model, I used the following parameters after hours of fine-tuning:
* **Optimizer: AdamOptimizer**: I chose Adam Optimizer because it is usually faster than SGD, and less likely to get stuck in saddle points
* **batch size:500**: For batch size, I set it to the biggest batch possible to control the noise of training signal. if the batch size is too small, the training data tend to be biased for each batch. I believe a bigger batch size, with enough epoches, is better than a small one
* **epochs:100**: For epoch, I gradually increase the number of epoches until overfitting occurs
* **learning_rate = 0.0001**: For learning rate, I started with a very big number 0.01, then gradually decrease until there's improvements on accuracy 
* **dropout probabitlity = 0.7**: For dropout probability, I started with 1, and gradually decrease the value
