# Health-Care-Premium-Prediction

## Project Statement
AtliQ AI has partnered with Shield Insurance to develop a predictive machine learning model to estimate health insurance premiums based on factors such as age, smoking habits, BMI, and medical history. The goal is to build a robust and accurate model that helps in premium estimation and risk assessment.

## Data Cleaning
Detected outliers using box plot visualizations and IQR (Interquartile Range) method.

Checked for duplicate rows and missing (NA) values.

Dropped NA values where missing count was below 15.

## EDA
Univariate and Bivariate Analysis:

Numerical columns:

Explored distribution using histograms and KDE plots.

Analyzed relationships with the Annual Premium Amount using scatter plots and correlation matrices.

Categorical columns:

Conducted  univarate analysis using (bar plots).

Analyzed relationships using cross tabs by displaying the distribution of one variable across the categories of another 

## Feature Engineering
Applied domain-based ordinal encoding with aggregation for medical history column 

Encoded text columns numerically.

Used One-Hot Encoding for nominal categorical features.

## Feature Selection
Examined feature correlation to drop irrelevant columns.

Scaled numerical features using Min-Max Scaler.

Applied Variance Inflation Factor (VIF) to detect multicollinearity and retained optimal features.

## Model Training
Linear Regression: Achieved an accuracy of ~92%.

Ridge Regression: Also yielded ~92% accuracy.

XGBoost Regressor: Improved accuracy significantly to ~98%.

## Hyperparameter Tuning
Used RandomizedSearchCV to optimize XGBoost parameters.

Despite parameter tuning, the model consistently achieved 98% accuracy, indicating robustness.

## Error Analysis
Conducted error analysis on prediction results.

Identified age as a significant contributor to prediction error.

Specifically, individuals under 25 showed the highest error rates.

Decided to segment the data based on age for better performance.

## Data Segmentation
To address the model’s higher error rate for younger individuals, two separate models were created:

Model A: Age ≤ 25
Trained on individuals under 25 using the notebook ml_premium_health_insurance_prediction_young.

Introduced genetic factor as an additional feature.

Retrained model (ml_premium_health_insurance_prediction_young_with_gr) significantly improved performance with this feature.

Model B: Age > 25
Trained on individuals over 25 using ml_premium_health_insurance_prediction_rest_with_gr.

Also included genetic factor data, leading to improved performance and generalization.

## Outcome
Successfully built segmented predictive models for health insurance premium estimation with 98% accuracy in both groups.

Used XGBoost for individuals over 25 and Linear Regression for individuals under 25  both achieved similar high performance after segmentation.

Identified age as a major source of error, and addressed it by creating separate models for different age groups.



## Conclusion
Incorporating domain-specific features like genetic factors significantly enhanced model performance.

Segmenting data by age helped address error disparities and improved prediction accuracy for the under-25 group.

More high-quality, relevant data directly contributes to better model training and more accurate premium predictions.












