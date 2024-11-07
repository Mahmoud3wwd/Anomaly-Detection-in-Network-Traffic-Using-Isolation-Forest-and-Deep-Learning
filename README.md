# Anomaly Detection in Network Traffic

This project implements an anomaly detection system for synthetic network traffic data using a combination of an Isolation Forest model and a deep learning neural network. The system is designed to identify anomalies in network traffic, which may indicate potential security threats or unusual activity.

## Table of Contents
- [Project Overview](#project-overview)
  This repository provides an end-to-end solution for detecting anomalies in network traffic using a hybrid approach. The first step utilizes the Isolation Forest algorithm for unsupervised anomaly detection, followed by a deep learning neural network for binary classification of normal and anomalous data. The system includes data preprocessing, feature engineering, model training, and evaluation, offering a comprehensive pipeline for anomaly detection tasks.

- [Dataset](#dataset)
- [Installation](#installation)
- [Code Structure](#code-structure)

- [Methodology](#methodology)
  The anomaly detection process follows these steps:

Data Preprocessing:

Min-Max scaling of numerical features to ensure all features are on the same scale.
Feature engineering by creating additional features like TotalBytes and TotalPackets.
Anomaly Detection with Isolation Forest:

An Isolation Forest model is trained on the features to detect anomalies in the dataset.
The predicted anomalies are labeled and used to train the deep learning model.
Deep Learning Model:

A simple neural network model is constructed using Keras with two hidden layers (64 and 32 neurons).
The model is compiled using binary cross-entropy loss and Adam optimizer, and trained on the labeled data.
Predictions are evaluated using metrics such as confusion matrix, classification report, and ROC-AUC.

- [Evaluation](#evaluation)
  Evaluation
The performance of the model is evaluated using several metrics:

Confusion Matrix: Provides insights into true positives, true negatives, false positives, and false negatives.
Classification Report: Includes precision, recall, F1-score, and support for both normal and anomalous classes.
ROC Curve and AUC: Plots the ROC curve and calculates the Area Under the Curve (AUC), which indicates the model’s ability to distinguish between normal and anomalous traffic.
- [Results](#results)
  Results
After training the model and evaluating it on the test set, the following results were observed:

Confusion Matrix: Visualizes the classification performance.
Classification Report: Shows the precision, recall, and F1-score for each class.
ROC-AUC: The AUC score indicates how well the model differentiates between normal and anomalous traffic.


## Dataset

The dataset used in this project is a synthetic network traffic dataset, which includes various features such as `BytesSent`, `BytesReceived`, `PacketsSent`, `PacketsReceived`, and `Duration`. The target variable, `IsAnomaly`, indicates whether a traffic instance is an anomaly (1) or normal (0).

## Installation

To run the code and experiment with the anomaly detection pipeline, you need to have the following libraries installed:

```bash
pip install pandas numpy tensorflow scikit-learn matplotlib seaborn
