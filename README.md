# Titanic Tragedy: Data Analysis & K-Means Clustering

An exploratory data analysis (EDA) and unsupervised machine learning project investigating the demographic, socioeconomic, and embarkation factors that influenced passenger survival rates aboard the RMS Titanic.

---

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Dataset Description](#-dataset-description)
- [Methodology & Workflow](#-methodology--workflow)
- [Key Findings & Insights](#-key-findings--insights)
- [Repository Structure](#-repository-structure)

---

## Project Overview
The RMS Titanic sank on its maiden voyage in April 1912 after colliding with an iceberg in the North Atlantic Ocean, resulting in over 1,500 fatalities out of more than 2,200 passengers and crew. 

This project explores a subset of passenger data to answer two core research questions:
1. **What demographic and socioeconomic factors most influenced passenger survival rates?**[cite: 2]
2. **How can the dataset be expanded to support a more comprehensive predictive analysis?**[cite: 2]

---

## Dataset Description
The raw dataset (`DatasetTitanic.csv`) contains **179 passenger records** across **6 primary features**:

| Feature | Type | Description |
| :--- | :--- | :--- |
| `Survived` | Categorical (`int64`) | Survival status (`0` = Died, `1` = Survived) |
| `Name` | Categorical (`object`) | Full name and title of the passenger |
| `Sex` | Categorical (`object`) | Gender (`male` or `female`)[cite: 2] |
| `Age` | Numerical (`float64`) | Passenger age in years |
| `Fare` | Numerical (`float64`) | Ticket fare paid by the passenger (in USD/GBP equivalent) |
| `Embarked` | Categorical (`object`) | Port of embarkation (`S` = Southampton, `C` = Cherbourg, `Q` = Queenstown) |

---

## ⚙️ Methodology & Workflow

1. **Business Understanding:**
   - Defined key metrics, identified data types, and ran descriptive statistics on numerical columns (`Age` and `Fare`)[cite: 2].
2. **Data Preparation:**
   - Inspected missing values (`35` missing in `Age`, `1` missing in `Embarked`).
   - Removed incomplete rows using `.dropna()` rather than imputing averages to preserve integer/qualitative integrity, resulting in **143 clean records** (`clean_df`).
3. **Exploratory Data Analysis & Visualization:**
   - Generated pie charts, bar plots, and scatter plots examining survival distribution, gender ratios, port of embarkation, and age groups using `matplotlib` and `pandas`[cite: 2, 3].
4. **Unsupervised Machine Learning (K-Means Clustering):**
   - Applied `KMeans(n_clusters=4)` from `scikit-learn` on `Age` and `Fare` features to segment passengers into four distinct socioeconomic and age-based clusters[cite: 1, 2, 3].

---

## 🔍 Key Findings & Insights

* **Overall Survival Rate:** Out of the 143 cleaned records, **69.2% (99 passengers) perished**, while **30.8% (44 passengers) survived**[cite: 2].
* **Gender Disparity ("Women and Children First"):** Although males made up the majority of passengers on board, females accounted for **86.0% of the survivors** (with a ~66.7% within-group female survival rate compared to ~10.9% for males).
* **Age Demographics:** The passenger base skewed young, with a mean age of **28.0 years** (SD: 15.1 years)[cite: 1, 2]. Over half of the dataset (**90 passengers**) was under 30 years old[cite: 1, 2].
* **Socioeconomic Class (`Fare`):** Ticket prices showed a right-skewed distribution with a mean of **$29.25**, a median of **$15.85**, and a maximum outlier of **$263.00**, reflecting stark class divides between 1st, 2nd, and 3rd class accommodations[cite: 1, 2].
* **Port of Embarkation:** **78.3%** of passengers boarded at Southampton (`S`), **16.8%** at Cherbourg (`C`), and **4.9%** at Queenstown (`Q`)[cite: 2].
* **K-Means Clustering (`K=4`):** Segmenting passengers by `Age` and `Fare` highlighted distinct survival trends across age/wealth brackets—showing higher survival priority among children and wealthier elderly passengers, while lower-fare elderly passengers faced the highest mortality rates[cite: 1, 2].

---

## 📁 Repository Structure

```text
├── bus201_titanic_ppt.pptx     # Presentation deck summarizing methodology, charts, and insights[cite: 1]
├── bus201_titanic_report.docx  # Comprehensive written analysis report with code outputs[cite: 2]
├── titanic_analysis.ipynb      # Google Colab / Jupyter Notebook containing Python code & K-Means model[cite: 3]
└── README.md                   # Project documentation
