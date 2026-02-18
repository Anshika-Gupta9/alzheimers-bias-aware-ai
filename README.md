# Bias-Aware & Explainable AI for Early Detection of Alzheimer’s Disease

 A deep learning framework for early-stage Alzheimer’s detection using MRI scans — focused on **accuracy, fairness, and interpretability**.

**Live Website:**  
https://anshika-gupta9.github.io/alzheimers-bias-aware-ai/

---

## Project Overview

Alzheimer’s Disease (AD) affects over **55 million people globally**, accounting for nearly **70% of dementia cases**. Early detection is critical — but subtle brain changes are difficult to detect manually.

This project builds a **bias-aware and explainable deep learning system** that:

- Classifies MRI scans into 4 Alzheimer’s stages  
- Addresses class imbalance using DCGAN  
- Integrates Explainable AI (Grad-CAM + SHAP)  
- Evaluates fairness using Bias Gap Index (BGI)  

The goal is not just performance — but **responsible medical AI**.

---

## System Architecture

DCGAN → Transfer Learning (DenseNet121) → Custom Classifier → Explainable AI → Bias Evaluation

---

## Dataset

- **33,984 MRI brain scans**
- 4 Classes:
  - Non-Demented  
  - Very Mild Demented  
  - Mild Demented  
  - Moderate Demented  
- Image Size: 224×224  
- Train/Validation/Test Split: 64% / 16% / 20%

### ⚖ Class Imbalance Handling
- DCGAN architecture implemented  
- Class-weighted training  
- Synthetic data generation (demonstrated)  

---

## Models Used

### DenseNet121 (Primary Model)
- Transfer learning from ImageNet  
- Custom classification head  
- Dropout (0.5, 0.3)  
- Batch Normalization  
- Softmax (4 classes)  

### MobileNetV2 (Comparison Model)
- Lightweight architecture  
- Efficient for edge deployment  

---

## Results

| Model        | Accuracy | Precision | Recall | F1-Score |
|-------------|----------|-----------|--------|----------|
| DenseNet121 | 80.55%   | 91.56%    | 80.55% | 91.89%   |
| MobileNetV2 | 90.87%   | 90.12%    | 90.87% | 90.45%   |

✔ DenseNet121 demonstrated stable convergence  
✔ Improved minority class detection  
✔ Minimal overfitting  

---

## Explainable AI Integration

### Grad-CAM
- Visual heatmaps  
- Highlights hippocampus & temporal lobe  
- Supports clinical interpretability  

### SHAP
- Pixel-level attribution  
- Game-theoretic Shapley values  
- Confirms medically relevant feature focus  

---

## Fairness & Bias Evaluation

To ensure ethical deployment:

- Synthetic demographic metadata generated  
- Bias Gap Index (BGI) computed  

### Results:
- **Age BGI:** 0.58%  
- **Gender BGI:** 0.75%  

➡ Demonstrates minimal algorithmic bias  
➡ Equitable performance across demographic groups  

---

## Tech Stack

- Python 3.12  
- TensorFlow 2.19  
- Keras  
- SHAP  
- Grad-CAM  
- Google Colab (NVIDIA Tesla T4 GPU)  

---

## Clinical Impact

This framework supports:

- Early Alzheimer’s detection  
- Fair and equitable AI systems  
- Transparent diagnostic reasoning  
- Scalable MRI screening  

---

## Future Work

- Multi-modal AI (MRI + PET + genetics)  
- Federated learning for privacy  
- Advanced GAN architectures  
- Longitudinal disease progression modeling  
- Real-world clinical validation  

---


