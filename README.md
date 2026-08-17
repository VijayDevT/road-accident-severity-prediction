Traffic Volume Prediction by Vehicle Type Overview This project implements a machine learning classification system to predict traffic level categories (Low, Medium, High) based on regional traffic data by vehicle type across UK regions from 1993 to 2025.

Dataset The model uses the region_traffic_by_vehicle_type.csv dataset containing traffic data for UK regions with the following features:

Features year: Year of data collection (1993-2025)

region_id: Unique identifier for each region

region_name: Name of the UK region (e.g., South West, London, Scotland)

region_ons_code: ONS region code

link_length_km: Road network length in kilometers

link_length_miles: Road network length in miles

pedal_cycles: Number of pedal cycle journeys

two_wheeled_motor_vehicles: Number of two-wheeled motor vehicles

cars_and_taxis: Number of cars and taxis

buses_and_coaches: Number of buses and coaches

LGVs: Number of Light Goods Vehicles

all_HGVs: Number of Heavy Goods Vehicles

all_motor_vehicles: Total motor vehicles

Target Variable traffic_level: Categorized into three levels based on all_motor_vehicles:

Low

Medium

High

Models Implemented Logistic Regression

Decision Tree

Random Forest

Gradient Boosting

Key Features Data Preprocessing: Handles missing values using median imputation

Feature Engineering: Creates categorical target variable through quantile-based binning

Encoding: Label encoding for categorical variables

Feature Scaling: StandardScaler for numerical features

Hyperparameter Tuning: GridSearchCV for Random Forest optimization

Cross-Validation: 5-fold cross-validation for robust evaluation

Requirements bash pip install numpy pandas scikit-learn matplotlib seaborn Installation bash

Clone the repository

git clone

Install dependencies

pip install -r requirements.txt Usage Prepare the dataset: Place region_traffic_by_vehicle_type.csv in the /content/ directory

Run the notebook: Execute all cells in the Jupyter notebook

Results:

Model performance metrics (Accuracy, Precision, Recall, F1-Score)

Confusion matrices for each model

Feature importance analysis

ROC-AUC scores

Model performance comparison visualizations

Model Performance Model Accuracy Logistic Regression 91.78% Decision Tree 98.63% Random Forest 98.63% Gradient Boosting 98.63% Feature Importance Top features contributing to traffic level prediction:

all_motor_vehicles (33.45%)

cars_and_taxis (26.20%)

all_HGVs (10.42%)

LGVs (9.40%)

two_wheeled_motor_vehicles (5.84%)

Cross-Validation Results Best Random Forest model achieved an average accuracy of 99.18% across 5-fold cross-validation.

Outputs Confusion Matrices: Visual representation of classification results

Feature Importance Plot: Bar chart showing feature significance

Model Comparison: Performance metrics across all models

ROC-AUC Score: Area Under the Curve for multi-class classification

Notes The dataset contains 363 records with no missing values

Traffic levels are determined by dividing total motor vehicles into three equal quantile groups

Random Forest with hyperparameter tuning (GridSearchCV) achieved the best performance

ROC-AUC score of 1.0 indicates excellent model discrimination

Future Enhancements Time series analysis for traffic trend prediction

Integration of external factors (weather, events)

Real-time traffic prediction system

Interactive dashboard for regional traffic analysis
