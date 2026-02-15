# Bias-Aware and Explainable Deep Learning Model for Early Detection of Alzheimer’s Disease using MRI Scans

## Overview

Alzheimer’s disease (AD) is a progressive neurodegenerative disorder affecting millions worldwide. Early diagnosis is critical, yet challenging due to subtle structural brain changes in initial stages.

This project presents a **bias-aware, explainable deep learning framework** for multi-class classification of Alzheimer’s disease using MRI scans. The system integrates:

- DCGAN-based class balancing
- Transfer Learning (DenseNet121 & MobileNetV2)
- Explainable AI (Grad-CAM + SHAP)
- Bias Gap Index (BGI) fairness evaluation

The goal is to build a model that is not only **accurate**, but also **interpretable and equitable** for responsible medical AI deployment.

---

## Key Objectives

- Improve early-stage Alzheimer’s detection
- Address class imbalance using synthetic MRI generation
- Provide transparent model explanations
- Evaluate and minimize demographic bias
- Develop a clinically meaningful AI pipeline

---

## Dataset

- 35,840 MRI images
- 4 diagnostic categories:
  - Non-Demented
  - Very Mild Demented
  - Mild Demented
  - Moderate Demented

### Preprocessing:
- Resize: 224 × 224
- Pixel normalization
- Data augmentation (rotation, zoom, flip, shift)
- Stratified train/validation/test split

---

## Methodology

### 1️⃣ DCGAN for Class Balancing
A Deep Convolutional GAN was trained to generate synthetic MRI scans for underrepresented classes, improving minority class detection and reducing bias caused by class imbalance.

### 2️⃣ Transfer Learning
Two pre-trained CNN architectures were fine-tuned:

- **DenseNet121**  
- **MobileNetV2**

A custom classification head was added to adapt models to 4-class Alzheimer’s detection.

### 3️⃣ Explainable AI

To improve transparency and clinical trust:

- **Grad-CAM** for region-level heatmap visualization  
- **SHAP** for pixel-level feature attribution  

These techniques highlight brain regions influencing predictions.

### 4️⃣ Fairness Evaluation

Bias Gap Index (BGI) was computed across:
- Age groups
- Gender groups

Lower BGI values indicate equitable performance across demographics.

---

## Experimental Results

| Model        | Accuracy | Age BGI | Gender BGI |
|-------------|----------|---------|------------|
| DenseNet121 | 92.34%   | 0.0185  | 0.0069     |
| MobileNetV2 | 90.87%   | 0.0203  | 0.0087     |

### Key Observations:
- DenseNet121 achieved highest performance.
- Minimal bias observed across demographic groups.
- Most misclassifications occur between adjacent severity stages (Very Mild ↔ Mild).

---

## Explainability Insights

- Grad-CAM highlighted hippocampus and temporal lobe regions.
- SHAP provided pixel-wise contribution maps.
- Model attention aligned with known Alzheimer’s pathology.

This strengthens clinical reliability and interpretability.

---

## Clinical Relevance

This framework prioritizes:

- Early detection
- Fair performance
- Transparent decision-making
- Responsible AI deployment

The integration of performance, fairness, and explainability makes this approach suitable for real-world medical systems.

---


