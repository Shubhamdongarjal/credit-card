# Models Directory

This directory contains the saved machine learning models.

## Saved Models

- `best_random_forest_model.pkl`: The best-tuned Random Forest model for predicting fraudulent credit card transactions.

## Usage

To load and use the saved model, use the following code:

python
import pickle

# Load the model from the .pkl file
model_path = 'models/best_random_forest_model.pkl'
with open(model_path, 'rb') as file:
    loaded_rf_model = pickle.load(file)

# Use the loaded model for predictions
predictions = loaded_rf_model.predict(X_test_over)
