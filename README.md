<h1 align="center" style="color:#ff66b3;">💖🩺 Health Check – MITBOTS 🩺💖</h1>

<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?font=Poppins&size=22&duration=3000&pause=1000&color=FF69B4&center=true&vCenter=true&width=600&lines=Machine+Learning-Based+Health+Status+Prediction;Random+Forest+Classifier+%F0%9F%8C%B8;Fit+%E2%9C%85+or+Not+Fit+%E2%9D%8C+Prediction+System" alt="Typing SVG" />
</p>

---

### 📖 Overview  
This project predicts whether an individual is **Fit ✅ or Not Fit ❌** based on their health data using a **Random Forest Classifier**.  
It leverages a real-world **Cardiovascular Disease Dataset** and performs preprocessing, training, and evaluation to achieve accurate fitness classification.  

---

### 🚀 Steps Performed  

#### 1️⃣ Data Loading  
- Dataset: `cardio_train.csv`  
- Loaded using **Pandas** with `;` as separator.  

#### 2️⃣ Data Preprocessing  
- Converted **age** from days → years.  
- Dropped irrelevant `id` column.  
- Renamed the target column `cardio` → `Fit`.  
- Checked and confirmed no missing values.  

#### 3️⃣ Feature & Label Separation  
```python
X = df.drop('Fit', axis=1)
y = df['Fit']
4️⃣ Train-Test Split
Split data into 80% training and 20% testing using train_test_split().

5️⃣ Model Training
Used RandomForestClassifier from Scikit-Learn:

python
Copy code
model = RandomForestClassifier(n_estimators=100, random_state=42, n_jobs=-1)
model.fit(X_train, y_train)
6️⃣ Model Evaluation
Evaluated the model using:

Accuracy Score

Confusion Matrix

Classification Report

📊 Model Performance:

Metric	Score
Accuracy	0.71 (71%)
Precision	0.70
Recall	0.70
F1-Score	0.71

🧠 Prediction Example
A test case predicts whether a 25-year-old active male is fit or not:

python
Copy code
input_data = pd.DataFrame([{
    'age': 25 * 365,
    'gender': 1,
    'height': 175,
    'weight': 70,
    'ap_hi': 120,
    'ap_lo': 80,
    'cholesterol': 1,
    'gluc': 1,
    'smoke': 0,
    'alco': 0,
    'active': 1
}])

prediction = model.predict(input_data)
print("Prediction:", "Fit ✅" if prediction[0] == 0 else "Not Fit ❌")
🧾 Output:

text
Copy code
Prediction: Not Fit ❌
🧩 Libraries Used
Pandas → Data handling

Scikit-Learn → ML model training and evaluation

NumPy → Numerical operations

