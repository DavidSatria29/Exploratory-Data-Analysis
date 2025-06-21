# Exploratory Data Analysis and Hypothesis Testing on Heart Attack Prediction

This repository contains the capstone project for the IBM course "Exploratory Data Analysis and Hypothesis Testing." The project performs a comprehensive analysis of a heart attack prediction dataset from Indonesia, sourced from Kaggle. The primary objective is to meticulously clean the data, uncover patterns through visualization, and use statistical testing to select the most significant features for building a potential predictive model.

---

### Methodology

The project follows a structured data analysis workflow:

* **Data Cleaning**: The initial phase involved a rigorous data cleaning pipeline. [cite_start]Missing values in the `alcohol_consumption` column were strategically imputed with 'Low' to maintain the feature's ordinal nature. [cite_start]Outliers in numerical columns were systematically identified using the **Interquartile Range (IQR)** method and removed to prevent them from skewing the analysis. [cite_start]The dataset was also verified to be free of duplicate entries.

* **Exploratory Data Analysis (EDA)**: The distributions of all features were visualized to understand their characteristics. [cite_start]Histograms and KDE plots were used for continuous variables, revealing that most were normally distributed, while `sleep_hours` and `fasting_blood_sugar` were skewed. [cite_start]Count plots were used to examine the balance of categorical features.

* **Feature Selection & Engineering**: Feature selection was driven by statistical correlation tests. [cite_start]The **Point-Biserial correlation** was calculated for continuous features against the `heart_attack` target , while the **Chi-Square test** and **Cramér's V** (with a threshold of V ≥ 0.1) were used for categorical features. The resulting selected features were then prepared for modeling. This involved **one-hot encoding** for categorical columns like `region` and `smoking_status` [cite: 105, 107][cite_start], and applying a **log transformation** to the `fasting_blood_sugar` feature to normalize its distribution.

* [cite_start]**Hypothesis Testing**: A final round of hypothesis testing was conducted to evaluate features that did not pass the initial selection phase[cite: 118]. [cite_start]An **independent t-test** was performed on `sleep_hours` , a **Chi-Square test** on `income_level` [cite: 130, 132][cite_start], and **logistic regression** on `physical_activity`. [cite_start]None of these tests yielded a statistically significant result (p < 0.05), so these features were not included in the final dataset.

---

### Conclusion

This project successfully transforms a raw dataset into a clean, feature-engineered dataset ready for machine learning. [cite_start]The analysis concludes that key features for predicting heart attacks include `age`, `cholesterol_level`, `waist_circumference`, `fasting_blood_sugar`, `region`, `hypertension`, `diabetes`, `obesity`, `smoking_status`, and `previous_heart_disease`. [cite_start]The next logical step is to use this refined data to build and evaluate predictive models, such as Logistic Regression, Random Forest, or XGBoost, to assess heart attack risk.
