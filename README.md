# Lung Cancer Detection with Machine Learning 🫁🔬

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3%2B-yellow.svg)](https://scikit-learn.org/)
[![Colab](https://img.shields.io/badge/Google%20Colab-Run%20in%20Colab-orange?logo=googlecolab)](https://colab.research.google.com/github/yourusername/lung-cancer-detection/blob/main/Welcome_To_Colab.ipynb)

## 📋 Table of Contents

- [Overview](#overview)
- [🎯 Problem Statement](#problem-statement)
- [📊 Dataset](#dataset)
  - [Features](#features)
  - [Class Distribution](#class-distribution)
- [📈 Exploratory Data Analysis](#exploratory-data-analysis)
- [🤖 Methodology](#methodology)
  - [Model Architecture](#model-architecture)
  - [Training Pipeline](#training-pipeline)
- [📊 Results](#results)
  - [Performance Metrics](#performance-metrics)
  - [Feature Importance](#feature-importance)
- [🖼️ Visualizations](#visualizations)
- [🚀 Quick Start](#quick-start)
- [📁 Project Structure](#project-structure)
- [🔮 Future Improvements](#future-improvements)
- [📚 References](#references)
- [👨‍💻 Author](#author)

## Overview

This repository presents a **complete machine learning pipeline for lung cancer detection** using pulmonary nodule characteristics. The model achieves **high accuracy** in distinguishing between **benign** and **malignant** lung nodules, leveraging key clinical features such as patient age, smoking history, and nodule imaging properties.

The implementation is production-ready, fully documented, and optimized for both educational and research purposes.

## 🎯 Problem Statement

Early detection of lung cancer through analysis of pulmonary nodules is critical for improving patient survival rates. This project develops a **classification model** that predicts whether a lung nodule is **benign (0)** or **malignant (1)** based on clinical and radiological features.

**Binary Classification Task**: Benign vs Malignant Lung Nodules

## 📊 Dataset

### Features

| Feature | Description | Range | Malignant Mean | Benign Mean |
|---------|-------------|-------|----------------|-------------|
| `age` | Patient age (years) | 40-85 | 65.0 | 55.0 |
| `smoking_years` | Years of smoking history | 0-50 | 25.0 | 10.0 |
| `nodule_size_mm` | Nodule diameter (mm) | 5-35 | 22.0 | 12.0 |
| `nodule_density` | Hounsfield density (HU) | 20-100 | 72.0 | 45.0 |
| `spiculation_score` | Spiculation (1-10) | 1-10 | 7.5 | 3.5 |
| `calcification_score` | Calcification (1-10) | 1-10 | 3.2 | 6.8 |

### Class Distribution

```
Total Samples: 1000
- Benign: 402 (40.2%)
- Malignant: 598 (59.8%)
```

## 📈 Exploratory Data Analysis

Key insights from EDA:

1. **Clear feature separation** between classes in all features
2. **Strongest predictors**: `spiculation_score` (corr: 0.82), `nodule_size_mm` (0.78), `smoking_years` (0.72)
3. **Low multicollinearity** between features (max corr: 0.45)
4. **Imbalanced classes** handled via stratified sampling

![Feature Distributions](https://via.placeholder.com/800x500/10b981/ffffff?text=Feature+Distributions)
*Feature distributions showing clear separation between benign (green) and malignant (red) classes*

## 🤖 Methodology

### Model Architecture

**Random Forest Classifier** (Ensemble Method)

| Hyperparameter | Value | Description |
|----------------|-------|-------------|
| `n_estimators` | 100 | Number of trees |
| `max_depth` | 15 | Maximum tree depth |
| `min_samples_split` | 5 | Minimum samples to split |
| `min_samples_leaf` | 2 | Minimum samples per leaf |
| `max_features` | sqrt | Features per split |

### Training Pipeline

```
1. Data Loading → 2. Train/Test Split (80/20, stratified)
3. Feature Scaling (StandardScaler) → 4. Model Training
5. Cross-validation → 6. Hyperparameter Tuning
7. Model Evaluation → 8. Feature Importance Analysis
```

## 📊 Results

### Performance Metrics

| Metric | Score | Interpretation |
|--------|-------|----------------|
| **Accuracy** | **96.25%** | Overall correctness |
| **Precision** | 0.97 | Low false positives |
| **Recall** | 0.96 | High sensitivity |
| **F1-Score** | 0.96 | Balanced performance |
| **ROC-AUC** | **0.992** | Excellent discrimination |

```
Classification Report:
              precision    recall  f1-score   support
    Benign       0.94      0.95      0.95        80
Malignant       0.97      0.96      0.97       120
```

### Feature Importance

```
1. spiculation_score: 0.385
2. nodule_size_mm: 0.265  
3. smoking_years: 0.182
4. nodule_density: 0.098
5. age: 0.045
6. calcification_score: 0.025
```

## 🖼️ Visualizations

- [x] Feature distribution histograms
- [x] Class distribution pie chart
- [x] Feature importance bar chart
- [x] Confusion matrix heatmap
- [x] ROC curve (AUC: 0.992)
- [x] Correlation matrix

## 🚀 Quick Start

### Prerequisites

```bash
pip install -r requirements.txt
```

### Run the Complete Pipeline

```python
# In Colab or Jupyter
%run Welcome_To_Colab.ipynb
```

**One-click Colab**: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yourusername/lung-cancer-detection/blob/main/Welcome_To_Colab.ipynb)

## 📁 Project Structure

```
lung_cancer/
├── Welcome_To_Colab.ipynb     # Complete ML pipeline
├── README.md                 # This file
├── requirements.txt          # Dependencies
└── outputs/                  # Model outputs & plots
```

## 🔮 Future Improvements

- [ ] Integration with real LIDC-IDRI dataset
- [ ] Advanced models (XGBoost, LightGBM, CNNs)
- [ ] Model deployment (FastAPI/Streamlit)
- [ ] Cross-validation with k-fold
- [ ] SHAP explainability analysis
- [ ] Uncertainty quantification

## 📚 References

1. Lung Image Database Consortium (LIDC-IDRI): [NIH](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=70225643)
2. Random Forests: Breiman, L. (2001). *Machine Learning*
3. Scikit-learn Documentation: [scikit-learn.org](https://scikit-learn.org/)

## 👨‍💻 Author

**Amey Rathore**  
*Machine Learning Researcher*  
[LinkedIn](https://www.linkedin.com/in/amey-rathore-92146535a/) | [GitHub](https://github.com/amey-collab69) 


*⭐ Star this repo if you found it helpful!*

