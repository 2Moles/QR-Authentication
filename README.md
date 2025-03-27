# QR-Authentication
This document details the process of building a machine learning model to classify QR codes  as either "Real" (first print) or "Fake" (second print/scanned). The goal is to distinguish  between original QR codes and those that have been reproduced, potentially for malicious  purposes. 
QR Code Classification: Detecting Counterfeit Prints

1. Introduction

QR codes are widely used for authentication, payments, and product verification. However, counterfeit QR codes pose security risks. This project classifies original and counterfeit QR codes using traditional machine learning and deep learning techniques.

2. Approach

a. Dataset Preparation

Two sets of QR code images: Original (First Print) and Scanned (Second Print)

Extracted features such as mean intensity, edge intensity, contrast, dissimilarity, and frequency domain characteristics

Stored extracted features in CSV files

b. Feature Engineering

Global properties: Mean intensity, standard deviation

Local patterns: Edge intensity, contrast, and dissimilarity

Frequency domain features: FFT mean and standard deviation

c. Model Development

1. Machine Learning Approach

Used a Random Forest classifier on extracted features

Trained using an 80-20 split with cross-validation

2. Deep Learning Approach

CNN-based model trained on raw images

Used data augmentation to improve generalization

Model architecture:

Convolutional layers with ReLU activation

Max pooling layers

Fully connected layers with dropout

Softmax activation for classification

4. Deployment Considerations

a. Computational Efficiency

Machine Learning Model: Low latency, can be deployed on edge devices

Deep Learning Model: Requires GPU acceleration for training, inference optimized using TensorRT

b. Robustness to Scanning Conditions

Used augmented datasets to simulate real-world distortions (blur, noise, rotation)

Achieved robust performance on different lighting and resolution settings

c. Security Implications

Prevents counterfeit QR codes in authentication systems

Can be integrated with blockchain for tamper-proof verification

5. Conclusion

Traditional ML methods provide a balance between speed and accuracy

Deep Learning with CNNs offers superior classification performance

Future improvements: Semi-supervised learning, adversarial training for robustness
