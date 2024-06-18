# Predicting Probabilities of XYZ and Seasonal Influenza Vaccination Uptake


# Overview

This project aims to predict the probabilities of individuals receiving XYZ and seasonal influenza vaccinations using machine learning models. The approach leverages a BaggingClassifier with XGBoostClassifier as the base estimator, addressing various data preprocessing challenges and evaluating model performance using ROC AUC scores.

# Model Used

The primary model employed in this project is a BaggingClassifier ensemble with XGBoostClassifier as the base estimator. This setup was chosen for its robustness in handling complex data relationships and potential class imbalances in the target variables.

# Key Points

- Data Preprocessing: 
  - Missing values in feature columns were tackled using `IterativeImputer` for numeric features and `SimpleImputer` for categorical features.
  - Categorical features were converted into numerical format using `One-Hot Encoding`.
  - Numerical features were normalized using `StandardScaler`.

- **Handling Class Imbalance**:
  - Given potential class imbalance in the target variables (`xyz_vaccine` and `seasonal_vaccine`), the `scale_pos_weight` parameter in XGBoostClassifier was adjusted to account for this during model training.

- **Model Training and Evaluation**:
  - Two separate models were instantiated using the BaggingClassifier ensemble with XGBoostClassifier as the base estimator for each target variable (`xyz_vaccine` and `seasonal_vaccine`).
  - Hyperparameters were fine-tuned using `RandomizedSearchCV` to optimize model performance.
  - Evaluation metrics included ROC AUC scores, providing a robust measure of model discrimination ability.

- **Results**:
  - **XYZ Vaccine Model**:
    - Mean ROC AUC Score: 0.8381
  - **Seasonal Vaccine Model**:
    - Mean ROC AUC Score: 0.8589
  - **Overall Performance**:
    - Combined ROC AUC Score: 0.8485

# Conclusion

The models demonstrated strong predictive performance, achieving competitive ROC AUC scores for both XYZ and seasonal influenza vaccination uptake prediction tasks. These results suggest that the applied machine learning approach effectively captures the underlying patterns in the data, providing valuable insights for public health decision-making and intervention strategies.
