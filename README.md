# Human Activity Recognition Using Neural Networks

This repository contains the implementation of a project focused on **Human Activity Recognition (HAR)** using various deep learning architectures, including **CNNs, LSTMs**, and **Temporal Convolutional Networks (TCNs)**. The project aims to explore whether Neural Networks can better classify static activities such as **sitting** and **standing**, which are particularly challenging for machine learning models.

---
## ❓ Problem of Interest
Human Activity Recognition (HAR) involves analyzing sensor data to determine an individual’s physical activity, such as walking 🚶, sitting 🪑, or standing 🧍.

- **🌟 Applications:**
  - Healthcare: Tracking patient mobility.
  - Fitness Apps: Providing personalized insights.
- **Objective:** Improve classification accuracy for challenging activities like sitting and standing.


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

**Dataset Link:** [UCI HAR Dataset](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)

### Preprocessing:
- The dataset was loaded as raw sensor data without feature extraction.
- Data was standardized and split into training, validation, and testing sets.

---
## ⏳ Time-Series Data Processing with Neural Networks

Neural Networks are particularly suited for time-series data because they can extract patterns over time. Each architecture brings unique advantages:

- **Convolutional Neural Networks (CNNs):** Efficiently extract local temporal patterns using 1D convolutions and pooling layers. Ideal for short-term dependencies.
- **Long Short-Term Memory (LSTMs):** Use gated mechanisms to store long-term dependencies and address vanishing gradient problems. Suitable for both short- and long-term temporal relationships.
- **Temporal Convolutional Networks (TCNs):** Employ causal and dilated convolutions for modeling long-term dependencies while ensuring no future information leakage. Highly parallelizable and scalable for large datasets.

---

## 🧠 Models
This project evaluates the following models:

### 1. Baseline Model: Support Vector Machine (SVM)
- Features extracted: Time and frequency domain characteristics.
- Multiclass classification using the One-vs-All strategy.
- **Accuracy:** 96%
- **Weakness:** Struggles with static activities (e.g., sitting: 88% recall).

### 2. Convolutional Neural Network (CNN)
- **Architecture:**
  - 3 convolutional layers with MaxPooling and Dropout.
  - Final dense layer with 128 neurons and softmax activation.
- **Accuracy:** 92.16%
- **Strength:** Handles short-term dependencies efficiently.

### 3. Long Short-Term Memory (LSTM)
- **Architecture:**
  - 2 LSTM layers with Batch Normalization and Dropout.
  - Fully connected dense layer with 64 neurons.
- **Accuracy:** 92.37%
- **Strength:** Captures long-term dependencies.

### 4. Temporal Convolutional Network (TCN)
- **Architecture:**
  - Dilated causal convolutions for long-term dependencies.
  - Fully connected dense layer for output.
- **Accuracy:** 93.01%
- **Strength:** Computationally efficient and best-performing model.
---

## 📊 Results

### Accuracy and Loss Comparison
| Model         | Test Accuracy | Test Loss |
|---------------|---------------|-----------|
| SVM           | 96.00%        | -         |
| CNN           | 92.16%        | 0.2547    |
| LSTM          | 92.37%        | 0.2758    |
| TCN           | **93.01%**    | **0.2381**|

### Confusion Matrices and Classification Reports
#### CNN Classification Report
- **Strengths:** High recall for dynamic activities like **walking (99%)** and **laying (100%)**.
- **Weaknesses:** Misclassification between sitting and standing, with F1-scores around **0.82**.

#### LSTM Classification Report
- **Strengths:** Slightly better recall for sitting and standing than CNN, with improved F1-scores for static activities.
- **Dynamic Activities:** Near-perfect accuracy for walking and laying.

#### TCN Classification Report
- **Strengths:** Best performance across all activities, including improved recall for static ones like sitting and standing.
- **Dynamic Activities:** Near-perfect classification.
- **Overall Accuracy:** **93.01%**, with F1-scores of **0.80** for sitting and **0.84** for standing.

---

## ⚙️ Installation

Clone the repository:
```bash
git clone https://github.com/sasha-ov/ECE5258-ICP.git
cd ECE5258-ICP
```

---

## 🛠️ Instructions to Replicate Results

### 1. Dataset Preparation
- Download the HAR dataset from the [UCI Archive](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones).
- Place the dataset in the `data/` folder.
---

## 📜 References
1. Anguita et al., "A Public Domain Dataset for Human Activity Recognition Using Smartphones". [Link](https://www.semanticscholar.org/paper/A-Public-Domain-Dataset-for-Human-Activity-using-Anguita-Ghio/83de43bc849ad3d9579ccf540e6fe566ef90a58e)
2. Wang et al. (2017), Hochreiter & Schmidhuber (1997), Bai et al. (2018)

---

## 🙏 Acknowledgments
- Project presentation video: [YouTube Link](https://youtu.be/dt7J8pqwO7I)
- Florida Institute of Technology
- Contributors: Alesandra Olinde Vergara
