                                      Predictive Analysis of Diabetic Risk Factors Using Machine Learning
                                                              Project Overview
This project investigated diabetic risk factors using machine learning. The dataset contained 1,000 records and 14 variables covering demographic information, biochemical measurements and BMI.
I used Python to clean and explore the data, engineer and select features, address class imbalance using SMOTE, and develop classification models to predict three categories: Non-diabetic, Pre-diabetic and Diabetic.
Four models were compared: Random Forest, Logistic Regression, K-Nearest Neighbours (KNN), and Support Vector Classifier (SVC).
                                                                    Objective
The objective was to identify important variables associated with the diabetes classifications and compare machine learning models based on their predictive performance.
                                                                   Dataset
Key variables included:
Age
Urea
Creatinine
HbA1c
Cholesterol
Triglycerides
HDL
LDL
VLDL
BMI
Gender
Diabetes classification
                                                                   Methodology
The analysis followed these stages:
Data Quality Assessment – checked missing values, duplicates and categorical inconsistencies.
Data Cleaning – standardised gender and diabetes classification values.
Exploratory Analysis – examined distributions, outliers, class frequencies and feature relationships.
Feature Engineering – applied logarithmic transformations to numerical variables.
Feature Selection – used ReliefF to rank feature relevance.
Class Balancing – applied SMOTE to address class imbalance.
Model Development – trained four classification algorithms.
Model Evaluation – compared accuracy, precision, recall, F1 score and cross-validation performance.
Key Findings
ReliefF identified the highest-ranked features as:
                                                     Feature	Importance
HbA1c	28.97%
BMI	22.74%
Age	15.88%
Triglycerides	7.40%
Cholesterol	6.13%
Gender, HDL and Creatinine were removed following feature selection.
Model Performance
Model	Precision	Recall	F1 Score
Random Forest	98.67%	98.67%	98.65%
KNN	93.35%	91.67%	91.50%
SVC	90.36%	93.00%	91.58%
Logistic Regression	90.98%	92.33%	91.54%
Random Forest performed best overall. In the main evaluation, it achieved 99.34% accuracy and a 98.68% cross-validation score.
                                                  Tools
Python | Pandas | NumPy | Matplotlib | Seaborn | Scikit-learn | SMOTE | ReliefF | Jupyter Notebook

                                                 Limitations
The dataset contains 1,000 records, so further testing on larger and independent datasets would be needed to assess generalisability.
The high model performance also requires further validation, particularly to reduce the potential for data leakage when applying SMOTE and cross-validation.
This project is an analytical and machine-learning exercise and should not be interpreted as a clinical diagnostic system.
                                             Skills Demonstrated
Data cleaning and preprocessing
Exploratory data analysis
Feature engineering
Feature selection
Machine learning classification
Imbalanced data handling
Model evaluation
Python data analysis
Statistical visualisation
