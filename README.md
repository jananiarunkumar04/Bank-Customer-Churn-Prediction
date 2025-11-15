# Bank-Customer-Churn-Prediction


## **Overview**

This project focuses on predicting whether a bank customer is likely to churn using machine learning. Churn prediction is an important problem in retail banking because retaining existing customers is generally more cost-effective than acquiring new ones. The model aims to flag customers who show signs of leaving so that the bank can take timely retention measures.

The work includes data preprocessing, exploratory analysis, handling class imbalance, model training, evaluation, and interpretation.

---

## **Dataset Description**

The dataset contains basic demographic and financial details of customers.
The key fields are:

* **credit_score**
* **country**
* **gender**
* **age**
* **tenure**
* **balance**
* **products_number**
* **credit_card**
* **active_member**
* **estimated_salary**
* **churn** (target)

These variables commonly influence customer behaviour in banking environments.

---

## **Model Used: XGBoost**

A gradient boosting model (**XGBoost**) is used for prediction.
Reasons for choosing XGBoost:

1. Performs well on structured, tabular financial data.
2. Handles non-linear relationships between customer features and churn behaviour.
3. Works effectively with imbalanced datasets when combined with SMOTE.
4. Provides clear feature importance, and supports SHAP for interpretation.
5. Widely used in real banking and financial analytics applications such as risk scoring and customer retention modelling.

The goal is not only to achieve good accuracy but also to understand *why* the model predicts churn, which is essential for decision-making in financial roles.

---

## **Project Steps**

### 1. Data Preparation

* Removed the non-informative **customer_id** column.
* Encoded categorical features (country, gender).
* Checked for missing values.
* Split dataset into features and target.

### 2. Exploratory Data Analysis

* Examined churn distribution.
* Analysed numerical and categorical feature behaviour.
* Plotted correlations to understand relationships among variables.

### 3. Class Imbalance Handling

The dataset had fewer churned customers compared to non-churned ones.
To avoid biased predictions, **SMOTE** was applied to oversample the minority class.

### 4. Model Training

An XGBoost classifier was trained with tuned parameters to balance accuracy and generalization.
The model was trained on the resampled dataset with an 80/20 train-test split.

### 5. Evaluation

Model performance was assessed using:

* Accuracy
* Precision
* Recall
* F1-score
* ROC-AUC

In addition, a metrics bar plot and confusion matrix were generated for quick comparison.

### 6. Interpretation

Feature importance charts and SHAP summary plots were used to understand which factors influence churn the most.
This helps convert raw model output into business-oriented insights.

---

## **Key Findings**

From the model and SHAP analysis, the factors most associated with churn include:

* Lower tenure
* Higher balance but limited engagement
* Lower credit score
* Fewer products
* Inactive membership status

These patterns suggest possible areas for targeted retention interventions such as product recommendations, loyalty programs, or personalised communication.

---

## **Technologies Used**

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Scikit-learn
* XGBoost
* imbalanced-learn (SMOTE)
* SHAP

---

## **Running the Project**

Install the required libraries:

```
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn xgboost shap
```

After installation, run the script or notebook containing the workflow.

---

## **Future Work**

* Building a simple API for scoring new customers.
* Creating a dashboard (Power BI / Tableau) to display churn risk and driver analysis.
* Including customer segmentation alongside churn risk.
* Testing other models such as LightGBM or Logistic Regression for comparison.

---

## **Conclusion**

The model provides a structured approach to predicting customer churn and understanding the factors contributing to it.
The workflow and interpretation techniques used here align closely with real financial analytics practices, especially in customer retention and risk-focused roles.

---

