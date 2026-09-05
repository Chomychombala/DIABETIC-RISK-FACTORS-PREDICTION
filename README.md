                                   Predictive Analysis of Diabetic Risk Factors Using Machine Learning
Project Overview
This project used machine learning to classify individuals into three diabetes-related categories: Non-diabetic, Pre-diabetic and Diabetic.
The project began with a dataset containing 1,000 records and 14 variables covering demographic information, biochemical measurements and body mass index (BMI).
Using Python and machine learning libraries, I performed data quality checks, exploratory data analysis, feature engineering, transformation and feature selection before training and evaluating several classification models.
Four machine learning algorithms were compared:
Random Forest
Logistic Regression
Support Vector Classifier (SVC)
K-Nearest Neighbours (KNN)
The models were evaluated using accuracy, precision, recall, F1 score and cross-validation performance.
The aim was to determine which model provided the strongest classification performance on the prepared dataset.
Project Objective
The objective was to develop and compare machine learning classification models for identifying diabetes-related classes from demographic and biochemical features.
The project focused on:
Understanding the structure of the dataset.
Assessing data quality.
Exploring the distribution of variables.
Identifying categorical inconsistencies.
Creating cleaned categorical variables.
Investigating numerical feature distributions.
Examining relationships between numerical variables.
Applying logarithmic transformations.
Selecting relevant features.
Encoding categorical variables.
Addressing class imbalance using SMOTE.
Training multiple classification algorithms.
Evaluating model performance.
Comparing the models using multiple evaluation metrics.
Dataset
The dataset contains 1,000 records and 14 original variables.
The variables include demographic information and biochemical measurements.
Variables
Variable	Description
ID	Record identifier
No_Pation	Patient identifier
Gender	Gender
AGE	Age
Urea	Urea measurement
Cr	Creatinine measurement
HbA1c	HbA1c measurement
Chol	Cholesterol measurement
TG	Triglycerides measurement
HDL	High-density lipoprotein
LDL	Low-density lipoprotein
VLDL	Very-low-density lipoprotein
BMI	Body mass index
CLASS	Original classification
The original classification contained three categories represented by:
N — Non-diabetic
P — Pre-diabetic
Y — Diabetic
Tools & Technologies
Tool / Library	Purpose
Python	Data preparation and machine learning
Pandas	Data manipulation
NumPy	Numerical operations
Matplotlib	Data visualisation
Seaborn	Statistical visualisation
Scikit-learn	Machine learning and model evaluation
Imbalanced-learn	SMOTE class balancing
ReliefF	Feature selection
Jupyter Notebook	Analysis and experimentation
Machine Learning Workflow
The project followed these stages:
1. Data Understanding
Reviewed the dataset structure, data types, descriptive statistics and variables.
2. Data Quality Assessment
Checked for missing values, null values and duplicate records.
3. Data Cleaning
Standardised inconsistent categorical values.
4. Exploratory Data Analysis
Examined distributions, class frequencies, outliers and relationships between numerical variables.
5. Feature Engineering
Created cleaned categorical variables and transformed numerical features.
6. Feature Selection
Used ReliefF to assess feature relevance and remove lower-ranked features.
7. Data Preparation
Encoded categorical variables and separated input features from the target variable.
8. Class Balancing
Applied SMOTE to address class imbalance.
9. Model Training
Trained four classification algorithms.
10. Model Evaluation
Compared model performance using accuracy, precision, recall, F1 score and cross-validation.
1. Data Understanding
The dataset was imported into Python using Pandas.
Initial inspection showed:
1,000 records
14 original variables
8 floating-point variables
4 integer variables
2 categorical variables
Descriptive statistics were also calculated to understand the central tendency and spread of the numerical variables.
The dataset included measurements such as age, urea, creatinine, HbA1c, cholesterol, triglycerides, HDL, LDL, VLDL and BMI.
2. Data Quality Assessment
Several data-quality checks were performed.
Missing Values
The dataset was checked for missing values using Pandas.
The assessment showed no missing values across the original 14 variables.
Duplicate Records
The dataset was also checked for duplicate records.
No duplicated records were identified through the duplicate-record check.
Categorical Consistency
The categorical variables required additional inspection.
The Gender variable contained:
F
M
f
The classification variable contained:
N
N
P
Y
Y
The additional spaces and inconsistent capitalisation were standardised before modelling.
3. Feature Engineering
Two cleaned variables were created from the original categorical fields.
Gender
The gender values were converted to a consistent format so that:
f became F
F remained F
M remained M
The resulting variable contained only:
F
M
Diabetes Classification
The original class values were cleaned by removing unnecessary whitespace and mapping the codes to descriptive categories:
Original Code	New Category
N	Non-diabetic
P	Pre-diabetic
Y	Diabetic
The original uncleaned categorical variables were then removed.
4. Exploratory Data Analysis
Exploratory analysis was performed to understand the characteristics of the dataset before modelling.
Outlier Analysis
Box plots were used to inspect the numerical variables for potential outliers.
This provided a visual assessment of the spread and unusual values across the numerical features.
Categorical Variables
The distribution of gender was visualised using a pie chart.
The distribution of the three diabetes classes was examined using a count plot.
Numerical Variables
Kernel density plots were used to examine the distributions of:
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
The distributions were also examined by diabetes classification using histograms with class-level separation.
5. Feature Transformation
The numerical variables were examined for their distributions and transformed using logarithmic transformation.
Log-transformed versions were created for:
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
The transformed variables were then visualised to examine their distributions.
The original numerical variables were subsequently removed from the modelling dataset, leaving the transformed versions as model inputs.
6. Correlation Analysis
A correlation matrix was generated to examine relationships between the numerical features.
The correlation heatmap provided a visual overview of the strength and direction of relationships between the transformed variables.
This formed part of the feature-selection process alongside the ReliefF analysis.
7. Feature Selection
ReliefF was used to estimate the relevance of the input features.
The feature importance results were:
Feature	Importance
HbA1c_log	28.97%
BMI_log	22.74%
AGE_log	15.88%
TG_log	7.40%
Chol_log	6.13%
LDL_log	4.40%
VLDL_log	4.35%
Urea_log	4.21%
Cr_log	3.25%
HDL_log	2.67%
Gender	0.00%
Based on this feature-ranking approach, the following variables were removed:
Gender
HDL_log
Cr_log
The remaining variables were used for the modelling stage.
8. Preparing the Machine Learning Dataset
The target variable was separated from the input features.
Target
The Class variable represented the outcome:
0 — Non-diabetic
1 — Pre-diabetic
2 — Diabetic
Input Features
The remaining selected numerical features were used as model inputs.
The data was also checked for infinite and missing values before modelling.
One missing value was identified in Chol_log.
This was handled before proceeding with model training.
9. Handling Class Imbalance
SMOTE (Synthetic Minority Over-sampling Technique) was applied to the dataset to address class imbalance.
The technique generated synthetic observations for the underrepresented classes.
The class distribution was visualised before and after applying SMOTE.
The resulting balanced dataset was then used for model development.
10. Model Development
Four classification algorithms were developed and evaluated.
Random Forest
A Random Forest classifier was trained using 1,000 trees.
The model achieved:
Accuracy: 99.34%
Precision: 99.35%
Recall: 99.34%
F1 Score: 99.34%
Cross-validation score: 98.68%
The confusion matrix showed very few classification errors, with five Diabetic observations classified as Non-diabetic.
Logistic Regression
Logistic Regression was trained as a linear classification baseline.
Results:
Accuracy: 91.84%
Precision: 92.26%
Recall: 91.84%
F1 Score: 91.88%
Cross-validation score: 89.34%
The model showed more classification errors between the three classes compared with Random Forest.
Support Vector Classifier
A linear Support Vector Classifier was also evaluated.
Results:
Accuracy: 94.87%
Precision: 95.05%
Recall: 94.87%
F1 Score: 94.86%
Cross-validation score: 92.11%
The SVC performed better than Logistic Regression but below Random Forest.
K-Nearest Neighbours
KNN was trained using three neighbours with distance-based weighting.
Results:
Accuracy: 98.03%
Precision: 98.08%
Recall: 98.03%
F1 Score: 98.01%
Cross-validation score: 93.29%
KNN achieved strong test performance, although Random Forest performed better overall.
11. Model Comparison
The final model comparison was based on precision, recall and F1 score.
Model	Precision	Recall	F1 Score
Random Forest	98.67%	98.67%	98.65%
Logistic Regression	90.98%	92.33%	91.54%
KNN	93.35%	91.67%	91.50%
SVC	90.36%	93.00%	91.58%
Random Forest produced the strongest results across the three reported metrics.
The earlier evaluation of the trained Random Forest also produced an accuracy of approximately 99.34%, with a cross-validation score of approximately 98.68%.
12. Key Findings
1. Data quality was generally good
The original dataset contained 1,000 complete records with no missing values and no duplicate records identified by the checks performed.
However, categorical inconsistencies were present and required cleaning.
2. HbA1c was the highest-ranked feature
The ReliefF feature-selection analysis ranked HbA1c_log as the most relevant feature, accounting for 28.97% of the calculated feature importance.
3. BMI and age were also highly ranked
BMI_log and AGE_log were the next two highest-ranked features, with importance scores of 22.74% and 15.88%, respectively.
4. Random Forest performed best
Across the model evaluation results, Random Forest produced the strongest overall performance.
It achieved approximately 99% accuracy in the main evaluation and outperformed the other three models in the final comparison.
5. KNN also performed strongly
KNN produced approximately 98% accuracy in the main evaluation, making it the second strongest model by test accuracy in that evaluation.
13. Model Evaluation
The models were assessed using multiple metrics rather than relying only on accuracy.
Accuracy
Measures the proportion of predictions that were correctly classified.
Precision
Measures how many observations predicted as a particular class were correctly classified.
Recall
Measures how many observations belonging to a class were correctly identified.
F1 Score
Provides a combined measure of precision and recall.
Cross-validation
Cross-validation was used to assess model performance across multiple data splits.
Confusion Matrix
Confusion matrices were generated to examine where classification errors occurred between:
Non-diabetic
Pre-diabetic
Diabetic
Using multiple evaluation measures provided a broader view of model performance.
14. Limitations
This project was developed as a machine learning classification exercise using the available dataset.
The results should not be interpreted as evidence that the model can be used as a clinical diagnostic system.
The dataset contains 1,000 records, so further testing on larger and independent datasets would be required before considering real-world application.
The very high performance observed from some models also warrants additional validation to assess how well the model generalises to unseen external data.
The modelling workflow could also be improved by applying preprocessing and SMOTE strictly within the training folds of cross-validation to reduce the possibility of data leakage.
15. Future Improvements
Potential improvements include:
Testing additional classification algorithms.
Performing systematic hyperparameter tuning.
Using stratified cross-validation.
Applying SMOTE only to training data within each validation fold.
Evaluating the models on an independent external dataset.
Examining ROC-AUC and precision-recall curves.
Investigating feature importance using additional methods.
Comparing models before and after feature selection.
Creating a reproducible machine-learning pipeline.
Developing a simple interface for demonstrating model predictions.
16. Project Structure
A suggested GitHub repository structure is:
diabetes-classification/
├── README.md
├── Diabetes.csv
├── notebooks/
│ └── diabetes_classification.ipynb
├── visualisations/
│ ├── distributions/
│ ├── correlation/
│ └── model_comparison/
└── requirements.txt
17. Skills Demonstrated
Data Analysis
Data profiling
Data-quality assessment
Exploratory data analysis
Outlier investigation
Correlation analysis
Feature engineering
Feature transformation
Feature selection
Machine Learning
Classification
Random Forest
Logistic Regression
Support Vector Classification
K-Nearest Neighbours
SMOTE
Train/test splitting
Cross-validation
Model comparison
Model Evaluation
Accuracy
Precision
Recall
F1 score
Confusion matrices
Cross-validation
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
Imbalanced-learn
ReliefF
Conclusion
This project demonstrates an end-to-end machine learning workflow, beginning with raw healthcare-related data and progressing through data quality assessment, exploratory analysis, feature engineering, transformation, feature selection, class balancing, model development and evaluation.
Four classification models were compared, with Random Forest producing the strongest overall performance among the models tested.
The feature-selection analysis also identified HbA1c, BMI and age as the highest-ranked features in the prepared dataset.
The project provided practical experience in using Python for data analysis and machine learning while demonstrating the importance of data preparation, feature selection and appropriate model evaluation.
