# Custom Sing Language Detection Tutorial

## Tutorial Overview

This tutorial offers a formal walkthrough of the entire process, beginning with the acquisition and preprocessing of data, followed by the training of a machine learning model, and concluding with real-time testing. It delves into the meticulous process of gathering hand gesture data through a webcam, extracting hand landmarks via MediaPipe, and meticulously preparing the data for model training. It then demonstrates the model training stage, where a Random Forest Classifier is educated on the collected data. Finally, the tutorial concludes by demonstrating how to deploy the trained model, enabling real-time testing using your computer's webcam.

## Installation

You'll need a working installation of Python to run the code examples and scripts. The code in this tutorial is written in Python 3.11.4.
Install required libraries using pip:

```
pip install -r requirements.txt
```

## Data Collection 
Create a folder named 'data' and ensure that it is in the same directory as your project.

Set the 'number_of_classes' variable in 'collect_data.py' to the desired number of hand gestures you intend to create and detect:
```
number_of_classes = 4
```
Run 'collect_data.py,' and when you are ready, press 'q' on your keyboard to capture the data using your webcam while using your hand to create the necessary gestures for the signs you want to generate.

## Create Dataset

"Run 'create_dataset.py' to generate the dataset that will be used for training the model. 
This process will create the 'data.pickle' file. The 'data.pickle' file is a data storage file that contains hand gesture data and their corresponding labels.  The 'data.pickle' file includes information about hand gestures and the labels indicating which class they belong to. This file represents preprocessed data ready for model training. 

## Train Dataset

Execute 'train.py' to initiate model training using the 'data.pickle' file generated in the previous step.
This process will create the 'model.p' file. The 'model.p' file is a model file that contains the trained version of the model. This file stores the learned model parameters and weights acquired during training. The trained model is used for recognizing hand gestures and is applied in real-time hand gesture recognition tasks. In essence, this file preserves the learned knowledge of the model and allows it to be used at a later time.

## Test Model

Before running 'test.py,' modify the code to adapt the names of the classes you created to your project, like this:

```
labels_dict = {0: 'gesture1', 1: 'gesture2', 2: 'gesture3', 3: 'gesture4'}
```
This way, you can customize the 'labels_dict' dictionary to match the names of the gestures you want to recognize in your project.
Finally, run 'test.py' to test the model.

This code performs real-time hand gesture recognition using a trained model. It identifies landmarks on the hand using MediaPipe on the live camera feed, then makes predictions using these landmarks. The model determines the hand gesture and displays the result on the screen. Users can terminate the process by pressing the 'q' key.