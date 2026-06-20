# 🦠 COVID-19 Patient Dataset — Exploratory Data Analysis (EDA)
> *"Mortality from COVID-19 was not random — it was systematically structured by age, sex, comorbidity burden, and severity of care."*
---
## 📌 Project Overview
This notebook performs a comprehensive, end-to-end **Exploratory Data Analysis** on over **1 million COVID-19 patient records** from Mexico to uncover the key factors that influenced patient mortality. It covers feature engineering, univariate, bivariate, and multivariate analysis — with a written conclusion after every chart and every section.
---
## 📂 Notebook Structure
| Section | Description |
|---------|-------------|
| 📋 **EDA Report** | Shape, dtypes, missing values, duplicates, statistical summary |
| ⚙️ **Feature Engineering** | 6+ new features: Death, Age_Group, COVID_Positive, Hospitalized, severity, TOTAL_DISEASES |
| 📊 **Univariate Analysis** | Distribution of Age Group, Gender, Pregnancy, COVID Status, Hospitalization, Death |
| 🔗 **Bivariate Analysis** | Death vs Gender, Age Group, Pregnancy, COVID Status, Hospitalization, Comorbidities, Severity, Total Diseases |
| 🌐 **Multivariate Analysis** | Sex + Age + COVID + Severity interactions, Death timeline (2020 vs 2021), Disease × Age Group heatmap |
---
## 🔑 Key Findings
| Factor | Insight |
|--------|---------|
| **Overall Mortality** | 7.3% of patients died (~76,942 of 1,048,575) |
| **Gender** | Males had nearly **2× higher mortality** than females across every age group |
| **Age** | Seniors (60+): drastically higher death rates → the single strongest predictor |
| **Severity** | ICU/Intubated ("Critical") patients faced near coin-flip survival odds |
| **Comorbidity Count** | Death rate compounds — ~1.2% at 0 diseases → ~31% at 3 → ~50% at 5+ |
| **Pneumonia** | The single most lethal comorbidity — 7× more deadly than the next-highest |
| **Hospitalization** | Outpatient deaths were rare; hospitalized patients drove nearly all fatalities |
| **Death Timeline** | Two waves — peak deaths in **Jul–Aug 2020** and **Jan–Feb 2021** |
---
## 👤 Mortality Risk Profiles
| Profile | Death Rate |
|---------|-----------|
| Senior, Pneumonia | 🔴 ~55% |
| Senior, Renal Chronic disease | 🔴 ~40% |
| ICU-admitted patient (any age) | 🔴 ~45–50% |
| Adult, Pneumonia | 🟡 ~32% |
| Adult, 3+ comorbidities | 🟡 ~31% |
| Hospitalized patient (any age) | 🟡 ~30–35% |
| Young Adult, no comorbidities | 🟢 ~1–2% |
| Outpatient, COVID-negative | 🟢 <1% |
---
## 🛠️ Tech Stack
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-EDA-green?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Plots-red)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-yellow?logo=jupyter)
![NumPy](https://img.shields.io/badge/NumPy-Arrays-lightblue?logo=numpy)
---
## 📁 Dataset
- **File used:** `Covid Data.csv`
- **Shape:** 1,048,575 rows × 21 columns
- **Overall death rate:** ~7.3%
---
> **Note:** Download `Covid Data.csv` from the source above and place it in the same folder as the notebook.
---
## 📌 Features Engineered
| Feature | Description |
|---------|-------------|
| `Death` | Binary flag derived from `DATE_DIED` |
| `Age_Group` | Infants, Children, Teens, Young Adults, Adults, Seniors |
| `COVID_Positive` | 1 if `CLASIFFICATION_FINAL ≤ 3`, else 0 |
| `Hospitalized` | 1 if admitted, 0 if outpatient |
| `severity` | 'Critical' (ICU/intubated) vs 'Normal' |
| `TOTAL_DISEASES` | Count of comorbidities per patient (0–10) |
