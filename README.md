Image Caption Generator (Deep Learning)

A deep learning model that generates natural language captions for images.
The model performs well on outdoor photos, people, and dogs, but struggles with indoor scenes and food images due to dataset limitations.

Project Overview

Input: Image
Output: Text description (caption)

The model takes an image and produces a sentence describing its visual content.

Strengths

The model performs well on:

Outdoor scenes (parks, beaches, snow)

Photos containing people and dogs

Common activities (running, playing, standing)

Simple, well-lit images

Limitations

The model performs poorly on:

Indoor rooms

Food images

Aerial or top-down views

Complex or cluttered scenes

Setup and Installation
Step 1: Install Requirements
pip install tensorflow numpy pandas matplotlib pillow nltk requests tqdm

Data Preparation

You need:

A folder containing images

A captions file in CSV format (image,caption)

Upload the dataset to Google Drive (recommended for Colab)

Folder Structure
caption_data/
├── Images/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
└── captions.txt

Example captions.txt
image,caption
image1.jpg,a dog running in the park
image2.jpg,a man wearing a red shirt

Training the Model
Step 1: Open Google Colab

Upload your dataset ZIP file to Google Drive.

Step 2: Set Dataset Path

Update the dataset path in the training notebook:

zip_path = '/content/drive/MyDrive/caption_data.zip'

Step 3: Run Training

Run all cells in the notebook from top to bottom.

What Happens During Training

Images and captions are loaded

Image features are extracted using the Xception model

The captioning model is trained

Early stopping is applied

The best model is saved automatically as:

best_model.keras


Estimated training time: 1–2 hours (depending on dataset size and GPU).

Using the Model (Inference)
Required Files

After training, keep the following files:

best_model.keras – trained model

tokenizer.pkl – converts words to numbers

image_features.pkl – optional (can be deleted after training)

Caption Generation Process

The model can generate captions from:

Local image files

Image URLs

Inference steps:

Load the trained model and tokenizer

Load an image

Extract image features

Generate the caption word by word

Display the image with the predicted caption

Important Training Parameters
batch_size = 32      # Number of images per batch
epochs = 50          # Maximum training epochs
patience = 3         # Early stopping patience
max_length = 38      # Maximum caption length
vocab_size = 10000   # Maximum vocabulary size

Code Flow Overview
Training Pipeline

Load images and captions

Clean and preprocess text

Extract image features using Xception

Build the vocabulary

Build the encoder–decoder model

Train the model

Save the best-performing model

Inference Pipeline

Load the trained model and tokenizer

Load an image from file or URL

Extract image features

Predict the caption sequence

Display the final caption

Common Issues and Solutions
Issue	Solution
Out of memory	Reduce batch_size to 16
Training takes too long	Reduce epochs to 20
Captions cut off early	Increase max_length to 50
Summary

This project implements an image captioning system that:

Takes images as input

Produces natural language descriptions

Performs best on outdoor scenes with people and dogs

Requires more diverse data to improve performance on indoor and food images

Usage

Train the model on your own dataset or use a pretrained model

Load the trained model and tokenizer

Pass an image to the caption generation function

Receive a descriptive caption
