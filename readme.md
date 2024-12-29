# Cyber Intrusion Detection using Deep Learning  

This repository contains a deep learning-based system for detecting intrusions in a cyber system. The project focuses on developing models to classify network connections as either "normal" or "intrusions/attacks" using the well-known KDD Cup 1999 dataset. The dataset simulates a military network environment with a variety of intrusion types, making it a benchmark for intrusion detection research.

---

## Project Objectives  

1. **Data Preparation**  
   - Load and verify the dataset for missing records.  
   - Perform data cleaning by removing NULL values and duplicates.  
   - Normalize and format the data to account for multidimensional features.  

2. **Data Visualization and Preprocessing**  
   - Visualize a subset of the data and its ground truth labels.  
   - Address data imbalance issues to improve classification performance.  

3. **Model Development**  
   - Develop and train three deep learning models:  
     - **Model 1**: Processes individual time instances.  
     - **Model 2**: Processes data as a time series.  
     - **Model 3**: Handles the problem as an anomaly detection task using an autoencoder.  

4. **Model Evaluation**  
   - Evaluate the models using metrics such as accuracy, precision, recall, F1-score, and confusion matrix.  
   - Conduct a comparative analysis of model performance.  

5. **Real-Time Data Analysis**  
   - Build Python code to process and classify incoming data in 5-second intervals using the anomaly detection model.

---

## Dataset  

The dataset used is the **KDD Cup 1999** dataset. It contains labeled network connection records with features such as protocol type, service, and connection status.  
- [KDD Cup 1999 Dataset Documentation](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html)

---

## Implementation Details  

### 1. **Data Preprocessing**  
- Encoded categorical variables (`protocol_type`, `service`, `flag`) using `LabelEncoder`.  
- Converted the label column into binary:  
  - **0**: Normal connections.  
  - **1**: Intrusions/attacks.  
- Standardized the dataset using `StandardScaler`.  
- Addressed data imbalance using class weights and SMOTE (Synthetic Minority Over-sampling Technique).

### 2. **Deep Learning Models**  

#### **Model 1: Feedforward Neural Network**  
- Dense architecture with dropout and L2 regularization for overfitting prevention.  
- Compiled with Adam optimizer and categorical cross-entropy loss.  
- Included callbacks for early stopping and learning rate reduction.  

#### **Model 2: LSTM-Based Time Series Classifier**  
- LSTM layers to capture temporal dependencies in the data.  
- Batch normalization and dropout for better generalization.  
- Optimized with Adam optimizer and evaluated using validation loss.  

#### **Model 3: Autoencoder for Anomaly Detection**  
- Trained on "normal" data only to learn its representation.  
- Used Mean Absolute Error (MAE) as the loss function.  
- Detected anomalies by setting an error threshold to classify deviations.  

### 3. **Real-Time Classification**  
- Built Python code to read incoming data in 5-second intervals.  
- Classified each record as "normal" or "anomalous" using the anomaly detection model.  

---

## Evaluation Metrics  

The models were evaluated using the following metrics:  
- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1-Score**  
- **Confusion Matrix**

---

## Key Results  

- **Feedforward Neural Network**: High performance on static data instances with balanced precision and recall.  
- **LSTM Classifier**: Outperformed static models by leveraging temporal patterns in the data.  
- **Autoencoder**: Effective in anomaly detection tasks, especially for identifying rare intrusions.  

---
## Future Enhancements

- **Incorporate advanced deep learning architectures such as Transformer models for enhanced sequential analysis.
- **Use streaming platforms like Kafka for real-time data ingestion and analysis.
- **Optimize autoencoder thresholds for more robust anomaly detection.
