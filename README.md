🏥 Disease Prediction Using Patient Symptoms (End-to-End Data Science Project)

🔍 Problem Statement
Healthcare diagnosis often depends on identifying patterns between symptoms and diseases.
The goal of this project is to predict the most likely disease for a patient based on reported symptoms and provide:
Prediction confidence
Disease explanation
Suggested precautions
This simulates a real clinical decision-support system.


📊 Datasets Used
We used real-world structured healthcare datasets:

dataset.xlsx
Each row = one patient
Columns: Disease, Symptom_1 … Symptom_17

symptom_Description.csv
Disease → medical description

symptom_precaution.csv
Disease → recommended precautions

symptom_severity.csv
Symptom → severity weight


🧠 Approach & Logic (Step-by-Step)

1️⃣ Understanding the Raw Data
Each patient can have up to 17 symptoms
Symptoms are categorical text values
ML models cannot directly understand text symptoms


📌 Conclusion:
We must convert symptoms into a machine-readable format


2️⃣ Feature Engineering: Binary Symptom Encoding
We transformed symptoms into binary features:

Symptom	    Value
itching	    1
fever	    0
cough	    1

Why this logic?
Presence / absence of a symptom is medically meaningful
Keeps feature space interpretable
Widely used in healthcare ML systems


📌 Result:
Each row still represents one patient
Row count remains unchanged
Columns = unique symptoms


3️⃣ Exploratory Data Analysis (EDA)

We performed EDA to:
Check class imbalance
Understand symptom frequency
Identify dominant symptom–disease patterns
Validate data quality

Why EDA is critical
Prevents misleading models
Avoids blind modeling
Helps justify feature choices

🤖 Machine Learning Models Implemented

We tested 4 classification models:

Model	                    Purpose
Logistic Regression	    Baseline & interpretability
Decision Tree	        Rule-based learning
Random Forest	        Ensemble robustness
Gradient Boosting	    Final optimized model

📈 Model Comparison Results
Model	                Accuracy	Weighted F1
Logistic Regression	    1.00	       1.00
Decision Tree	        0.23	       0.22
Random Forest	        1.00	       1.00
Gradient Boosting	    0.84	       0.81

⚠️ Important Insight
100% accuracy indicates memorization / leakage
Gradient Boosting showed realistic generalization

📌 Final Model Selected:
✅ Gradient Boosting Classifier

🧪 Prediction Demo (New Patient)
Input
Patient symptoms entered manually

Output
Predicted disease
Prediction confidence score
Top 3 possible diseases

Example Output
Predicted Disease: $Disease_Name  
Confidence Score: $XX.XX%

Top 3 Predictions:
- $Disease_1 → $XX%
- $Disease_2 → $XX%
- $Disease_3 → $XX%

Why confidence matters
Helps doctors trust predictions
Low confidence → further tests needed
High confidence → strong recommendation


🩺 Post-Prediction Business Value
After prediction:
Disease description is shown
Recommended precautions are displayed
Enables end-to-end decision support


🧠 Key Learnings
How to convert medical text data into ML features
Why perfect accuracy can be misleading
Importance of confidence scores
Building explainable healthcare ML systems
Thinking beyond models → real-world usage


🛠️ Tech Stack
Python
Pandas, NumPy
Scikit-learn
Gradient Boosting
Git & GitHub

📂 Repository Structure
├── data/
│   ├── dataset.xlsx
│   ├── symptom_Description.csv
│   ├── symptom_precaution.csv
│   └── symptom_severity.csv
├── notebooks/
│   ├── EDA.ipynb
│   ├── Feature_Engineering.ipynb
│   └── Modeling.ipynb
├── README.md
