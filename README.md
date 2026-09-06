# CIFAR10-CNN-Image-Classification
CNN based image classification on the CIFAR10 dataset using PyTorch, including data preprocessing, model training, validation, and model evaluation.

## Project Overview
This project implements a CNN to classify images from the CIFAR-10 dataset into 10 different categories.
The project covers the complete deep learning workflow:
* Dataset loading
* Image preprocessing
* Data normalization
* CNN model building
* Model training
* Validation
* Model evaluation
* Training and validation loss analysis

## Dataset

The project uses the **CIFAR-10 dataset**, which contains:
* **50,000 training images**
* **10,000 test images**
* Image size: **32 × 32 pixels**
* **3 color channels (RGB)**
* **10 classes**

### Classes
1. Airplane
2. Automobile
3. Bird
4. Cat
5. Deer
6. Dog
7. Frog
8. Horse
9. Ship
10. Truck

The dataset is automatically downloaded using `torchvision.datasets.CIFAR10`.

## Technologies Used

* Python
* PyTorch
* Torchvision
* Matplotlib

## Data Preprocessing

The images are converted into PyTorch tensors using `ToTensor()` and normalized using:

transforms.Normalize(
    (0.5, 0.5, 0.5),
    (0.5, 0.5, 0.5)
)

A separate mean and standard deviation value is provided for each of the three RGB channels.

## CNN Architecture

The model consists of three convolutional blocks followed by fully connected layers.

| Layer           | Details                                  |
| --------------- | ---------------------------------------- |
| Conv Layer 1    | 3 → 32 channels, 3×3 kernel, padding=1   |
| ReLU            | Activation function                      |
| Max Pooling     | 2×2                                      |
| Conv Layer 2    | 32 → 64 channels, 3×3 kernel, padding=1  |
| ReLU            | Activation function                      |
| Max Pooling     | 2×2                                      |
| Conv Layer 3    | 64 → 128 channels, 3×3 kernel, padding=1 |
| ReLU            | Activation function                      |
| Max Pooling     | 2×2                                      |
| Flatten         | Converts feature maps into a vector      |
| Fully Connected | 2048 → 256                               |
| ReLU            | Activation function                      |
| Output Layer    | 256 → 10                                 |

The final layer produces **10 output values**, corresponding to the 10 CIFAR-10 classes.

## Training Configuration

* **Batch Size:** 64
* **Epochs:** 10
* **Optimizer:** Adam
* **Loss Function:** Cross-Entropy Loss

## Training Results

The model was trained for 10 epochs and both training and validation loss were monitored.

| Epoch | Training Loss | Validation Loss |
| ----: | ------------: | --------------: |
|     1 |        1.4040 |          1.1077 |
|     2 |        0.9611 |          0.9102 |
|     3 |        0.7623 |          0.7948 |
|     4 |        0.6374 |          0.7371 |
|     5 |        0.5271 |          0.7506 |
|     6 |        0.4318 |          0.7256 |
|     7 |        0.3462 |          0.8435 |
|     8 |        0.2716 |          0.8798 |
|     9 |        0.2082 |          0.9535 |
|    10 |        0.1651 |          1.0231 |

The training loss continuously decreases, while the validation loss begins increasing after around epoch 6. This indicates that the model starts showing signs of **overfitting** during the later epochs.

## Loss Visualization

The notebook includes a visualization of the training and validation loss across epochs.

This helps analyze how the model performs during training and identify potential overfitting.

## Model Evaluation

The project includes validation during training to monitor the model's performance on unseen validation data.
The training and validation losses are compared to understand the model's learning behavior and identify signs of overfitting.

## What I Learned

Through this project, I gained practical experience with:

* CNN architecture
* Convolutional layers and feature extraction
* ReLU activation
* Max pooling
* Fully connected layers
* Image preprocessing and normalization
* Cross-Entropy Loss
* Adam optimization
* Training and validation
* Overfitting analysis
* PyTorch model implementation
* Model Evaluation

## Future Improvements

The project can be further improved by adding:

* Test-set accuracy
* Per-class accuracy
* Confusion matrix
* Sample image predictions
* Data augmentation
* Dropout
* Batch normalization
* Early stopping
* Hyperparameter tuning
* Comparison with deeper CNN architectures
