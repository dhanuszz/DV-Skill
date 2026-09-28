# AAPL Data Exploratory Analysis

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on Apple Inc. (AAPL) stock market data using Python.

The analysis uses **Pandas, NumPy, Matplotlib, and Seaborn** to load, inspect, summarize, and analyze stock price information.

The dataset contains **184 records** and **7 columns** covering AAPL stock data.

---

## 🎯 Objectives

The main objectives of this project are:

* Load the AAPL stock dataset.
* Explore the structure of the dataset.
* Check basic statistical information.
* Convert the Date column into a proper date format.
* Check for missing values.
* Analyze Open, High, Low, Close, and Volume values.
* Calculate price changes.
* Calculate daily return percentages.
* Understand the basic behavior of AAPL stock prices.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook / Google Colab**

---

## 📂 Dataset

The dataset used in this project is:

**File:** `AAPL (3).csv`

### Dataset Columns

| Column    | Description              |
| --------- | ------------------------ |
| Date      | Date of the stock record |
| Open      | Opening stock price      |
| High      | Highest stock price      |
| Low       | Lowest stock price       |
| Close     | Closing stock price      |
| Adj Close | Adjusted closing price   |
| Volume    | Number of shares traded  |

### Dataset Size

* **Rows:** 184
* **Columns:** 7

---

## 🔍 Exploratory Data Analysis

### 1. Import Libraries

The project uses the following Python libraries:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### 2. Load Dataset

The CSV file is loaded using Pandas:

```python
df = pd.read_csv(file_path)
display(df.head())
```

The `head()` function displays the first few records of the dataset.

---

### 3. Dataset Information

The `info()` function is used to examine:

* Number of entries
* Column names
* Data types
* Non-null values

```python
print(df.info())
```

---

### 4. Statistical Summary

The `describe()` function provides statistical information about numerical columns.

```python
print(df.describe())
```

This helps understand values such as:

* Mean
* Standard deviation
* Minimum
* Maximum
* Quartiles

---

### 5. Date Conversion

The Date column is converted into Pandas datetime format:

```python
df["Date"] = pd.to_datetime(df["Date"])
```

This makes the date column easier to use for time-based analysis.

---

### 6. Selecting Price Columns

The following columns are selected for analysis:

```python
price_cols = ["Open", "High", "Low", "Close", "Volume"]
```

---

### 7. Missing Value Check

Missing values are checked using:

```python
print(df[price_cols].isnull().sum())
```

This identifies whether important stock-price columns contain missing data.

---

## 📊 Feature Engineering

### Price Delta

A new column called `Price_Delta` is created to calculate the difference between the closing and opening prices.

```python
df["Price_Delta"] = df["Close"] - df["Open"]
```

Formula:

**Price Delta = Close − Open**

A positive value means the closing price is higher than the opening price, while a negative value means the closing price is lower.

---

### Daily Return Percentage

The project also calculates the percentage change between the opening and closing price:

```python
df["Daily_Return_%"] = (
    (df["Close"] - df["Open"]) / df["Open"]
) * 100
```

Formula:

**Daily Return % = ((Close − Open) / Open) × 100**

This helps measure the percentage movement of the stock during each recorded period.

---

## 📋 Final Analysis Output

The notebook displays selected columns including:

```python
print(df[[
    "Date",
    "Open",
    "High",
    "Low",
    "Close",
    "Volume",
    "Price_Delta",
    "Daily_Return_%"
]].head())
```

The output contains the original stock information along with the newly calculated `Price_Delta` and `Daily_Return_%` values.

---

## 📁 Project Files

```text
AAPL-Data-Exploratory-Analysis/
│
├── AAPL (3).csv
├── AAPL Data Exploratory Analysis.ipynb
└── README.md
```

---

## ▶️ How to Run the Project

### Using Jupyter Notebook

1. Install Python.
2. Install the required libraries.
3. Open Jupyter Notebook.
4. Open `AAPL Data Exploratory Analysis.ipynb`.
5. Place the CSV file in the appropriate folder.
6. Run the notebook cells sequentially.

### Using Google Colab

1. Open Google Colab.
2. Upload the `.ipynb` file.
3. Upload the `AAPL (3).csv` dataset.
4. Update the file path if required.
5. Run all cells.

---

## 📦 Installation

Install the required libraries using:

```bash
pip install pandas numpy matplotlib seaborn
```

---

## ✅ Conclusion

This project demonstrates the basic process of performing **Exploratory Data Analysis on AAPL stock data**.

The analysis covers dataset loading, data inspection, statistical summary, date conversion, missing-value checking, and calculation of price differences and daily return percentages.

The project provides a simple foundation for further stock-data analysis and visualization using Python.

---

## 👨‍💻 Author

**Dhanush G**

**Project:** AAPL Data Exploratory Analysis
