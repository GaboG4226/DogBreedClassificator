# Dog Breed Classificator

## Table of Contents
1. [Description](#description)
2. [Getting Started](#getting_started)
	1. [Requirements installation](#installation)
	2. [Folder structure and files/directories explanation](#folder_structure)
	3. [Instructions](#instructions)
3. [Project results](#projectresults)
4. [Authors](#authors)
5. [Acknowledgement](#acknowledgement)

<a name="descripton"></a>
## Description

The project aim is to develop a Convolutional Neural Netowrk (CNN) to classify between 133 different dog breeds. Additionally, a pipeline is set to first detect a human or a dog using pre-trained neural networks to then detect the dog breed or the dog breed the human most resembles to. The training of the neural network is enhanced with transfer learning to get the most possible accurate network without spending a lot of time.

A blog post on the development of this project can be found in my [Medium Dog Breed Classification Post](https://medium.com/@gabogarcia4225/classification-of-dog-breeds-using-a-custom-cnn-model-and-transfer-learning-b6d985926a3a)

It is important to mention that this repo will only have few commits as the project was developed in an environment with GPU provided by Udacity :) 

<a name="getting_started"></a>
## Getting Started

<a name="installation"></a>
### Requirements installation

The requierements for this project can be installed with the line of code provided next:

```
pip install -r requirements.txt
```
<a name="folder_structure"></a>
### Folder structure and files/directories explanation
```
C:.
│   dog_app.ipynb - jupyter notebook with all the project development
│   extract_bottleneck_features.py - functions used to extract bottleneck features before predictions
│   README.md
│   requirements.txt - file to install
│
├───bottleneck_features - folder with all the bottleneck features used for transfer learning
│ 
├───data - folder with all the data for training
│   ├───dog_images - folder with all the training images of dog breeds separated by subfolders
│   └───lfw - folder with human images used for checking accuracy detecting faces
│
├───haarcascades - folder with the files used for face detection with cv2 library
│
├───images - images used within the jupyter notebook in several markdown blocks
│       
├───test_images - images used for testing the CNN
│   
└───saved_models - weights of models that got the best accuracy and minimum loss value
```
It is important to mention that the data folder is not in this repo as the data is heavy, if wanted to download the training dataset you could do it by following the below subsection.

<a name="instructions"></a>
### Instructions to run the complete jupyter notebook starting from training
1. Clone the repository and navigate to the project's root directory in the terminal
2. Download the [dog dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/dogImages.zip). Unzip the folder and place the three files (test, train and valid) in the cloned repository in the folder ```data/dog_images```. If one of these folders does not yet exist, please create it manually. 
3. Download the [human dataset](https://s3-us-west-1.amazonaws.com/udacity-aind/dog-project/lfw.zip). Unzip the folder and place it in the cloned repository in the folder ```data/lfw```. If one of these folders does not yet exist, please create it manually. 
4. Download the [best models](https://drive.google.com/drive/folders/158NkcmtvT2TMLUv7NTP1npRE3Nf0cHGn?usp=sharing) from the google drive folder to run the initial CNN created
5. Start the notebook ```dog_app.ipynb``` and start running the blocks. 

Note: If don't want to tun the notebook from the training, just run all the functions needed and load the weights of the final model in Steps 5,6 and 7.

<a name="projectresults"></a>
### Project results

The CNN model created had a 80.02% accuracy and a final loss function of 0.75. During training it was observed how the loss function and validation loss function values both decreased and have really close values between each other indicating that the model was generalizung well for validation data. That was a good indication that the model was not overfitting nor underfitting and was learning the underlying patterns in the data.

When testing the model, it was observed it worked really well by identifying the dog breeds and resemblance to human faces, where if it is wanted to have more precision several things could be done:

1. Use data augmentation techniques to get more features during training. In the specific case of the french bulldog I would propose using image changes that allows to differentiate between the two breeds
2. Add more dense layers to get more high level features and see if this helps
3. Use a more robust pretrained network to get more bottleneck features

<a name="authors"></a>
## Authors

* [Gabriel Garcia](https://github.com/GaboG4226)

<a name="acknowledgement"></a>
## Acknowledgements

* [Udacity](https://www.udacity.com/) for providing an amazing Data Science Nanodegree Program, I really enjoyed it so much!

