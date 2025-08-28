


#### 📌 **Financial Fraud Detection on Large-Scale Transactions (6.3M records)**

#### 📖 Overview

Built a fraud detection system using **XGBoost** on an imbalanced dataset with 6.3M+ transactions (only 0.12% fraudulent). Focused on maximizing recall while reducing false positives.

#### ⚙️ Features

* 📊 **Advanced Feature Engineering**: transaction timing, balance deltas, mismatch flags, ratio features

<img width="866" height="783" alt="image" src="https://github.com/user-attachments/assets/9521ce74-db95-4fd2-98e5-28cd56454944" />

<img width="1189" height="790" alt="image" src="https://github.com/user-attachments/assets/a2a6a8e6-2906-49a0-8fa7-653c09f34bcc" />

<img width="1010" height="547" alt="image" src="https://github.com/user-attachments/assets/4adad69b-61ff-4a17-9d55-5a6a3ee42ba8" />
 - Most Frauds Occur From 3 am to 6 am 

---

* ⚡ **Imbalanced Data Handling**: class weighting + custom recall-first objective

- Fraudulent transactions: 8213

- Non-fraudulent transactions: 6354407

- Percentage of fraud transactions: 0.12908204481801522

<img width="876" height="547" alt="image" src="https://github.com/user-attachments/assets/66291077-4550-4cad-ba30-eaefe0310b2b" />
- Need to take a log to reduce the effect of outliers ( common in transactional datasets)

---

* 🔍 **Hyperparameter Optimization**: Optuna tuning for best precision–recall balance

```
[I 2025-08-22 00:12:31,186] A new study created in memory with name: no-name-703cc720-9121-414a-b7aa-57bfd6d2d821
[I 2025-08-22 00:14:24,958] Trial 0 finished with value: 0.8702898550724638 and parameters: {'n_estimators': 780, 'learning_rate': 0.09755368817832326, 'max_depth': 10, 'subsample': 0.6088709827067248, 'colsample_bytree': 0.690529990277774}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:15:43,917] Trial 1 finished with value: 0.835357624831309 and parameters: {'n_estimators': 917, 'learning_rate': 0.2655721526808504, 'max_depth': 4, 'subsample': 0.6512699971177104, 'colsample_bytree': 0.9495275770890528}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:16:20,232] Trial 2 finished with value: 0.7468030690537084 and parameters: {'n_estimators': 378, 'learning_rate': 0.011648045057617972, 'max_depth': 5, 'subsample': 0.7608412131701605, 'colsample_bytree': 0.6009662853612291}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:17:46,267] Trial 3 finished with value: 0.8448687350835322 and parameters: {'n_estimators': 957, 'learning_rate': 0.14333833895960493, 'max_depth': 5, 'subsample': 0.9350768741348, 'colsample_bytree': 0.8807505889993189}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:18:30,942] Trial 4 finished with value: 0.7927051671732522 and parameters: {'n_estimators': 369, 'learning_rate': 0.038343522025847385, 'max_depth': 9, 'subsample': 0.8640675300267133, 'colsample_bytree': 0.6466142918653509}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:19:00,511] Trial 5 finished with value: 0.84472049689441 and parameters: {'n_estimators': 204, 'learning_rate': 0.1589680288543987, 'max_depth': 10, 'subsample': 0.9593531931213815, 'colsample_bytree': 0.7786130095475737}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:22:02,216] Trial 6 finished with value: 0.05018514141652879 and parameters: {'n_estimators': 911, 'learning_rate': 0.25705635642131885, 'max_depth': 4, 'subsample': 0.7071461384724161, 'colsample_bytree': 0.9636107698476916}. Best is trial 0 with value: 0.8702898550724638.
[I 2025-08-22 00:23:07,151] Trial 7 finished with value: 0.8642779587404995 and parameters: {'n_estimators': 550, 'learning_rate': 0.22337627398318233, 'max_depth': 8, 'subsample': 0.9924810682358475, 'colsample_bytree': 0.9667576916732075}. Best is trial 0 with value: 0.8702898550724638.
Tuning complete.
Best trial F1-score (with 100% recall): 0.8702898550724638
Best parameters found:  {'n_estimators': 780, 'learning_rate': 0.09755368817832326, 'max_depth': 10, 'subsample': 0.6088709827067248, 'colsample_bytree': 0.690529990277774}
```
---

* ✅ **Results**: Achieved **100% recall** and improved precision from **52% → 63%**, reducing false positives by \~20%

<img width="541" height="277" alt="image" src="https://github.com/user-attachments/assets/0cd666e5-ade0-42ee-a21a-7f11ce00b063" />

<img width="515" height="435" alt="image" src="https://github.com/user-attachments/assets/89e9dc93-04ea-4418-b1bf-8eae92a07d94" />

---

#### 🛠️ Tech Stack

* Python, Pandas, NumPy
* XGBoost, scikit-learn, Optuna
* Matplotlib, Seaborn

#### 📂 Environment Structure

```
├── data/              # dataset (links or instructions)
├── notebooks/         # EDA & model building
└── README.md          # project details
```

#### 🚀 Future Work

* Testing newer transformer-based anomaly detection methods
* Deploying the model as an API with FastAPI/Flask
* Exploring explainability with SHAP/LIME

#### 🔗 Links

* [Dataset Source](https://drive.usercontent.google.com/download?id=1VNpyNkGxHdskfdTNRSjjyNa5qC9u0JyV&export=download&authuser=0)
* [Contact/LinkedIn](https://www.linkedin.com/in/aditya-rawat-27ab59292)

---

