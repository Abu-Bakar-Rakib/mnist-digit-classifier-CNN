# MNIST Digit Classifier using CNN

A production-ready implementation of a Convolutional Neural Network (CNN) for handwritten digit classification using the MNIST dataset. This project demonstrates best practices in deep learning model development, including data preprocessing, model training, evaluation, and persistence.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Performance](#performance)
- [Dataset](#dataset)
- [Results](#results)
- [License](#license)

## Overview

This project implements a Convolutional Neural Network to accurately classify handwritten digits (0–9) from the MNIST dataset. The model achieves >98% test accuracy through an optimized architecture combining convolutional layers, pooling, and dense layers. The implementation uses TensorFlow and Keras for efficient training and inference.

## Features

- **High Accuracy**: Achieves >98% test accuracy on MNIST dataset
- **Efficient Architecture**: Optimized CNN with Conv2D, MaxPooling, Flatten, and Dense layers
- **Data Preprocessing**: Automatic normalization and augmentation
- **Model Persistence**: Save and load trained models in HDF5 format
- **Visualization**: Prediction visualization and performance metrics
- **Well-Documented**: Clear code structure with comprehensive comments
- **Reproducible**: Fixed random seeds for consistent results

## Requirements

- Python 3.8+
- TensorFlow 2.x
- Keras
- NumPy
- Matplotlib
- Pandas (optional)

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Abu-Bakar-Rakib/mnist-digit-classifier-CNN.git
   cd mnist-digit-classifier-CNN
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Train the model**
   ```bash
   jupyter notebook mnist_classifier.ipynb
   ```
   Run all cells to train the CNN model on the MNIST dataset.

2. **Evaluate predictions**
   The notebook includes visualization of model predictions on test samples.

3. **Save/Load the model**
   - Model is automatically saved as `mnist_model.h5` after training
   - Load existing model: `from tensorflow.keras.models import load_model`

## Model Architecture

The CNN architecture is composed of:

| Layer | Type | Parameters | Output Shape |
|-------|------|-----------|--------------|
| Input | - | - | (28, 28, 1) |
| Conv2D | 32 filters, 3×3 kernel | 320 | (26, 26, 32) |
| MaxPooling2D | 2×2 pool | - | (13, 13, 32) |
| Conv2D | 64 filters, 3×3 kernel | 18,496 | (11, 11, 64) |
| MaxPooling2D | 2×2 pool | - | (5, 5, 64) |
| Flatten | - | - | 1,600 |
| Dense | 128 units, ReLU | 204,928 | 128 |
| Dropout | 0.5 rate | - | 128 |
| Dense | 10 units, Softmax | 1,290 | 10 |

**Total Parameters**: ~225,000 trainable parameters

## Performance

### Training Configuration
- **Batch Size**: 64
- **Epochs**: 5
- **Optimizer**: Adam (default learning rate: 0.001)
- **Loss Function**: Categorical Crossentropy
- **Metrics**: Accuracy

### Results
- **Test Accuracy**: >98%
- **Training Time**: ~2-5 minutes (depending on hardware)
- **Model Size**: ~2.5 MB (HDF5 format)

## Dataset

**MNIST Handwritten Digits Dataset**

| Property | Value |
|----------|-------|
| Source | [Yann LeCun's MNIST](http://yann.lecun.com/exdb/mnist/) |
| Training Samples | 60,000 |
| Test Samples | 10,000 |
| Image Size | 28×28 pixels (grayscale) |
| Number of Classes | 10 (digits 0–9) |
| Pixel Range | 0–255 (normalized to 0–1) |

The dataset is automatically downloaded via Keras/TensorFlow on first run.

## Results

The trained model successfully:
- Classifies handwritten digits with >98% accuracy
- Generalizes well to unseen test samples
- Provides confidence scores for each prediction
- Visualizes correct and incorrect predictions for analysis

## Project Structure

```
mnist-digit-classifier-CNN/
├── mnist_classifier.ipynb    # Main training notebook
├── mnist_model.h5            # Trained model (generated after training)
├── README.md                 # This file
└── requirements.txt          # Python dependencies
```

## License

This project is licensed under the MIT License. See the LICENSE file for details.

---

**Author**: Abu-Bakar-Rakib  
**Last Updated**: June 2026
