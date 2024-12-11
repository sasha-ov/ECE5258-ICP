# Human Activity Recognition Using Neural Networks

This repository contains the implementation of a project focused on **Human Activity Recognition (HAR)** using various deep learning architectures, including **CNNs**, **LSTMs**, **CNN-LSTMs**, and **Temporal Convolutional Networks (TCNs)**. The project compares the performance of these models on the **Human Activity Recognition Using Smartphones Dataset**.

---

## 📂 Dataset

The dataset used in this project is the **Human Activity Recognition Using Smartphones Dataset**, which includes:
- Accelerometer and gyroscope signals recorded at 50 Hz from 30 participants performing six activities:
  1. Walking
  2. Walking Upstairs
  3. Walking Downstairs
  4. Sitting
  5. Standing
  6. Laying

### Dataset Link:
[UCI HAR Dataset](https://archive.ics.uci.edu/ml/datasets/human+activity+recognition+using+smartphones)

### Preprocessing:
- The dataset was loaded as raw sensor data without feature extraction.
- Data was standardized and split into training, validation, and testing sets.

---

## 🧠 Models

This project evaluates the following models:

### 1. **Baseline Model: Support Vector Machine (SVM)**
- Features extracted: Time and frequency domain characteristics.
- Multiclass classification using the One-vs-All strategy.
- Accuracy: **96%**
- Weakness: Struggles with static activities (e.g., sitting: 88% recall).

### 2. **Convolutional Neural Network (CNN)**
- 3 convolutional layers with MaxPooling and Dropout.
- Final dense layer with 128 neurons and softmax activation.
- Accuracy: **92.16%**
- Strength: Handles short-term dependencies efficiently.

### 3. **Long Short-Term Memory (LSTM)**
- 2 LSTM layers with Batch Normalization and Dropout.
- Fully connected dense layer with 64 neurons.
- Accuracy: **92.37%**
- Strength: Captures long-term dependencies.

### 4. **CNN-LSTM**
- Combines spatial feature extraction (via CNNs) with temporal modeling (via LSTMs).
- Accuracy: **91.82%**
- Strength: Models spatial and temporal dependencies.

### 5. **Temporal Convolutional Network (TCN)**
- Dilated causal convolutions for long-term dependencies.
- Fully connected dense layer for output.
- Accuracy: **93.01%**
- Strength: Computationally efficient and best-performing model.

---

## 🔧 Installation

### Clone the repository:
```bash
git clone https://github.com/yourusername/HAR-Neural-Networks.git
cd HAR-Neural-Networks
