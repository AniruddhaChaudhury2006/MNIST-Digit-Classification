# Handwritten Digit Recognition using MNIST

This repository contains a Python project that demonstrates a simple handwritten digit recognition model built using TensorFlow and Keras. The model is trained on the classic MNIST dataset and is capable of accurately classifying handwritten digits from 0 to 9.

## Table of Contents

- [Introduction](#introduction)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Setup](#setup)
- [Usage](#usage)
- [Results](#results)
- [Files](#files)

## Introduction

Handwritten digit recognition is a fundamental task in computer vision and machine learning. This project provides a clear and concise example of how to implement a neural network for this task, from data loading and preprocessing to model training, evaluation, and prediction on new images.

## Dataset

The project utilizes the **MNIST dataset**, which is widely recognized as the 'hello world' of deep learning for computer vision. It comprises:

- **60,000 training images**: Used to train the neural network.
- **10,000 testing images**: Used to evaluate the model's performance on unseen data.

Each image in the dataset is a 28x28 pixel grayscale image of a handwritten digit.

## Model Architecture

The neural network architecture used in this project is a `Sequential` model from Keras, consisting of:

1.  **`keras.layers.Flatten(input_shape=(28,28))`**: This layer transforms the 2D 28x28 pixel images into a 1D array of 784 pixels, which can be fed into the dense layers.
2.  **`keras.layers.Dense(50, activation='relu')`**: A fully connected hidden layer with 50 neurons and a Rectified Linear Unit (ReLU) activation function.
3.  **`keras.layers.Dense(50, activation='relu')`**: Another fully connected hidden layer with 50 neurons and a ReLU activation function.
4.  **`keras.layers.Dense(10, activation='sigmoid')`**: The output layer, comprising 10 neurons (one for each digit from 0 to 9) with a Sigmoid activation function. The Sigmoid function is used here to output probabilities for each class.

The model is compiled with the `adam` optimizer, `sparse_categorical_crossentropy` as the loss function (suitable for integer labels), and `accuracy` as the evaluation metric.

## Setup

To run this program, you will need to have Python installed along with the following libraries:

-   `numpy`
-   `matplotlib`
-   `seaborn`
-   `opencv-python` (`cv2`)
-   `tensorflow`
-   `Pillow` (`PIL`)

You can install these dependencies using `pip`:

```bash
pip install numpy matplotlib seaborn opencv-python tensorflow Pillow
```

## Usage

1.  **Clone the repository** (if applicable) or download the notebook file.
2.  **Open the Jupyter Notebook/Google Colab**: The code is structured within a Jupyter Notebook or Google Colab environment.
3.  **Execute cells sequentially**: Run each code cell in order to:
    -   Load necessary libraries.
    -   Load and preprocess the MNIST dataset (`X_train`, `Y_train`, `X_test`, `Y_test`). Images are normalized by dividing pixel values by 255.
    -   Define, compile, and train the neural network model.
    -   Evaluate the model's performance on the test set.
    -   Visualize the confusion matrix to understand prediction accuracy per digit.
    -   Demonstrate prediction on a custom image. You can specify the path to your own handwritten digit image (`/content/MNIST_digit.png` is used as an example in the notebook). The image will be preprocessed (converted to grayscale, resized to 28x28, and normalized) before prediction.

### Example Prediction

The notebook includes a section where you can input the path to an image file (e.g., `MNIST_digit.png`) to see how the trained model predicts the digit within that image. Make sure the image is accessible in the environment where you run the notebook.

## Results

Upon training for 10 epochs, the model typically achieves an accuracy of approximately **97-98%** on the test dataset. A confusion matrix is generated to provide a detailed breakdown of correct and incorrect classifications for each digit.

## Files

-   `MNIST_digit.png`: An example image file used for demonstration of single image prediction.
