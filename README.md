# Heart-Disease-Prediction-using-Machine-Learning

## 📘 Project Overview

This project aims to **predict the likelihood of heart disease** in patients using various health-related features such as age, cholesterol, and blood pressure. The dataset used is `heart_disease.csv`, containing 302 samples and 13 features after cleaning.

---

## 🧩 Dataset Information

| **Feature** | **Description**                                                                                   |
| ----------- | ------------------------------------------------------------------------------------------------- |
| age         | Age of the patient                                                                                |
| sex         | Gender (1 = male; 0 = female)                                                                     |
| cp          | Chest pain type (0 = typical angina, 1 = atypical angina, 2 = non-anginal pain, 3 = asymptomatic) |
| trestbps    | Resting blood pressure (mm Hg)                                                                    |
| chol        | Serum cholesterol (mg/dl)                                                                         |
| fbs         | Fasting blood sugar > 120 mg/dl (1 = true; 0 = false)                                             |
| restecg     | Resting ECG results (0 = normal, 1 = ST-T abnormality, 2 = left ventricular hypertrophy)          |
| thalach     | Maximum heart rate achieved                                                                       |
| exang       | Exercise-induced angina (1 = yes; 0 = no)                                                         |
| oldpeak     | ST depression induced by exercise                                                                 |
| slope       | Slope of the peak exercise ST segment (0 = upsloping, 1 = flat, 2 = downsloping)                  |
| ca          | Number of major vessels (0–4) colored by fluoroscopy                                              |
| thal        | Thalassemia (0 = normal; 1 = fixed defect; 2 = reversible defect; 3 = non-fixed defect)           |
| target      | Heart disease presence (1 = yes; 0 = no)                                                          |

---

## 🧼 Data Preprocessing

* Total samples: **303**
* Duplicated sample: **1** (removed)
* Final samples: **302**
* Missing values: **None**
* Encoding: **Not required** (all numeric features)

---

## 📊 Insights

**Sample Distribution:**

* Heart Disease (1): 164 samples
* No Heart Disease (0): 138 samples

**Top Correlated Features with Target:**

* `cp` (Chest Pain Type): **+0.432**
* `thalach` (Max Heart Rate): **+0.420**
* `slope`: **+0.344**
* `exang`: **–0.436**
* `oldpeak`: **–0.429**
* `ca`: **–0.409**

**Key Findings:**

* Higher heart rate and chest pain type correlate with heart disease.
* Exercise-induced angina, oldpeak, and more affected vessels correlate negatively.
* Males show higher heart disease incidence.

---

## 🔍 Model Training

Dataset split:

* **Train set:** 80%
* **Test set:** 20%

### ⚙️ Models Evaluated

| **Model**         | **Dataset** | **Accuracy** | **Precision** | **Recall** | **F1-Score** | **Confusion Matrix**  | **Difference (Train–Test)**                                                             |
| ----------------- | ----------- | ------------ | ------------- | ---------- | ------------ | --------------------- | --------------------------------------------------------------------------------------- |
| **KNN**           | Train       | 0.8548       | 0.8559        | 0.9000     | 0.8541       | [[89, 22], [13, 117]] | **Δ Acc:** +0.0305<br>**Δ Prec:** –0.0267<br>**Δ Recall:** +0.1000<br>**Δ F1:** +0.0525 |
|                   | Test        | 0.8852       | 0.9048        | 1.0000     | 0.8821       | [[20, 7], [0, 34]]    |                                                                                         |
| **Decision Tree** | Train       | 1.0000       | 1.0000        | 1.0000     | 1.0000       | [[111, 0], [0, 130]]  | **Δ Acc:** –0.1475<br>**Δ Prec:** –0.1477<br>**Δ Recall:** –0.1176<br>**Δ F1:** –0.1479 |
|                   | Test        | 0.8525       | 0.8523        | 0.8824     | 0.8521       | [[22, 5], [4, 30]]    |                                                                                         |
| **SVM**           | Train       | 0.8880       | 0.8917        | 0.9462     | 0.8872       | [[91, 20], [7, 123]]  | **Δ Acc:** –0.0191<br>**Δ Prec:** –0.0667<br>**Δ Recall:** +0.0244<br>**Δ F1:** +0.0047 |
|                   | Test        | 0.8689       | 0.8814        | 0.9706     | 0.8660       | [[20, 7], [1, 33]]    |                                                                                         |

---

## 🏆 Champion Model: K-Nearest Neighbour (KNN)

**Test Accuracy:** 88.52%
**Highlights:**

* Highest accuracy among all models.
* Balanced performance between training and test sets.
* **0 false negatives** (perfectly identified all heart disease cases).

---

## 🧠 Conclusion

* All 13 features contribute meaningfully to predicting heart disease.
* **KNN** was selected as the best model due to strong generalisation and reliability.
* This model can be used to **assist healthcare professionals** in identifying patients at higher risk for heart disease.

---

## 🗂️ Files Included

```
heart_disease.csv       # Dataset
Heart_Disease_Prediction_ML_Models.ipynb  # Model training notebook
README.md               # Project documentation
```

