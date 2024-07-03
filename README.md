# Credit Card Fraud Detection

## Problem Statement

Credit card fraud is the unauthorized use of someone else's credit card or credit card information to make purchases or withdraw cash. It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase. The dataset used in this project contains transactions made by credit cards in September 2013 by European cardholders. This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly imbalanced, with the positive class (frauds) accounting for 0.172% of all transactions.

## Introduction

This project aims to build a classification model to predict whether a credit card transaction is fraudulent. The dataset contains transactions made by European cardholders in September 2013.

## Project Structure

- `data_preprocessing.ipynb`: Jupyter notebook for data loading, preprocessing, and visualization.
- `model_deployment.ipynb`: Jupyter notebook for model training, evaluation, and saving the best model.
- `models`: Directory containing the saved model files.
- `visuals`: Directory containing visualization files.
- `data`: Directory containing the train and test datasets.
- `README.md`

Ensure all dependencies are installed: 
 
    pip install -r requirements.txt

## Data Preprocessing

1. **Loading and Exploring the Dataset**
    - Loaded the dataset from `creditcard.csv`.
    - Displayed the first few rows and summary statistics.

2. **Exploratory Data Analysis (EDA)**
    - Analyzed the data using various visualizations.
    - Identified patterns and relationships in the data.

3. **Handling Class Imbalance**
    - Used SMOTE to balance the dataset.
    - Performed undersampling for comparison.

4. **Feature Scaling**
    - Scaled the 'Amount' feature using StandardScaler.

5. **Train/Test Split**
    - Split the data into training and testing sets.

## Model Training and Evaluation

1. **Training Multiple Models**
    - Trained Logistic Regression, Random Forest, Decision Tree, and XGBoost models.
    - Performed hyperparameter tuning using RandomizedSearchCV.

2. **Model Evaluation**
    - Evaluated models using accuracy, precision, recall, F1 score, and AUC-ROC.
    - Selected the Random Forest model as the best-performing model.

3. **Saving the Model**
    - Saved the best-tuned Random Forest model to a `.pkl` file for future use.

## Usage

### Saving the Model

After training and tuning the best model, save it using the following code:

```python
import pickle
from sklearn.ensemble import RandomForestClassifier

# Assuming best_rf_over is your best-tuned Random Forest model
best_rf_over = randomized_search(RandomForestClassifier(), rf_param_grid, X_train_over, y_train_over)

# Save the best model to a .pkl file
model_path = 'models/best_random_forest_model.pkl'
with open(model_path, 'wb') as file:
    pickle.dump(best_rf_over, file)

print(f"Model saved to {model_path}")
