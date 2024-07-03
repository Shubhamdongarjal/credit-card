# Model Deployment Notebook

This notebook contains the model training, evaluation, and saving steps for the credit card fraud detection project.

## Steps Included

1. **Model Training**
    - Trained multiple models: Logistic Regression, Random Forest, Decision Tree, and XGBoost.
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
