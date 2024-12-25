# Credit Card Fraud Detection

## Overview
This repository contains a machine learning project aimed at detecting fraudulent credit card transactions. The dataset used is highly imbalanced, with legitimate transactions far outnumbering fraudulent ones. The project implements logistic regression and evaluates its performance to identify potential fraudulent activities.

## Dataset
The dataset consists of the following features:
- **Time**: Seconds elapsed between this transaction and the first transaction in the dataset.
- **V1, V2, ..., V28**: Principal components obtained using PCA to protect confidentiality.
- **Amount**: Transaction amount.
- **Class**: The target variable (0 = Legitimate, 1 = Fraudulent).

### Key Statistics
- **Legitimate Transactions**: 284,315
- **Fraudulent Transactions**: 492
- **Imbalance Ratio**: ~578:1

## Project Workflow
1. **Data Preprocessing**
   - Separate legitimate and fraudulent transactions.
   - Resample the data to handle class imbalance (e.g., undersampling legitimate transactions).
   - Scale features for better performance of the logistic regression model.

2. **Modeling**
   - Split the data into training and testing sets (80% training, 20% testing).
   - Train a logistic regression model to classify transactions.
   - Evaluate the model using appropriate metrics.

3. **Evaluation Metrics**
   - Accuracy
   - Precision
   - Recall
   - F1-Score
   - ROC-AUC

## Results
- **Training Accuracy**: 94.92%
- **Testing Accuracy**: 92.39%

While the model achieves high accuracy, additional metrics such as precision and recall provide better insights into its performance given the dataset's imbalance.

## Visualization
Key visualizations include:
- **Class Distribution**: Highlighting the imbalance between legitimate and fraudulent transactions.
- **ROC Curve**: Showing the trade-off between true positive and false positive rates.

## Future Work
- Implement advanced resampling techniques like SMOTE.
- Explore other machine learning algorithms such as Random Forest, XGBoost, or LightGBM.
- Use hyperparameter tuning to improve model performance.
- Add feature importance analysis to understand which variables are most predictive of fraud.

## How to Use
1. Clone this repository:
   ```bash
   git clone https://github.com/shashank274/CreditCard_Fraud_Detection.git
## Install the required Libraries:
   ```bash
   pip install -r requirements.txt




