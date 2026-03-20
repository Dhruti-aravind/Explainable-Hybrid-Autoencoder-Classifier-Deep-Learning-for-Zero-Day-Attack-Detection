# Explainable Hybrid Autoencoder-Classifier for Zero-Day Attack Detection

## Overview

This project presents a hybrid deep learning framework for detecting both known and zero-day cyber attacks. The model combines an unsupervised autoencoder with a supervised classifier to learn normal network behavior and identify deviations indicative of malicious activity.

By leveraging reconstruction error and latent feature representations, the system achieves strong generalization to previously unseen attack types while maintaining high detection performance.

---

## Dataset

This project uses the **UNSW-NB15 dataset**, a modern and comprehensive network intrusion dataset that includes both real and synthetic traffic.

* Contains normal traffic and nine categories of cyber attacks
* Includes 49 features capturing flow, content, and time-based attributes
* Designed to reflect contemporary network behaviors and attack patterns

The dataset provides a robust benchmark for evaluating intrusion detection systems, especially for zero-day attack scenarios.

---

## Methodology

### Hybrid Model Architecture

The proposed system integrates:

* **Autoencoder (Unsupervised Learning)**
  Learns normal traffic patterns and encodes them into latent representations

* **Classifier (Supervised Learning)**
  Uses latent features and reconstruction error to classify traffic as benign or malicious

### Key Idea

* Normal traffic → low reconstruction error
* Anomalous/zero-day traffic → high reconstruction error
* Combined features improve classification accuracy

---

## Algorithm

### Training Phase

1. Train autoencoder on normal (benign) traffic
2. Encode input into latent space
3. Reconstruct input and compute reconstruction error
4. Create hybrid feature vector:

   * Latent representation
   * Reconstruction error
5. Train classifier using labeled data

### Inference Phase

1. Encode incoming sample
2. Compute reconstruction error
3. Form hybrid feature vector
4. Predict using classifier
5. Classify as:

   * Attack
   * Normal
6. Generate explanation using SHAP

---

## Explainability

The model integrates explainable AI techniques using SHAP to interpret predictions.

* Identifies important features influencing decisions
* Provides transparency for cybersecurity applications
* Enhances trust in model predictions

---

## Performance

The model demonstrates strong performance on the UNSW-NB15 dataset:

* Accuracy: 93.15%
* Precision: 89.91%
* Recall: 98.63%
* F1 Score: 94.06%
* ROC-AUC: 0.952

### Zero-Day Detection

* Recall: 99.29%
* F1 Score: 99.64%

The system effectively detects previously unseen attack types with very low false negatives.

---

## Key Features

* Hybrid AE-classifier architecture
* Effective zero-day attack detection
* Reconstruction-error-based anomaly detection
* SHAP-based explainability
* Strong generalization to unseen attacks

---

## Project Structure

```
├── Dataset/
├── Images/
├── Model/
└── README.md
```

---

## Installation

### Requirements

* Python 3.x
* TensorFlow / PyTorch
* Scikit-learn
* NumPy, Pandas
* Matplotlib / Seaborn
* SHAP

### Setup

```bash
git clone https://github.com/Dhruti-aravind/Explainable-Hybrid-Autoencoder-Classifier-Deep-Learning-for-Zero-Day-Attack-Detection.git
cd Explainable-Hybrid-Autoencoder-Classifier-Deep-Learning-for-Zero-Day-Attack-Detection
```

---

## Usage

1. Download the UNSW-NB15 dataset from Kaggle
2. Run the notebook:

```bash
jupyter notebook Zero_day_attack.ipynb
```

---

## Results and Visualization

The project includes:

* Reconstruction error distribution
* Latent space visualization (PCA)
* Confusion matrix
* SHAP feature importance plots

---

## Future Work

* Extend to federated learning for privacy-preserving IDS
* Evaluate on additional datasets (NSL-KDD, CIC-IDS2017, IoT-23)
* Optimize for real-time and edge deployment
* Improve scalability and model efficiency

---
