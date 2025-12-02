# Spam Email Classification Using Logistic Regression

This project develops a statistical classification model to determine whether an email is spam or not spam using the UCI Spambase dataset.
The analysis applies a complete supervised machine learning workflow, including exploratory data analysis, feature diagnostics, dimensionality reduction, logistic regression modeling, and evaluation using multiple performance metrics.

Project Overview
----------------
The Spambase dataset contains 4,601 email observations and 57 numeric predictors representing word frequencies, character frequencies, and structural features of email messages.
The objective of this project is to determine whether logistic regression can reliably discriminate between spam and non-spam emails while addressing analytical challenges such as:

- High dimensionality
- Multicollinearity among predictors
- Outlier presence
- Class imbalance
- Model interpretability

This project integrates statistical inference and predictive modeling to produce interpretable, high-performing classification models.

Repository Structure
--------------------
spam-email-classification/
├─ Notebook - spam_email_notebook.ipynb
├─ Report - Spam Email Classification Using Logistic Regression.pdf
└─ README.md

File Descriptions
-----------------
- Notebook - spam_email_notebook.ipynb  
  Jupyter notebook containing preprocessing, EDA, PCA, logistic regression models, and evaluation metrics.

- Report - Spam Email Classification Using Logistic Regression.pdf  
  Written report describing methodology, results, interpretations, and limitations.

Methodology
-----------
1. Data Preparation
   - Examined distributions, summary statistics, and variable types.
   - Identified and addressed outliers through log-transformations where appropriate.
   - Standardized predictors due to varying measurement scales.
   - Split the dataset into training and testing partitions.

2. Exploratory Data Analysis
   - Investigated predictor correlations and detected strong multicollinearity among frequency-based variables.
   - Examined class proportions (spam ≈ 39%).
   - Visualized distributions and identified influential variables.

3. Logistic Regression Models
   A sequence of logistic regression models was developed:
   - Full logistic regression model including all predictors.
   - Reduced model after removing highly correlated variables.
   - PCA-based logistic regression, retaining principal components that explain ~90% of variance.
   - Regularized logistic regression using L1 (Lasso) and L2 (Ridge) penalties.

4. Model Evaluation
   Models were evaluated using:
   - Accuracy
   - Precision, recall, F1 score
   - Confusion matrix
   - ROC curve and AUC

   Final model performance:
   - Accuracy: ~93.5%
   - ROC AUC: 0.975
   - Balanced performance across classes with reduced false positives and false negatives.

Key Findings
------------
- Word and character frequency features are strong indicators of spam likelihood.
- Logistic regression performs well even in high-dimensional settings when supported by normalization and multicollinearity mitigation.
- PCA reduces noise and collinearity while preserving predictive performance.
- Regularization enhances model stability and interpretability.

Limitations
-----------
- The Spambase dataset reflects older email behaviors; modern spam detection may require more sophisticated models.
- Logistic regression assumes linear log-odds relationships, which may not fully capture complex email patterns.
- Ensemble and tree-based methods (e.g., Random Forests, Gradient Boosting) may provide stronger nonlinear performance.

Outcome
-------
This project demonstrates the effectiveness of logistic regression for email spam classification and provides a reproducible analytical workflow for supervised learning tasks.
The findings highlight best practices in data preprocessing, dimensionality reduction, multicollinearity handling, and model validation.

Author
------
Rania Hamid
GitHub: https://github.com/ranuyay
Portfolio: https://github.com/ranuyay/Public-Portfolio
