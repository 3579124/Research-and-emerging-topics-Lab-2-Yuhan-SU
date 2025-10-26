# Research-and-emerging-topics-Lab-2-Yuhan-SU
GIST Steel Plant Production Prediction
Overview

This project focuses on predicting plant-level steel production using a combination of plant operational and environmental features. The goal is to provide actionable insights to steel plant managers, optimize production efficiency, and demonstrate a full machine learning lifecycle, including data cleaning, feature engineering, modeling, evaluation, hyperparameter tuning, deployment planning, and monitoring.

Dataset
Source: GIST Steel Dataset
Key Columns:
Plant ID, Plant Name, Owner, Location
Plant age (years), Workforce size
Steel product capacities:
Ferronickel capacity (ttpa)
Sinter plant capacity (ttpa)
Coking plant capacity (ttpa)
Pelletizing plant capacity (ttpa)
Certifications: ISO 14001, ISO 50001, ResponsibleSteel
Main production equipment, Power source, Iron ore and Met coal sources
Target Variable:
Total capacity (ttpa) — calculated as the sum of all plant capacities.

Data Cleaning & Preprocessing
Replaced non-numeric entries ('unknown', 'N/A', '>0', etc.) in numerical columns with NaN, then imputed with mean or median where appropriate.
Converted all numeric columns to proper data types.
Checked and corrected outliers for extreme capacity values.
Feature-engineered:
Capacity per worker: total production / workforce size
ISO Certification flag: binary indicator if plant has ISO 14001 or ISO 50001
Encoded categorical variables using LabelEncoder.
Standardized numeric features with StandardScaler.

Feature Engineering & Analysis
Created new meaningful features capturing operational efficiency.
Explored correlations between features and production to identify redundant predictors.
Visualized correlations using heatmaps for linear relationships.

Modeling
Baseline Model: Mean predictor of production to establish a simple reference.
Linear Regression: Multiple linear regression trained on key plant variables.
Cross-Validation: K-Fold (K=5) used to evaluate model stability.
Model Comparison:
Linear Regression
Ridge Regression
Random Forest Regressor
Hyperparameter Tuning: RandomizedSearchCV applied to Random Forest to optimize performance.

Model Lifecycle
Tracking: MLflow used to log experiments, parameters, metrics, and artifacts.
Optimization: Optuna implemented to efficiently tune hyperparameters.
Storage: Best model saved using joblib for future predictions.

Deployment & Monitoring (Conceptual)
Deployment Options: REST API for real-time predictions or batch pipelines for periodic reporting.
Monitoring Metrics: RMSE, MAE, R², input data quality, and drift detection.

Model Drift Examples:
Data drift: Change in workforce distribution due to automation.
Concept drift: Change in relationship between ISO certification and production efficiency.

Reflection
Challenges: Feature engineering and handling non-standardized capacity data, and also for the training part. As for a student who didn't do a lot of coding before, everything's quite difficult.
Enhancements: Additional plant-level operational and environmental data could improve predictions.
Business Insights: Visualizations and feature importance analysis help translate model results into actionable recommendations.

