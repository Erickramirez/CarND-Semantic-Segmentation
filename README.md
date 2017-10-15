[//]: # (Image References)
[image1]: ./images_samples/epoch05.png
[image2]: ./images_samples/epoch10.png
[image3]: ./images_samples/epoch15.png
[image4]: ./images_samples/epoch20.png
[image5]: ./images_samples/epoch25.png
[image6]: ./images_samples/epoch30.png
[image7]: ./images_samples/epoch35.png
[image8]: ./images_samples/epoch40.png
[image9]: ./images_samples/epoch45.png
[image10]: ./images_samples/epoch49.png
[image11]: ./images_samples/training_loss.png

# Semantic Segmentation
### Introduction
In this project, you'll label the pixels of a road in images using a Fully Convolutional Network (FCN).

### Setup
##### Frameworks and Packages
Make sure you have the following is installed:
 - [Python 3](https://www.python.org/)
 - [TensorFlow](https://www.tensorflow.org/)
 - [NumPy](http://www.numpy.org/)
 - [SciPy](https://www.scipy.org/)
##### Dataset
Download the [Kitti Road dataset](http://www.cvlibs.net/datasets/kitti/eval_road.php) from [here](http://www.cvlibs.net/download.php?file=data_road.zip).  Extract the dataset in the `data` folder.  This will create the folder `data_road` with all the training a test images.

### Start
##### Implement
Implement the code in the `main.py` module indicated by the "TODO" comments.
The comments indicated with "OPTIONAL" tag are not required to complete.
##### Run
Run the following command to run the project:
```
python main.py
```
**Note** If running this in Jupyter Notebook system messages, such as those regarding test status, may appear in the terminal rather than the notebook.

### Analisis on Training
This project is using a Fully Convolutional Network (FCN) and using [vgg 16](http://www.robots.ox.ac.uk/~vgg/research/very_deep/) in order to label  the pixels of a road in images. I tested with several combination of epochs, batch sizes, learning rates among otheres. 
* Here's a link to my [epoch30 video result](./videos/epoch_30.avi)
* Here's a link to my [final video result](./videos/final_result.avi)

This project implemented the folowing steps:
* load_vgg 
* layers 
* optimize 
* train_nn 
* the model decreases loss over time 
The  `main.py`  is recording in a csv file and printing the loss of the network. Here is a example of the [csv file generated](./summary_trainig_loss.csv)
and in the following image, we can check that the model decreases loss over time:
![alt text][image11]

* Final hyperparameters:
 * epochs = 50 (actually it could be lower, an example of epoch #31(it has epoch30 as reference because the index started at 0) has been included, you can update it if you want at the line 170.
 * batch_size = 4
 * learning_rate =   1e-4

#### Does the project correctly label the road?
During the training it is saving the image samples with the classification and it generates a video (every 5 epoch), The following images are examples using Fully Convolutional Network for Semantic Segmentation:
![alt text][image1] epoch 05
![alt text][image2] epoch 10
![alt text][image3] epoch 15
![alt text][image4] epoch 20
![alt text][image5] epoch 25
![alt text][image6] epoch 30
![alt text][image7] epoch 35
![alt text][image8] epoch 40
![alt text][image9] epoch 45
![alt text][image10] epoch 49 
