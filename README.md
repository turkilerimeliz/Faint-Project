# 🧠 Predicting Vasovagal Reaction Risk  using Facial Action Units

This project explores the early prediction of vasovagal reactions (VVR) in blood donors using machine learning and facial action unit (AU) intensities extracted from video recordings taken **before needle insertion**. The aim is to provide a baseline for real-time, non-invasive monitoring systems that can help ensure donor safety and retention — critical for maintaining a sustainable blood supply.

---

## 🩸 Background

Blood donation environments contain several stimuli such as needles, blood, or the experience of another donor that can trigger donors to have negative emotional and physiological responses, such as fainting or dizziness, referred to as **vasovagal reactions**. Experiencing vasovagal reactions may affect donors’ retention behavior, posing a significant risk to sustainable blood supply. While self-reporting of vasovagal reactions may not allow early interventions, enhancing developments in video recordings and machine learning may enable
early detection of these feelings. This project investigates whether machine learning models can predict VVR risk **before** it happens, using only facial muscle movement data.

---

## 🎯 Objectives

- Predict whether a donor is at **high or low risk** of experiencing a VVR.
- Compare performance of three models:
  - 🤖 Multi-Layer Perceptron (MLP)
  - 📈 XGBoost
  - 🌲 Random Forest
- Evaluate oversampling techniques:
  - 🔁 SMOTE
  - 🌀 Random Oversampling (ROS)
- Test effect of somatosensory amplification (SSA) on model performance.

---

## 🛠️ Methodology

- **Data**: Facial Action Unit (AU) intensities from video footage recorded *before needle insertion*. The data utilized in this study has been acquired from the Faint Project
(FAINT, 2018), in an anonymized format.
- **Target**: Binary classification (High vs. Low VVR risk), derived from self-reported VVR scores.
- **Features**:
  - Time series characteristics of AUs
  - 🧍‍♀️ SSA scores obtained using 10-item somatosensory amplification scale test 
- **Preprocessing**: EDA, data cleaning, feature engineering, oversampling.
- **Models**: Trained using nested cross validation. 
- **Evaluation Metrics**: 🎯 F1 Score, 📊 Recall,📈 PR-AUC,  ✅ Accuracy

---

## 🧪 Results

- 🌳 Random Forest showed the most balanced performance:
  - 🎯 F1 Score: 0.49
  - 📊 Recall: 0.55
  - ✅ Accuracy: 0.63
  - 📈 PR-AUC included for comprehensive evaluation
    
-  **SMOTE outperforms ROS** in handling class imbalance.
-  Adding somatosensory amplification as a feature led to minor, model-dependent improvements—only tree-based models benefitted slightly.
-  Top informative facial expressions: **lip tightening**, **jaw drawing**, **blinking**.

---

## 📁 Repository Structure
📂 code/  
&nbsp;&nbsp;&nbsp;&nbsp;📓 Preprocessing.ipynb  
&nbsp;&nbsp;&nbsp;&nbsp;📓 DataCleaning_EDA.ipynb  
&nbsp;&nbsp;&nbsp;&nbsp;📓 Model_Implementation.ipynb

📄 README.md

---

## ⚙️ Technologies Used

| **Library**       | **Version** | **Reference**                       |
|-------------------|-------------|-------------------------------------|
| **Pandas**        | 2.2.2       | McKinney, 2010                      |
| **Numpy**         | 1.26.4      | Harris et al., 2020                 |
| **Seaborn**       | 0.13.2      | Waskom, 2021                        |
| **Matplotlib**    | 3.8.0       | Hunter, 2007                        |
| **Imbalanced-learn (Imblearn)** | 0.13.0  | Junder et al., 2018       |
| **Scikit-learn**  | 1.5.2       | Pedregosa et al., 2011              |
| **XGBoost**       | 1.7.6       | Chen and Guestrin, 2016             |
| **SHAP**          | 0.46.0      | Lundberg and Lee, 2017              |
| **SciPy**         | 1.13.1      | Jones et al., 2007                  |
| **Missingno**     | 0.52.2      | Mikulski, 2023                      |
| **Pingouin**      | 1.17.0      | Vallat, 2018                        |
| **Statsmodels**   | 0.14.0      | Seabold and Perktold, 2010          |

---
