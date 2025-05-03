# EEG-Based Seizure Prediction System

Predicting epileptic seizures using EEG (Electroencephalogram) data is a critical step toward providing early warnings and improving the quality of life for epilepsy patients. This project applies machine learning models to classify EEG signals and forecast seizures in advance.

---

## 📚 Table of Contents

- [Project Objective](#-project-objective)
- [EEG Overview](#-eeg-overview)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
  - [1. Data Preprocessing](#1-data-preprocessing)
  - [2. Feature Engineering](#2-feature-engineering)
  - [3. Model Development](#3-model-development)
  - [4. Model Evaluation](#4-model-evaluation)
- [Results](#-results)
- [Visual Architecture](#-visual-architecture)
- [Repository Structure](#-repository-structure)
- [How to Run](#-how-to-run)
- [Future Enhancements](#-future-enhancements)
- [License](#-license)
- [Contributors](#-contributors)
- [Contact](#-contact)

---

## 🧠 Project Objective

The goal of this project is to develop an automated system that analyzes EEG data to predict the onset of epileptic seizures. By identifying patterns in brain activity, this system aims to provide early warnings to patients and medical professionals, enabling timely intervention and improved patient outcomes.

---

## 🧾 EEG Overview

Electroencephalography (EEG) is a method used to record electrical activity in the brain using sensors (electrodes) placed on the scalp. These readings are used to detect unusual brain activity that may precede epileptic seizures.

![EEG Brain Signals](https://github.com/user-attachments/assets/5121e10b-099f-4504-98f2-ddf54b4e612b)


---

## 📊 Dataset

We used the **Epileptic Seizure Recognition Dataset** from the UCI Machine Learning Repository. It contains 11,500 EEG segments categorized into five classes.

- **Instances:** 11,500
- **Features:** 178 EEG signal values per second
- **Classes:**
  - Class 1: Seizure activity
  - Classes 2–5: Normal or non-seizure activity
- For binary classification: Class 1 → Seizure, Class 2–5 → Non-Seizure

---

## 🛠️ Methodology

## 🧩 Visual Architecture

### EEG-Based Seizure Prediction Pipeline

![system_architecture](https://github.com/user-attachments/assets/50e287bd-7c57-47eb-ba00-082ac0f1fab1)


### 1. Data Preprocessing
- **Binary Conversion**: Converted the 5-class target into binary labels (seizure vs. non-seizure).
- **Shuffling**: To randomize patterns and avoid bias.
- **Train-Test Split**: 80/20 ratio.
- **Standardization**: Used `StandardScaler` to normalize feature ranges.

### 2. Feature Engineering
- The dataset includes 178 EEG values per instance (1-second snapshot), which serve directly as features.
- Future enhancements may include:
  - Statistical extraction (mean, kurtosis)
  - Frequency domain transformation (FFT)

### 3. Model Development
We trained the following models using the same training dataset:

| Model                | Description |
|---------------------|-------------|
| Logistic Regression | Baseline linear classifier |
| SVM (RBF Kernel)    | Handles non-linear separation |
| Random Forest       | Tree-based ensemble model |
| XGBoost             | Gradient-boosted decision trees |
| KNN                 | Distance-based lazy learner |
| Artificial Neural Network (ANN) | Deep learning with dense layers |

### ANN Model Architecture  

![ann_architecture](https://github.com/user-attachments/assets/43e936af-b9c1-4236-be91-82059bb93e22)

### 4. Model Evaluation
We used the following performance metrics:
- **Accuracy**: Overall correctness
- **Precision & Recall**: For seizure detection (Class 1)
- **F1 Score**: Balance of precision and recall
- **Confusion Matrix**: Error analysis

---

## 📈 Results

| Model                 | Accuracy | Precision | Recall | F1-Score |
|----------------------|----------|-----------|--------|----------|
| Logistic Regression  | 92.3%    | 91.8%     | 91.2%  | 91.5%    |
| SVM (RBF Kernel)     | 94.1%    | 93.7%     | 92.9%  | 93.3%    |
| Random Forest        | 96.3%    | 96.0%     | 95.6%  | 95.8%    |
| XGBoost              | 96.4%    | 96.2%     | 95.9%  | 96.0%    |
| KNN (k=5)            | 93.0%    | 92.6%     | 92.1%  | 92.3%    |
| **ANN**              | **97.2%**| **96.9%** | **96.7%**| **96.8%**|

✅ **ANN performed the best**, achieving over 97% accuracy and balanced F1-score.

---

