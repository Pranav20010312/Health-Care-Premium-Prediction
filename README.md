# 🏥 Health Care Premium Prediction

## 📌 Project Statement  
AtliQ AI partnered with Shield Insurance to develop a machine learning model that predicts health insurance premiums based on factors such as age, smoking habits, BMI, and medical history. The goal was to create a robust and accurate model to assist in premium estimation and risk assessment.

---

## 🧰 Technologies & Tools Used  
- Python  
- Pandas, NumPy – Data manipulation  
- Matplotlib, Seaborn – Visualization  
- Scikit-learn – To build Machine Learning Models  
- XGBoost – Gradient boosting model  
- Statsmodels – VIF calculation for multicollinearity detection  

---

## 🧪 Project Workflow  

### 1. 🧹 Data Cleaning  
- Detected outliers using box plots and IQR (Interquartile Range).  
- Checked for duplicates and missing (NA) values.  
- Dropped missing values where the count was below 15.

### 2. 📊 Exploratory Data Analysis (EDA)  
- **Numerical variables:**  
  - Analyzed distributions using histograms and KDE plots.  
  - Explored relationships with the target variable (Annual Premium Amount) through scatter plots and correlation matrices.  
- **Categorical variables:**  
  - Performed univariate analysis with bar plots.  
  - Analyzed relationships via crosstabs to understand category distributions.

### 3. 🛠️ Feature Engineering  
- Applied domain-based ordinal encoding with aggregation for the medical history column.  
- Encoded text columns numerically.  
- Used One-Hot Encoding for nominal categorical features.

### 4. 🎯 Feature Selection  
- Dropped irrelevant or redundant features based on correlation analysis.  
- Scaled numerical features using Min-Max Scaler.  
- Applied Variance Inflation Factor (VIF) to detect and remove multicollinearity.

### 5. 🤖 Model Training  
- Trained multiple models:  
  - Linear Regression (~92% accuracy)  
  - Ridge Regression (~92% accuracy)  
  - XGBoost Regressor (~98% accuracy)  

### 6. 🔧 Hyperparameter Tuning  
- Used RandomizedSearchCV to tune XGBoost parameters.  
- Model performance remained stable at ~98% accuracy, indicating robustness.

### 7. 📉 Error Analysis & Data Segmentation  
- Found that age was a key factor driving prediction errors, particularly for individuals under 25.  
- Decided to segment the data:  
  - **Model A:** For individuals aged ≤ 25, trained with additional genetic factor features, significantly improving performance.  
  - **Model B:** For individuals aged > 25, also included genetic data for better generalization.

---

## 📈 Results  
- Developed **segmented predictive models** achieving 98% accuracy for both age groups.  
- Utilized **XGBoost** for individuals over 25 and **Linear Regression** for those under 25, with both models performing comparably well post-segmentation.  
- Successfully reduced prediction errors by age-based segmentation and inclusion of domain-specific features such as genetic factors.

---

## 💡 Conclusion  
- Incorporating domain-specific features like genetic factors significantly improved model accuracy.  
- Segmenting data by age effectively addressed error disparities, particularly for the younger population.  
- Availability of more high-quality and relevant data will further enhance premium prediction accuracy and model robustness.

---

## 💼 Business Impact  
- Enables **accurate and personalized health insurance premium calculations**.  
- Helps Shield Insurance **reduce underwriting risks and improve decision-making**.  
- Automates premium estimation, reducing **manual effort and errors**.  
- Supports **customer segmentation** for tailored insurance offerings and better service.

---















