# CIFAR-10 Dataset with Noisy Labels

This dataset is based on the CIFAR-10 dataset and is designed for training machine learning models under two types of label noise: symmetric and asymmetric.

## Overview

The CIFAR-10 dataset is a popular benchmark for image classification tasks, consisting of 60,000 32x32 color images across 10 different classes. In this variant, we introduce label noise to simulate real-world scenarios where the labels assigned to data points may not always be accurate.

## Dataset Information

- **Dataset Name**: CIFAR-10 with Noisy Labels
- **Release Date**: 2023
- **Dataset Size**: Approximately 166MB (compressed)
- **Number of Samples**: 60,000
- **Number of Classes**: 10
- **License**: Not applicable (based on CIFAR-10 license)
- **Contact**: elhoussainianas8@gmail.com

## Label Noise Types

### 1. Symmetric Label Noise

In this type of noise, the correct label is flipped with a probability ε for the training data. This means that for each class, a fraction ε of the samples will have their labels changed to a random class label different from the correct one.

### 2. Asymmetric Label Noise

Asymmetric label noise introduces label flipping based on the noise level ε and the specific class. The label of training data instances belonging to certain classes is flipped with probability ε. The following class-to-class mappings are applied:

- **Truck** → **Automobile**
- **Bird** → **Airplane**
- **Deer** → **Horse**
- **Cat** → **Dog**
- **Dog** → **Cat**

## Data Description

The dataset is organized into three main directories: `ImageData`, `SymmetricNoiseData`, and `AsymmetricNoiseData`. It contains the following components:

### `ImageData`

- `train.pt`: A PyTorch tensor with shape (50,000, 3, 32, 32) representing the training images.
- `test.pt`: A PyTorch tensor with shape (10,000, 3, 32, 32) representing the test images.

### `SymmetricNoiseData` and `AsymmetricNoiseData`

These directories contain subfolders corresponding to different noise levels:

- `0`: No noise
- `10`: Noise level 10%
- `30`: Noise level 30%
- `50`: Noise level 50%
- `80`: Noise level 80%
- `90`: Noise level 90%

Within each noise level subfolder, you will find the following components:

- `train.pt`: A PyTorch tensor with shape (50,000) representing the noisy training labels with the specified noise level.
- `test.pt`: A PyTorch tensor with shape (10,000) representing the clean test labels.

This structure allows users to access images, training data, noisy labels, and test data with different levels of label noise.

Please update your README with this revised "Data Description" section to accurately reflect the structure of your dataset.

## Data Usage

Researchers and machine learning practitioners can use this dataset to develop and evaluate machine learning models under noisy label scenarios. This dataset can be used for various tasks, including image classification, label noise detection, and noise-resilient model training.

## Citation

If you use this dataset in your research or work, please consider citing the original CIFAR-10 dataset:

@techreport{Houssaini23cifar10,
    author = {Anas Houssaini},
    title = {CIFAR-10 with Symmetric and Asymmetric Noisy Labels},
    institution = {},
    year = {2023}
}

Please acknowledge this variant of the CIFAR-10 dataset when using it in your work.
