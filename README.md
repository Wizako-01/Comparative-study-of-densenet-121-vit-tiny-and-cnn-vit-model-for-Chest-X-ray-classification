# Multiclass Chest X-ray Classification using Hybrid Deep Learning

## Overview

This project presents a deep learning approach for multiclass classification of chest X-ray images into four categories: COVID-19, Pneumonia, Tuberculosis (TB), and Normal. The study evaluates convolutional, transformer-based, and hybrid architectures, and proposes a hybrid model that integrates DenseNet-121 and a Vision Transformer (ViT-Tiny).

The objective is to develop a reliable and interpretable system that can support clinical decision-making, particularly in settings with limited access to radiological expertise.

---

## Models

Three models were implemented and compared:

- **DenseNet-121**: A convolutional neural network used as a baseline for extracting local image features.
- **Vision Transformer (ViT-Tiny)**: A transformer-based model designed to capture global contextual relationships within the image.
- **Hybrid Model (DenseNet-121 + ViT-Tiny)**: A proposed architecture that combines both models through feature-level fusion.

The hybrid model integrates local feature extraction with global contextual representation to improve classification performance.

---

## Results

| Model | Accuracy | Macro F1 | Macro AUC |
|------|---------|---------|----------|
| DenseNet-121 | 97.17% | 0.97 | 0.99897 |
| ViT-Tiny | 98.17% | 0.98 | 0.99863 |
| Hybrid Model | 99.00% | 0.99 | 0.99959 |

The hybrid model achieved the best overall performance across all evaluation metrics.

---

## Explainability

Model interpretability was assessed using Gradient-weighted Class Activation Mapping (Grad-CAM). The hybrid model demonstrated more consistent focus on clinically relevant lung regions compared to the individual models, providing improved interpretability.

---

## Dataset

The study uses the Nigeria Chest X-ray Dataset from Kaggle.

- Source: Aminu Kano Teaching Hospital, Nigeria  
- Total Images: 2,600  
- Classes: COVID-19, Pneumonia, Tuberculosis (TB), Normal  
- Distribution: Balanced (650 images per class)  
- Annotations: Radiologist-verified  

---

## Preprocessing

- Images resized to 224 × 224  
- Grayscale images converted to three channels  
- Normalization applied  
- Training set split into training (80%) and validation (20%)  

---

## Training Configuration

- Loss Function: Cross-Entropy Loss  
- Optimizer: AdamW  
- Learning Rate: 1 × 10⁻⁴  
- Weight Decay: 0.01  
- Scheduler: Cosine Annealing  
- Epochs: 10  

---

## Evaluation Metrics

Performance was evaluated using:

- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion Matrix  
- AUC-ROC (One-vs-Rest)  

---

## Project Structure

