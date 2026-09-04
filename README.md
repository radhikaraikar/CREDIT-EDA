# Credit Risk EDA

## 📌 Project Overview

This project focuses on **Exploratory Data Analysis (EDA) of credit application data** to understand customer characteristics, loan applications, previous loan outcomes, and factors associated with loan default.

The analysis uses two major datasets:

* **Application Dataset** – Current loan application information
* **Previous Application Dataset** – Customers' previous loan application history

The project performs data inspection, data-quality checks, missing-value treatment, outlier analysis, univariate analysis, and bivariate/multivariate analysis to identify meaningful patterns in the data.

---

## 🎯 Objectives

The main objectives of this project are:

* Understand the structure and characteristics of the credit datasets.
* Identify and handle missing values.
* Detect and analyze outliers.
* Understand the distribution of loan applicants.
* Analyze the imbalance between defaulters and non-defaulters.
* Study customer demographics and financial characteristics.
* Analyze previous loan application outcomes.
* Identify patterns that may help understand credit-risk behavior.
* Generate business-oriented insights from the data.

---

## 📂 Datasets

### 1. Application Dataset

The application dataset contains **307,511 records and 122 columns**. It includes information such as:

* Income
* Credit amount
* Annuity
* Goods price
* Gender
* Age
* Education
* Occupation
* Family status
* Housing type
* Employment information
* Regional information
* Credit bureau enquiries
* Loan repayment target

The dataset contains both numerical and categorical variables.

### 2. Previous Application Dataset

The previous application dataset contains **1,670,214 records and 37 columns**. It includes information about customers' previous loan applications, including:

* Previous credit amount
* Application amount
* Down payment
* Goods price
* Contract type
* Contract status
* Payment type
* Client type
* Product type
* Channel type
* Seller industry
* Yield group
* Product combination

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## 🔍 Data Cleaning & Preparation

### Missing Value Analysis

Missing values were analyzed using percentage-based checks.

Several columns contained substantial missing values. The project uses a threshold-based approach for columns with high levels of missing data.

### Missing Value Imputation

Different strategies were used depending on the variable:

* **Categorical variables:** Missing values were replaced with `"Others"`.
* **Numerical variables:** Median/mode-based imputation was used where appropriate.
* Credit-bureau enquiry columns were imputed using their **mode**, because approximately 99% of their observed values were zero.

For example, `OCCUPATION_TYPE` had approximately **31.35% missing values**, which were categorized as `"Others"`.

---

## 📊 Exploratory Data Analysis

### 1. Target Variable Analysis

The target variable shows a significant class imbalance:

| Target          | Percentage |
| --------------- | ---------: |
| 0 – Non-default |     91.93% |
| 1 – Default     |      8.07% |

This means that the dataset contains substantially more non-default cases than default cases.

---

### 2. Loan Credit Analysis

The `AMT_CREDIT` variable was categorized into different credit ranges.

The analysis found that **low-credit applications (₹2L–₹4L range)** represent a large portion of the applications.

---

### 3. Age Analysis

Applicants were divided into age groups:

| Age Group | Percentage |
| --------- | ---------: |
| Below 25  |      4.43% |
| 25–45     |     50.09% |
| 45–65     |     41.77% |
| 65–85     |      3.71% |

The **25–45 age group** represents the largest proportion of applicants.

---

### 4. Previous Application Status

Previous applications were divided into:

* Approved
* Cancelled
* Refused
* Unused offers

The distribution was:

| Status       | Percentage |
| ------------ | ---------: |
| Approved     |     62.07% |
| Cancelled    |     18.94% |
| Refused      |     17.40% |
| Unused offer |      1.58% |

---

## 📈 Outlier Analysis

Box plots and descriptive statistics were used to identify potential outliers.

Variables showing notable outlier behavior include:

* `AMT_INCOME_TOTAL`
* `AMT_CREDIT`
* `AMT_ANNUITY`
* `AMT_GOODS_PRICE`
* `REGION_POPULATION_RELATIVE`

The first four financial variables showed substantial differences between their upper percentiles and maximum values.

---

## 🔗 Bivariate & Multivariate Analysis

The project analyzes relationships between variables to identify patterns in loan applications.

Examples include:

* Weekday vs. application amount
* Annuity vs. goods price
* Customer characteristics vs. loan default
* Previous application characteristics vs. contract status

For example, the analysis compares application amounts across weekdays for approved, cancelled, refused, and unused applications.

### Key Observation

For approved applications, credit amounts were higher on **Monday and Wednesday** compared with other days, while cancelled applications showed higher amounts on Sunday.

---

## 💡 Key Insights

Some important findings from the analysis include:

1. The dataset is highly imbalanced, with approximately **92% non-default and 8% default** applications.
2. Most applicants belong to the **25–45 age group**.
3. A significant proportion of previous applications were **approved**.
4. Financial variables such as income, credit amount, annuity, and goods price contain notable outliers.
5. The previous-application dataset is dominated by **repeat customers**, with `Repeater` representing approximately 73.7% of applications.
6. The most common previous application product combinations include **Cash**, **POS household with interest**, and **POS mobile with interest**.
7. Credit and cash offices represent a major application channel.

---

## 📁 Project Structure

```text
CREDIT-EDA/
│
├── application_data.csv
├── previous_application.csv
├── CREDIT_EDA.ipynb
├── README.md
└── images/
    └── charts/
```

> Dataset filenames and notebook names can be adjusted to match the actual files in the repository.

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

### 3. Start Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the EDA notebook

Open:

```text
CREDIT_EDA.ipynb
```

Make sure the required CSV datasets are available in the expected directory.

---

## 📌 Conclusion

This project provides an extensive exploratory analysis of credit application and previous application data.

The analysis highlights **customer demographics, financial characteristics, loan application behavior, missing-data patterns, outliers, application outcomes, and default imbalance**.

These insights can serve as a foundation for further **credit-risk analysis and predictive modeling**, where machine-learning techniques could be used to identify applicants with a higher probability of default.

---


---

## 📜 License

This project is intended for **educational and analytical purposes**.
