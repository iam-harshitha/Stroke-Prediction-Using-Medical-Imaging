# Stroke-Prediction-Using-Medical-Imaging

## Problem statement - 
The main goal of the project is to classify the strokes in different parts of brain namely glioma, meningioma, pituitary, no tumer.
## Dataset - https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset
This dataset contains 7023 images of human brain MRI images which are classified into 4 classes: glioma - meningioma - no tumor and pituitary.

## libraries 
- os
- numpy
- tenserflow
- keras
  
## Preprocessing
- imported the data into jupyter notebook
- Resized the image to (256,256)
- Initialized ImageDataGenerator for training data with data augmentation
- Initialize ImageDataGenerator for testing data with only rescaling
- Load training data and testing data from the directory, specifying the target image size and batch size, class_mode, color_mode.

## Model
- Initialize a Sequential model with input shape(256,256,1), Conv2D(2 input layers), MaxPooling2D, GlobalAveragePooling2D for flattening the output, Dense(1 hidden layer) with 128 neurons and relu activation function, Dropout to prevent overfitting Dense(output layer) with softmax activation function and 4 classes.
- complie model using Adam optimizer, categorical_crossentropy, accuracy
- getting the model architecture.

## Model Training
- Early stopping to stop training when validation accuracy doesn't improve
- train the model using the training data with 30 epochs, test_generator as validation_data, 1 verbose
- save the model in keras format

## Model Evaluation
- load the model saved in keras format
- load the image and preprocess
- make the prediction
- output the prediction
