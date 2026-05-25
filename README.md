# Optimizing Breast Cancer Prediction with the Puma Optimizer

## Overview
This project explores the application of a state-of-the-art metaheuristic algorithm, the **Puma Optimizer (PO)**, to improve the diagnosis of breast cancer tumors as Malignant or Benign using the Breast Cancer Wisconsin dataset. 

While traditional Machine Learning approaches often rely on human-guided feature selection (e.g., manually dropping features based on correlation heatmaps) and limited grid searches for hyperparameter tuning, this project aims to fully automate and mathematically optimize this pipeline. 

By simulating the biological exploration and exploitation behaviors of pumas, the optimizer autonomously navigates the complex search space of both features and model hyperparameters to find the optimal configuration for a Support Vector Machine (SVM).

## Key Concepts

### The Puma Optimizer (PO)
The Puma Optimizer is a continuous optimization algorithm inspired by the hunting mechanisms of pumas. For this project, it was adapted into a **Binary Puma Optimizer (BPO)** to handle discrete feature selection, mapping continuous values into binary decisions (include or drop a feature).

### Simultaneous Feature and Hyperparameter Optimization
Instead of optimizing features and hyperparameters in isolation, the Puma Optimizer evaluates them simultaneously. The "DNA" of each simulated puma represents a potential solution that encodes:
- Which medical features to include or exclude.
- The `C` (Regularization) hyperparameter.
- The `Gamma` hyperparameter.
- The SVM `Kernel` type (`linear` or `rbf`).

### The Goal: Accuracy and Recall in Medical Diagnosis
The primary objective of the fitness function guiding the Puma Optimizer is twofold:
1. **Minimize Classification Errors:** Achieve the highest possible accuracy by selecting the most mathematically significant features.
2. **Prioritize Recall:** In the medical field, False Negatives (missing a cancer diagnosis) are far more dangerous than False Positives. The algorithm is designed to heavily penalize False Negatives, ensuring a robust model tailored for real-world medical applications.

## Conclusion
By treating the machine learning pipeline as an evolutionary optimization problem, the Puma Optimizer removes human bias from feature selection and overcomes the limitations of narrow grid searches, ultimately delivering a highly precise, autonomous diagnostic model.
