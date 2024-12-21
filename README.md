# Intrusion Detection System (IDS) using Machine Learning

This project aims to develop and evaluate an Intrusion Detection System (IDS) based on machine learning models, using the **CIC-IDS 2017** dataset. The goal is to classify network traffic data into normal and attack categories, including identifying specific attack types using both binary and multi-class classification models.

## Dataset

The **CIC-IDS 2017** dataset is designed to simulate modern network traffic, including benign traffic and seven types of attacks:

- **Brute Force**
- **Heartbleed**
- **Botnet**
- **DoS**
- **DDoS**
- **Web Attack**
- **Infiltration**

The dataset contains **2.8 million** rows and **79 columns**, with the majority of data labeled as benign traffic and a highly imbalanced distribution between normal and attack traffic.

### Dataset Preprocessing

1. **Duplicates Removal**: Duplicate rows (308,381) were identified and dropped to ensure unbiased training.
2. **Handling Missing and Invalid Values**: Columns `Flow Bytes/s` and `Flow Packets/s` had missing values (0.06%), which were filled with median values.
3. **Memory Optimization**: Due to the large size of the dataset, memory usage was reduced by downcasting data types, reducing memory consumption by 47.5%.
4. **Feature Scaling**: Standardization was applied to the dataset before PCA for dimensionality reduction.

## Exploratory Data Analysis (EDA)

- **Correlations**: Identified strong correlations between many features, leading to issues with multicollinearity. A correlation matrix was generated and visualized.
- **Outliers**: Detected and analyzed outliers, which may represent network intrusion attempts.
- **Visualizations**: Histograms, box plots, scatter plots, and heatmaps were created to understand data distribution, correlations, and feature relationships.

## Data Preprocessing and Feature Engineering

1. **Principal Component Analysis (PCA)**: Used to reduce dimensionality and overcome the computational burden of working with a large number of features.
2. **SMOTE (Synthetic Minority Over-sampling Technique)**: Applied to create a balanced dataset for multi-class classification by upsampling the minority class.

## Machine Learning Models

### Binary Classification

The binary classification task involved distinguishing between normal traffic and anomalous traffic. The following models were trained:

- **Logistic Regression**: Simple, fast, but less accurate.
- **Support Vector Machine (SVM)**: Computationally expensive but higher accuracy.

### Multi-class Classification

The multi-class classification task extended the binary task by predicting the specific type of attack. Models used include:

- **Random Forest Classifier**
- **Decision Tree Classifier**
- **K Nearest Neighbors (KNN)**

## Model Performance

- **Accuracy, Recall, F1-Score**: These metrics were calculated and used to evaluate the performance of the models.
- **Confusion Matrix**: Provided insights into the model's performance across different attack types.
- **Cross-Validation**: Ensured models were not overfitted by evaluating them across multiple folds.

### Results

- **Best Performing Model (Multi-class)**: Random Forest achieved the highest performance, with the best precision, recall, and F1-score.
- **Best Performing Model (Binary)**: SVM performed better in terms of accuracy compared to Logistic Regression.
