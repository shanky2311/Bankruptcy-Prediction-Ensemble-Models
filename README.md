# Bankruptcy Prediction Using Ensemble Models

This repository contains the final project for MGMT 571 (Fall 2024) at Purdue University. The objective was to build robust machine learning models to **predict bankruptcy** using high-dimensional financial attributes from a Kaggle-provided dataset.

## 🎯 Problem Statement
Develop data mining models that can predict whether a firm is at risk of bankruptcy, based on a large set of financial attributes.

## 📦 Dataset Overview
- Source: Kaggle (Private Competition)
- Features: 60+ econometric attributes
- Target Variable: Bankruptcy (Yes/No)

## ⚠️ Challenges Encountered
- **High Dimensionality**: Risk of overfitting due to large feature space.
- **Class Imbalance**: Few firms labeled bankrupt relative to non-bankrupt.
- **Multicollinearity**: Strong correlation between features (e.g., Attr33 vs. Attr63).
- **Extreme Skewness & Kurtosis**: Outliers and non-normal distributions across attributes (e.g., Attr13 kurtosis > 5,000).

## 🧹 Data Processing
- Class balancing using **sampling** techniques (Sample Node in SAS EM)
- Skewness/outlier handling using **Replacement/Filter Nodes**
- Feature standardization using **Transform Nodes**
- Eventually, **gradient boosting and ensemble models** were chosen due to their robustness, and preprocessing was minimized

## 🔍 Models Explored

### ✅ Final Ensemble Model:
- **ROC-AUC (Test Set): 0.94466**
- Components:
  - Logistic Regression (with regularization & polynomial features)
  - High Performance GLM (HP GLM)
  - HP SVM (Polynomial Kernel)
  - Gradient Boosting (100 iterations, depth = 2)
  - Neural Network (3 hidden layers, 10 units)
  - LARS (adaptive Lasso)

### 📊 Additional Experiments:
- Tried excluding HP GLM → Slight drop in performance
- Used polynomial kernels for SVM
- Boosted NN capacity (from 5 to 10 hidden units)

## 🔑 Key Decisions
- Switched to **ensemble modeling** to improve generalization and reduce overfitting.
- Increased **Gradient Boosting iterations** for stability.
- Tuned **SVM kernel**, **Neural Network architecture**, and **optimizer convergence settings**.

## 🧠 Why Ensemble Works
- Gradient Boosting and Neural Nets handle non-linear interactions.
- Logistic Regression and GLM offer interpretability.
- SVM provides strong classification boundaries in high dimensions.
- LARS helps with dimensionality reduction and sparse selection.

## 🛠️ Tools Used
- **SAS Enterprise Miner** (modeling, preprocessing)
- **Kaggle** (private leaderboard evaluation)

## 📈 Final Evaluation Metric
- **ROC-AUC** on Kaggle private leaderboard used to assess model performance.

## 👥 Team
FAST Analytics:
- Muskan Aggarwal
- [Other team members if applicable]

## 📚 Course Info
MGMT 571 — Data Mining for Business  
Purdue University, Fall 2024

---

Let me know if you'd like this saved as a file, or need a PPT or ZIP-ready GitHub structure!
