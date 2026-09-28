# 🏥 Healthcare Data Analysis

## 📌 Project Overview

This project performs **Healthcare Data Analysis** using Python and Pandas.

The project analyzes patient information such as gender, age, medical condition, admission type, medical code, billing amount, admission date, and discharge date.

The dataset contains **500 patient records and 9 columns**.

---

## 🎯 Objectives

The main objectives of this project are:

* Load the healthcare dataset.
* Explore the dataset structure.
* Check column names and data types.
* Identify missing values.
* Handle missing medical codes.
* Convert admission and discharge dates.
* Clean admission type values.
* Analyze billing amounts.
* Calculate hospital stay duration.
* Analyze medical conditions by gender.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **Matplotlib**
* **Seaborn**
* **Google Colab / Jupyter Notebook**

---

## 📂 Project Files

```text
Healthcare-Data-Analysis/
│
├── healthcare_dataset.csv
├── healthcare.py
├── Healthcare.ipynb
└── README.md
```

---

## 📊 Dataset Information

### Dataset Size

* **Rows:** 500
* **Columns:** 9

### Columns

| Column            | Description                   |
| ----------------- | ----------------------------- |
| Patient_ID        | Unique patient identification |
| Gender            | Patient gender                |
| Age               | Patient age                   |
| Medical_Condition | Patient's medical condition   |
| Admission_Date    | Date of hospital admission    |
| Admission_Type    | Type of hospital admission    |
| Medical_Code      | Medical/diagnostic code       |
| Billing_Amount    | Patient billing amount        |
| Discharge_Date    | Date of hospital discharge    |

---

## 🔍 Data Analysis

### 1. Import Libraries

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

---

### 2. Load Dataset

The healthcare CSV file is loaded using Pandas:

```python
df = pd.read_csv("healthcare_dataset.csv")
```

---

### 3. View Dataset

The first records are displayed using:

```python
df.head()
```

The last records can also be inspected.

---

### 4. Check Columns

```python
df.columns
```

This displays all column names available in the dataset.

---

### 5. Check Data Types

```python
df.dtypes
```

This helps identify the data type of each column.

---

### 6. Check Dataset Shape

```python
df.shape
```

The dataset contains **500 rows and 9 columns**.

---

## 🧹 Data Cleaning

### Missing Values

Missing values are checked using:

```python
df.isnull().sum()
```

The `Medical_Code` column is specifically checked:

```python
df["Medical_Code"].isnull().sum()
```

Missing medical codes are replaced with `"Unknown"`:

```python
df["Medical_Code"] = df["Medical_Code"].fillna("Unknown")
```

---

## 📅 Date Conversion

The admission and discharge dates are converted into datetime format.

```python
df["Discharge_Date"] = pd.to_datetime(df["Discharge_Date"])
df["Admission_Date"] = pd.to_datetime(df["Admission_Date"])
```

This allows date calculations and time-based analysis.

---

## 🏥 Admission Type Cleaning

Admission types are cleaned by removing unnecessary spaces and converting the values to lowercase:

```python
df["Admission_Type"] = (
    df["Admission_Type"]
    .str.strip()
    .str.lower()
)
```

The frequency of each admission type is then analyzed:

```python
df["Admission_Type"].value_counts()
```

---

## 💰 Billing Amount Analysis

The billing amount is analyzed using:

```python
df["Billing_Amount"].describe()
```

This provides statistical information such as:

* Count
* Mean
* Standard deviation
* Minimum
* Maximum
* Quartiles

---

## 🏨 Hospital Stay Calculation

A new column called `Hospital_Stay_Days` is created:

```python
df["Hospital_Stay_Days"] = (
    df["Discharge_Date"] - df["Admission_Date"]
).dt.days
```

This calculates the number of days each patient stayed in the hospi
