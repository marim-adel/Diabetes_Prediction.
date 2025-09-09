# Diabetes Prediction with Machine Learning

This project explores how machine learning can be used to predict diabetes based on patient health data.  
The idea is simple: given measurements like glucose level, BMI, age, and more, can we predict whether a person is likely to have diabetes?

## Why this project?
Diabetes is one of the most common chronic diseases worldwide, and early detection can make a huge difference in treatment and lifestyle changes.  
By training models on medical data, we can build a system that helps classify patients as **diabetic** or **non-diabetic**.

## The Dataset
We use the Pima Indians Diabetes Dataset (`diabetes.csv`).  
Each record describes one patient with features like:

- Pregnancies  
- Glucose  
- Blood Pressure  
- Skin Thickness  
- Insulin  
- BMI  
- Diabetes Pedigree Function  
- Age  
- Outcome (1 = Diabetic, 0 = Non-Diabetic)

## What I did
1. **Exploratory Data Analysis (EDA)**  
   - Looked at how glucose and BMI differ between diabetic and non-diabetic groups.  
   - Checked correlations between features.  
   - Visualized class imbalance.

2. **Preprocessing**  
   - Standardized the features so that all are on the same scale.  
   - Split the dataset into 80% training and 20% testing.

3. **Modeling**  
   - Trained and compared three models:
     - Logistic Regression  
     - Random Forest  
     - Support Vector Machine (SVM)  
   - Used GridSearchCV to tune hyperparameters.

4. **Evaluation**  
   - Compared accuracy, precision, recall, F1-score, and ROC-AUC.  
   - Focused on **recall for diabetic patients**, since in healthcare missing a sick patient is riskier than a false alarm.

## Results

| Model               | Accuracy | Recall (Diabetic) | ROC-AUC |
|---------------------|----------|-------------------|---------|
| Logistic Regression | 0.75     | **0.67**          | **0.74**|
| Random Forest       | 0.75     | 0.64              | 0.72    |
| SVM (RBF)           | 0.73     | 0.56              | 0.69    |

- Logistic Regression gave the **best overall performance**, especially in recall and ROC-AUC.  
- Random Forest was close, but not quite as strong in identifying diabetic patients.  
- SVM lagged behind in this dataset.  

## Conclusion
Logistic Regression is the most reliable model here because it balances accuracy with the ability to catch more diabetic patients.  
The project shows how important it is to evaluate models beyond accuracy — in medical applications, recall matters more.  
