# 🦠 COVID-19 Mortality Risk Analysis 

This project analyzes demographic, medical, and condition-based factors that influenced mortality during the early months of the COVID-19 pandemic. The goal is to identify **which variables had the strongest relationship with fatal outcomes** and determine whether **COVID-19 became the leading cause of death during that period.**

---

## 🔍 Research Questions

1️⃣ **Which risk factors are more relevant or have more impact on the death of a person from Jan 2021 to June 2022?**

2️⃣ **Was COVID-19 the main cause of death during this period compared to other causes?**

---
## Methodology
### 1) Data Preparation
- Load raw data from `data/raw/`
- Standardize column names (if required)
- Parse and validate date fields (e.g., symptoms, admission, death date)
- Convert coded categorical variables into consistent binary/ordinal representations
- Create the target variable:
  - `death = 1` if `FECHA_DEF` is present and valid, else `death = 0`
- Save cleaned dataset into `data/processed/`

### 2) Exploratory Data Analysis (EDA)
- Missing values profile and data quality checks
- Descriptive statistics and distribution analysis
- Mortality rates stratified by:
  - Age groups
  - Sex
  - Hospitalization type
  - ICU and intubation
  - Comorbidities
- Visualization-focused insights (clear figures stored in `reports/figures/`)

### 3) Risk Factor Assessment
To quantify the relationship between risk factors and mortality, the project uses:
- Mortality rate comparisons across groups
- Contingency tables
- **Odds Ratios (OR)** (where appropriate) for interpretable risk comparisons
- Optional: interpretable logistic regression for multivariable context (if included)

### 4) Cause of Death Comparison (Question 2)
Depending on availability and quality of cause-of-death information, we compare:
- COVID-19-related deaths vs. other causes (if explicitly recorded)
- COVID classification vs. mortality outcomes as a proxy when direct cause is unavailable

---

## Project Outputs

- 📄 [Exploratory Data Analysis Notebooks](notebook/)
- 📊 [Key Figures](reports/figures/)
- 📝 [Final Conclusions](reports/conclusions.md)
---
## Repository Structure
```text
COVID-19-Mortality-Risk-Analysis-Identifying-Key-Risk-Factors/
│
├── data/
│   ├── raw/                 # Original dataset (not modified)
│   └── processed/           # Cleaned and filtered dataset used for analysis
│
├── notebooks/
│   ├── 01_data_overview.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_exploratory_analysis.ipynb
│   ├── 04_risk_factor_analysis.ipynb
│   └── 05_conclusions.ipynb
│
├── reports/
│   ├── figures/             # Exported plots for README/LinkedIn
│   └── summary_report.md    # Optional executive summary
│
├── requirements.txt
├── README.md
└── LICENSE


