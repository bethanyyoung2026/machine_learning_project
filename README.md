# 🏠 Housing Price Prediction with Machine Learning Pipelines

Welcome to my machine learning pipeline project on GitHub!

This repository houses a Python notebook that uses a scikit-learn pipeline to predict median house values from housing data. The project combines numerical and categorical preprocessing with Linear Regression in a single workflow, then explores hyperparameter selection using cross-validation.

---

## 📊 Project Overview

This project walks through the following machine learning workflow:
- Downloading and loading housing data
- Exploring numerical feature distributions
- Demonstrating transformation functions and a custom transformer
- Handling missing values and scaling numerical features
- Encoding categorical features
- Building a preprocessing and regression pipeline
- Generating predictions on a held-out test set
- Tuning a model parameter with cross-validation
- Comparing actual and predicted values
- Displaying the pipeline structure

The goal is to predict `median_house_value` using selected housing characteristics while keeping preprocessing and model training together in a reusable pipeline.

---

## 🧠 Skills Demonstrated

- Data manipulation using pandas and NumPy
- Data visualization with Matplotlib
- Missing-value imputation with SimpleImputer
- Numerical feature scaling with StandardScaler
- Categorical encoding with OneHotEncoder
- Combining column-specific transformations with ColumnTransformer
- Building workflows with scikit-learn Pipeline
- Training a LinearRegression model
- Hyperparameter selection using GridSearchCV
- Defining custom transformers with BaseEstimator and TransformerMixin

---

## 📁 Dataset

The notebook downloads a housing dataset archive from the `ageron/data` GitHub repository:

```text
https://github.com/ageron/data/raw/main/housing.tgz
```

The loading function:
1. Checks for `datasets/housing.tgz`.
2. Downloads and extracts the archive if it is not already present.
3. Loads `datasets/housing/housing.csv`.
4. Exports a copy as `housing_data.csv` in the working directory.

The dataset includes geographic coordinates, housing age, room and bedroom totals, population, household counts, median income, ocean proximity, and median house value.

### Features Used by the Model

| Type | Columns |
|------|---------|
| Numerical predictors | `total_rooms`, `households`, `median_income` |
| Categorical predictor | `ocean_proximity` |
| Prediction target | `median_house_value` |

Although the dataset contains additional columns, the ColumnTransformer selects only the four predictors listed above. Other columns are not passed to the model.
