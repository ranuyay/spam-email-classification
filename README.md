# Spam Email Classification Using Logistic Regression

This project develops an interpretable statistical classification model to determine whether an email is spam or not spam using the UCI Spambase dataset.

The analysis follows a complete supervised machine learning workflow, including exploratory data analysis, feature diagnostics, dimensionality reduction, logistic regression modeling, and evaluation using multiple performance metrics. Emphasis is placed on understanding which signals matter most for classification and how modeling choices affect interpretability and stability.

---

## Project Overview

The Spambase dataset contains 4,601 email observations and 57 numeric predictors representing word frequencies, character frequencies, and structural features of email messages.

The objective of this project is to evaluate whether logistic regression can reliably discriminate between spam and non-spam emails while addressing common analytical challenges such as:

- High dimensionality
- Multicollinearity among predictors
- Outlier presence
- Class imbalance
- Model interpretability

This project integrates statistical inference with predictive modeling to produce transparent, high-performing classification models suitable for real-world decision support.

---

## Quick Start

This repository is organized as a notebook-driven analysis focused on feature engineering, model comparison, and evaluation.

To explore the full workflow locally:

```bash
pip install -r requirements.txt
jupyter notebook notebooks/spam_email_classifier.ipynb
```

The notebook walks through data preparation, exploratory analysis, feature extraction, logistic regression modeling, and evaluation.

---

## Repository Structure

```
spam-classification/
├── README.md
├── data/
├── notebooks/
│   └── spam_email_classifier.ipynb
├── report/
│   └── Classifying Email as Spam or Not Spam.pdf
├── src/
│   └── (reserved for modularized preprocessing and modeling logic)
├── requirements.txt
├── .gitignore
└── LICENSE
```

The notebook serves as the primary narrative artifact, combining exploratory data analysis, feature engineering, model development, and evaluation.

The src/ directory is reserved for extracting reusable components as the project evolves.

---

## Methodology

### 1. Data Preparation

- Examined distributions, summary statistics, and variable types
- Identified and addressed outliers using log-transformations where appropriate
- Standardized predictors to account for differing measurement scales
- Split the dataset into training and testing partitions

### 2. Exploratory Data Analysis

- Investigated predictor correlations and identified strong multicollinearity among frequency-based variables
- Examined class proportions (spam ≈ 39%)
- Visualized distributions and identified influential predictors

### 3. Logistic Regression Models

A sequence of logistic regression models was developed and compared:

- Full logistic regression model including all predictors
- Reduced model after removing highly correlated variables
- PCA-based logistic regression retaining components explaining approximately 90% of variance
- Regularized logistic regression using L1 (Lasso) and L2 (Ridge) penalties

### 4. Model Evaluation

Models were evaluated using:

- Accuracy
- Precision, recall, and F1 score
- Confusion matrix
- ROC curve and AUC

Final model performance:

- Accuracy: ~93.5%
- ROC AUC: 0.975
- Balanced performance across classes with reduced false positives and false negatives

Evaluation focused not only on performance metrics but also on model stability and interpretability.

---

## Key Findings

- Word and character frequency features are strong indicators of spam likelihood
- Logistic regression performs well in high-dimensional settings when supported by normalization and multicollinearity mitigation
- PCA reduces noise and collinearity while preserving predictive performance
- Regularization improves coefficient stability and interpretability

---

## Limitations

- The Spambase dataset reflects older email behaviors; modern spam detection may require more sophisticated models
- Logistic regression assumes linear log-odds relationships, which may not fully capture complex email patterns
- Ensemble and tree-based methods (e.g., Random Forests, Gradient Boosting) may provide stronger nonlinear performance

---

## Outcome

This project demonstrates the effectiveness of logistic regression for email spam classification while highlighting best practices in preprocessing, dimensionality reduction, multicollinearity handling, and model validation.

The workflow emphasizes interpretability and analytical judgment over purely performance-driven model selection.
