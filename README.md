# Heart Disease Prediction Challenge

This project is a **machine learning solution to predict heart disease** using patient data. The goal is to accurately identify individuals at risk of heart disease, minimizing false negatives to catch as many cases as possible while keeping false positives reasonable.

---

## Dataset

The dataset contains patient health records with features such as:

- Age  
- Sex  
- Blood Pressure (BP)  
- Cholesterol  
- Max Heart Rate  
- ST depression (exercise-induced)  
- Number of vessels fluro  
- EKG results  
- Other health indicators  

The target variable is `Heart Disease` (1 = presence, 0 = absence).

---

## Approach

1. **Data Preprocessing**
   - Handle missing values and duplicates
   - Encode categorical features
   - Scale numerical features if needed
   - Feature selection (variance threshold, correlation analysis)

2. **Modeling**
   - RandomForestClassifier with tuned parameters:
     - `n_estimators=300`  
     - `max_depth=10`  
     - `min_samples_leaf=100`  
     - `max_features='sqrt'`  
     - `class_weight={0:1, 1:3}` to reduce false negatives
   - Optional threshold adjustment (e.g., 0.3) to improve recall

3. **Evaluation Metrics**
   - **Accuracy**: overall correctness  
   - **Precision**: penalizes false positives  
   - **Recall**: penalizes false negatives (important for heart disease detection)  
   - **F1-score**: balance between precision and recall  
   - Confusion matrix visualization to inspect FP and FN  

---

## Results

Example metrics on test data:

| Metric      | Value    |
|------------|----------|
| Accuracy   | 86.7%    |
| Precision  | 80.3%    |
| Recall     | 93.4%    |
| F1-score   | 86.3%    |

- Using **class weighting** and **threshold adjustment**, false negatives were significantly reduced, improving recall for high-risk patients.
