# MNIST Classification: Perceptron vs ANN vs CNN

## Overview

This project implements and compares three different neural network
approaches for handwritten digit classification using the MNIST dataset:

1. Perceptron
2. Artificial Neural Network (ANN)
3. Convolutional Neural Network (CNN)

The objective is to understand how different neural network architectures
perform on image classification tasks and why CNNs are particularly
effective for image data.

## Dataset

The MNIST dataset contains grayscale images of handwritten digits from
0 to 9.

Each image has a size of:

28 × 28 pixels

The dataset used in this project contains:

- 20,000 training images
- MNIST test images
- 784 pixel features per image
- 10 classes (digits 0–9)

## Models Implemented

### 1. Perceptron

Architecture:

Input Image
→ Flatten
→ Dense(10)
→ Softmax

The Perceptron is used as a simple baseline model.

### 2. Artificial Neural Network

Architecture:

Input
→ Flatten
→ Dense(250, ReLU)
→ Dense(128, ReLU)
→ Dense(64, ReLU)
→ Dense(10, Softmax)

### 3. Convolutional Neural Network

Architecture:

Input
→ Conv2D(32)
→ MaxPooling2D
→ Conv2D(64)
→ MaxPooling2D
→ Flatten
→ Dense(128, ReLU)
→ Dropout(0.5)
→ Dense(10, Softmax)

## Preprocessing

The pixel values are normalized from:

0–255

to:

0–1

using:

X = X.astype('float32') / 255.0

The images are reshaped from 784 pixels into:

28 × 28

For the CNN, an additional channel dimension is added:

28 × 28 × 1

The labels are converted to one-hot encoded vectors using
`to_categorical()`.

## Training

The models are trained for:

- Epochs: 5
- Batch size: 32

Optimizers:

- Perceptron: SGD
- ANN: Adam
- CNN: Adam

Loss function:

Categorical Cross-Entropy

Evaluation metric:

Accuracy

## Results

The models were compared using:

- Training accuracy
- Validation accuracy
- Training loss
- Validation loss
- Test accuracy
- Confusion matrix
- Prediction confidence

The CNN achieved the best overall performance, reaching approximately
99% validation accuracy.

The results demonstrate the advantage of convolutional architectures
for image classification.

## Visualizations

The notebook includes:

- Training vs validation accuracy
- Training vs validation loss
- Model accuracy comparison
- Prediction confidence comparison
- Confusion matrices

## Technologies Used

- Python
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- TensorFlow / Keras
- Google Colab

## How to Run

1. Clone the repository.
2. Open `CNN.ipynb` in Google Colab or Jupyter Notebook.
3. Download/place the required MNIST CSV files in the `data` directory.
4. Run the notebook cells sequentially.

## Key Learning

The experiment demonstrates the progression:

Perceptron → ANN → CNN

and shows how CNNs can exploit the spatial structure of images through
convolution and pooling operations.
