# Student Performance Prediction – KNIME Analytics

An end-to-end data analytics project predicting student pass/fail outcomes from **6,607** records.  
Built in **KNIME Analytics Platform** with data cleaning, class balancing, model training, and evaluation.

## Student Performance Dashboard – KNIME
A complete workflow using **KNIME** to preprocess the *Student Performance Factors* dataset, engineer features, balance classes (SMOTE), and train multiple models (Decision Tree, Random Forest, Neural Network/MLP, Logistic Regression).  
Random Forest achieved the best validation accuracy (**91.09%**). Insights highlight the impact of **attendance** and **hours studied** on outcomes.

<img width="1030" height="555" alt="workflow" src="https://github.com/user-attachments/assets/e3d1b818-f2be-4821-91a6-a022e82a0b3f" />

---

## Project Links
- [View GitHub Repository](https://github.com/kwekud26/)
- [Kaggle Dataset – Student Performance Factors](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors)

---

## Table of Contents
- [Project Overview](#project-overview)  
- [Project Scope](#project-scope)  
- [Business Objective](#business-objective)  
- [Document Purpose](#document-purpose)  
- [Use Case](#use-case)  
- [Skills Demonstrated](#skills-demonstrated)  
- [Data Source](#data-source)  
- [Data Preparation & Processing](#data-preparation--processing)  
- [Model Training & Evaluation](#model-training--evaluation)  
  - [Decision Tree](#decision-tree--simple-explainable)  
  - [Random Forest](#random-forest--most-accurate-robust)  
  - [Neural Network (MLP)](#neural-network-mlp--captures-complex-patterns)  
- [Results & Insights](#results--insights)  
- [Recommendation](#recommendation)  
- [Conclusion](#conclusion)  
- [Built With](#built-with)  
- [Roadmap](#roadmap)  
- [Contact](#contact)

---

## Project Overview
This project predicts whether a student will **pass** or **fail** using behavioral and environmental variables (e.g., study hours, attendance, sleep).  
The KNIME workflow cleans and transforms the data, balances classes, trains multiple models, and evaluates them with ROC, lift charts, and confusion matrices.

---

## Project Scope
- Analyze **6,607** student records  
- Engineer features and handle missing data/outliers  
- Balance classes with **SMOTE**  
- Train and compare multiple models (DT, RF, MLP, LR)  
- Report metrics and interpret key drivers of success

---

## Business Objective
Provide data-driven insights to help schools:
- **Identify at-risk students** early  
- **Target interventions** (attendance support, study planning)  
- **Prioritize factors** that most impact outcomes

---

## Document Purpose
Show the full analytics lifecycle in **KNIME** from raw CSV to validated models and explainable insights that educators can use.

---

## Use Case
**Scenario:**  
A school district wants to spot students likely to fail before exam season. This workflow flags at-risk students and highlights the factors to address (e.g., low attendance, minimal study hours).

---

## Skills Demonstrated
- KNIME workflow design (ETL, modeling, evaluation)  
- Data cleaning: imputation, outlier capping, encoding, scaling  
- Class balancing (SMOTE)  
- Model comparison: Decision Tree, Random Forest, Logistic Regression, MLP  
- Metrics: Accuracy, Cohen’s Kappa, AUC, Lift, Confusion Matrix  
- GitHub documentation

---

## Data Source
- **Provider:** Kaggle – [Student Performance Factors](https://www.kaggle.com/datasets/lainguyn123/student-performance-factors)  
- **Format:** CSV  
- **Records:** 6,607  
- **Target:** `Exam_Score` (Pass > 60, Fail ≤ 60)  
- **Key Features:** `Hours_Studied`, `Attendance`, `Sleep_Hours`, `Parental_Involvement`, `Access_to_Resources`

---

## Data Preparation & Processing
1. **Missing Values:** Mean imputation (`Sleep_Hours` ~7%, `Attendance` ~5%)  
2. **Outliers:** Cap `Hours_Studied` at 40/week; `Attendance` at 100%  
3. **Encoding & Scaling:** Categorical to numeric; standardize numeric features  
4. **Split:** 70% train / 30% validation  
5. **Class Balance:** Apply **SMOTE** to reduce bias

---

## Model Training & Evaluation

### Decision Tree – Simple, Explainable
<img width="855" height="352" alt="dt_config" src="https://github.com/user-attachments/assets/b63c5541-6c09-4542-9911-ef3511702cc8" />  
<img width="829" height="595" alt="dt_results" src="https://github.com/user-attachments/assets/c30e19de-34ce-4f8b-9d4b-5d23d256ebe5" />

---

### Random Forest – Most Accurate, Robust
<img width="683" height="484" alt="rf_config" src="https://github.com/user-attachments/assets/0dfc1059-87cb-45a9-abe4-d1f04aa7c8b0" />  
<img width="869" height="635" alt="rf_results" src="https://github.com/user-attachments/assets/a6a31e2d-2924-46f7-a831-d6ecda189ff0" />

---

### Neural Network (MLP) – Captures Complex Patterns
<img width="830" height="345" alt="mlp_config" src="https://github.com/user-attachments/assets/b44753a7-170e-41bf-b344-66dce4a5fe13" />  
<img width="885" height="626" alt="mlp_results1" src="https://github.com/user-attachments/assets/edb98c8e-a109-42d5-be30-f3682e6a1b18" />  
<img width="975" height="728" alt="mlp_results2" src="https://github.com/user-attachments/assets/976cca1b-9d5f-47b8-b70d-51d509d17977" />

---

## Results & Insights
**Top accuracy:** **Random Forest – 91.09%**  
**Decision Tree:** 90.82% (highly interpretable)  
**Neural Network:** ~91.09% (less explainable)

| Model           | Validation Accuracy | Key Strength                                                        |
|-----------------|---------------------|----------------------------------------------------------------------|
| Decision Tree   | 90.82%              | Simple and interpretable, ideal for educators.                      |
| Random Forest   | 91.09%              | High accuracy and robustness, suitable for deployment.              |
| Neural Network  | 91.09%              | Accurate but less interpretable; better for research.               |

**Key drivers of success:**
- **Hours_Studied** — strongest predictor (students studying <5 hrs/week → high failure rate; >10 hrs/week → much higher pass rate)  
- **Attendance** — <60% predicts failure risk; >80% aligns with passing  
- **Sleep_Hours**, **Parental_Involvement**, **Resources** — supportive but secondary

---

## Recommendation
- Track and improve **attendance** proactively  
- Promote structured **study routines** (10+ hours/week)  
- Use **Random Forest** for large-scale accuracy; use **Decision Tree** where explainability is critical  
- Refresh models each term and monitor drift

---

## Conclusion
This KNIME workflow turns raw data into **actionable, explainable** insights.  
With targeted interventions on attendance and study habits, schools can **identify at-risk students early** and improve outcomes.

---

## Built With
- **KNIME Analytics Platform**  
- **SMOTE** (class balancing)  
- **CSV** (data format)  
- **Kaggle** dataset

---

## Roadmap
- [ ] Add socio-economic and behavioral features  
- [ ] Deploy as KNIME WebPortal app  
- [ ] Automate data refresh and model retraining  
- [ ] Add SHAP/Feature importance visuals for explainability

---

## Contact
**Kweku Darko**  
**Email:** [kaydarko7@gmail.com](mailto:kaydarko7@gmail.com)  
**LinkedIn:** [Kweku Darko](https://www.linkedin.com/in/kweku-darko-b880b4161/)
