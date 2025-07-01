# 💳 Viva-Credit Default Prediction

## 📌 Project Overview  
This project, developed by Harshit Arora (DS/AIML Batch-1), aims to predict the likelihood of credit card default for Viva-Credit, a Romania-based credit card issuer ([vivacredit.ro](https://vivacredit.ro)).  
Using a dataset of 30,000 customers with 24 variables (demographic, credit, payment history, and bill statements from April to September 2005), the analysis identifies key drivers of default to inform credit approval and limit decisions, enhancing strategic planning and targeted product offerings.

---

## 🧭 Table of Contents  
- [Problem Statement](#problem-statement)  
- [Dataset](#dataset)  
- [Project Structure](#project-structure)  
- [Methodology](#methodology)  
- [Results](#results)  
- [Conclusion](#conclusion)  
- [Author](#author)

---

## ❓ Problem Statement  
Viva-Credit seeks to predict customer default likelihood and identify influencing factors to optimize credit card issuance and limits. The goal is to improve decision-making and tailor future credit products based on insights from historical data.

---

## 📊 Dataset  
The dataset (`viva_credit.csv`) includes:

- ID: Unique customer identifier  
- LIMIT_BAL: Credit limit  
- SEX: Gender (1 = Male, 2 = Female)  
- EDUCATION: Education level (0–6)  
- MARRIAGE: Marital status (0–3)  
- AGE: Age in years  
- PAY_0 to PAY_6: Repayment status (April to September 2005)  
- BILL_AMT1 to BILL_AMT6: Bill amounts (April to September 2005)  
- PAY_AMT1 to PAY_AMT6: Payment amounts (April to September 2005)  
- default.payment.next.month: Target variable (0 = No default, 1 = Default)

> ℹ️ Note: No missing values were detected in the dataset.

---

## 🗂 Project Structure  
- 📓 `Mini_Project_3_Viva_Credit_Harshit_Arora.ipynb`:  
  Main Jupyter notebook containing full data analysis and modeling.

- 📁 `viva_credit.csv`:  
  Dataset used for modeling (not included in the repository; users must provide their own copy).

- 📄 `README.md`:  
  This file — providing an overview of the project.

---

## 🧪 Methodology  

### 📥 Data Loading  
- Loaded the dataset using pandas  
- Used `.head()`, `.info()`, `.describe()` to understand structure and summary stats  

### 🧹 Data Preparation  
- Split data into features (X) and target (y)  
- Performed train-test split (80/20) with `random_state=42`  
- Applied `StandardScaler` for feature normalization  

### 🤖 Model Training  
- Trained Logistic Regression models on both unscaled and scaled data  

### 📈 Evaluation  
- Evaluated models using:
  - Accuracy
  - Precision
  - Recall
  - F1-Score
  - AUC-ROC

---

## ✅ Results  

### ⚙️ Logistic Regression Results  
- Unscaled Accuracy: 0.7812  
- Scaled Accuracy: 0.8098  
- Precision: 0.6928  
- Recall: 0.2353  
- F1-Score: 0.3513  
- AUC-ROC: 0.7271

### 🔍 Key Drivers  
- PAY_0 (most significant coefficient) strongly predicts default  
- Higher BILL_AMT1 → higher default risk  
- Higher PAY_AMT1 and PAY_AMT2 → reduce default risk

### 🥇 Comparison: Gradient Boosting  
- AUC-ROC: 0.7832  
- Accuracy: 0.8205  
- F1-Score: 0.4634

---

## 🧾 Conclusion  
The scaled Logistic Regression model improved accuracy to 80.98%, with PAY_0 emerging as the strongest predictor of default.  
However, Gradient Boosting outperformed all models, achieving:

- 82.05% Accuracy  
- 0.4634 F1-Score  
- 0.7832 AUC-ROC

### 💡 Recommendations  
- Use Gradient Boosting as the production model  
- Explore further feature engineering to improve recall  
- Consider real-time monitoring of key variables like PAY_0 and recent payment behavior for credit decisioning

---

## 👨‍💻 Author  
**Harshit Arora**  
B.Tech CSE Student, Sharda University
