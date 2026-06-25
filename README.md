# California Housing Price Prediction

This project demonstrates a complete workflow for predicting housing prices in California using machine learning techniques. The workflow includes data exploration, preprocessing, feature engineering, model training, evaluation, and hyperparameter tuning.

## Table of Contents

- [Overview](#overview)
- [Dataset](#dataset)
- [Project Steps](#project-steps)
  - [Data Exploration & Visualization](#1-data-exploration--visualization)
  - [Data Preprocessing](#2-data-preprocessing)
  - [Feature Engineering](#3-feature-engineering)
  - [Model Training & Evaluation](#4-model-training--evaluation)
  - [Hyperparameter Tuning](#5-hyperparameter-tuning)
  - [Final Evaluation](#6-final-evaluation)
- [Results](#results)
- [Requirements](#requirements)
- [Usage](#usage)
- [References](#references)

## Overview

The goal is to predict the median house value in various districts of California based on features such as location, population, median income, and proximity to the ocean. The project uses Python libraries like pandas, NumPy, matplotlib, seaborn, and scikit-learn for data analysis and modeling.

## Dataset

- **Source:** California housing dataset (`housing.csv`)
- **Features:**
  - longitude, latitude
  - housing_median_age
  - total_rooms, total_bedrooms
  - population, households
  - median_income
  - ocean_proximity (categorical)
- **Target:** median_house_value

## Project Steps

### 1. Data Exploration & Visualization

- Loaded the dataset and examined its structure and summary statistics.
- Visualized distributions and relationships using histograms and scatter plots.
- Explored the effect of geographical features and ocean proximity on housing prices.
- Identified that `median_income` is a crucial feature, scaled to $10,000 and capped at both ends.

### 2. Data Preprocessing

- Split the data into training and test sets using stratified sampling based on income categories to ensure representative splits.
- Handled missing values in `total_bedrooms` by imputing the median.
- Encoded categorical features (`ocean_proximity`) using one-hot encoding to avoid introducing ordinal relationships.
- Standardized numerical features using `StandardScaler` for improved model performance.

### 3. Feature Engineering

- Created new features:
  - `rooms_per_household`
  - `bedrooms_per_room`
  - `population_per_household`
- Analyzed feature correlations to target variable (`median_house_value`).

### 4. Model Training & Evaluation

- Trained multiple models:
  - Linear Regression
  - Decision Tree Regressor (noted overfitting)
  - Random Forest Regressor (best performance)
- Evaluated models using Root Mean Squared Error (RMSE) and cross-validation for robust performance estimates.

### 5. Hyperparameter Tuning

- Used `GridSearchCV` to tune Random Forest parameters (number of estimators, max features, bootstrap).
- Identified best parameters and analyzed feature importances.

### 6. Final Evaluation

- Built a full pipeline for preprocessing and prediction.
- Evaluated the final model on the test set using metrics: MAE, RMSE, and R²-score.

## Results

- **Best Model:** Random Forest Regressor with hyperparameter tuning.
- **Test Set Performance:**
  - Mean Absolute Error (MAE): ~33,359
  - Root Mean Squared Error (RMSE): ~49,731
  - R²-score: 81.02%
- **Key Insights:**
  - Median income is the most influential feature.
  - Some engineered features and ocean proximity categories provide additional value.
  - Decision Trees tend to overfit; ensemble methods like Random Forests generalize better.

## Requirements

- Python 3.x
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Usage

1. Clone the repository and place `housing.csv` in the working directory.
2. Run the notebook or script to reproduce the workflow.
3. Modify or extend the pipeline for further experimentation or deployment.

## References

- Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow (Aurélien Géron)
- California Housing Dataset (StatLib)

*This project is a comprehensive example of the end-to-end machine learning process, from data exploration to model deployment-ready evaluation.*