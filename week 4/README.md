# AAPL Stock Data Analysis Using Python

## Project Overview

This project analyzes Apple Inc. (AAPL) historical stock market data using Python and Pandas.

The dataset contains daily stock information such as Open, High, Low, Close, Adjusted Close, and Volume. Additional columns were created to calculate the daily price change and daily percentage return.

## Technologies Used

* Python
* Pandas
* Google Colab
* CSV Dataset

## Dataset

The dataset used in this project is `AAPL.csv`.

It contains the following columns:

* Date
* Open
* High
* Low
* Close
* Adj Close
* Volume

The dataset contains 10,409 rows of historical Apple stock data.

## Project Steps

### 1. Import Pandas

```python
import pandas as pd
```

Pandas is used for loading and analyzing the dataset.

### 2. Load the Dataset

```python
data = pd.read_csv("AAPL.csv")

print("Dataset loaded successfully")
```

The AAPL CSV file is loaded into a Pandas DataFrame.

### 3. View the Dataset

```python
data.head()
```

This displays the first five rows of the dataset.

### 4. Calculate Daily Delta

```python
data["Daily Delta"] = data["Close"] - data["Open"]

data.head()
```

Daily Delta represents the difference between the closing price and opening price.

Formula:

```text
Daily Delta = Close - Open
```

A positive value means the closing price was higher than the opening price.

A negative value means the closing price was lower than the opening price.

### 5. Find Top 10 Positive Daily Changes

```python
top_10 = data[data["Daily Delta"] > 0].sort_values(
    "Daily Delta", ascending=False
).head(10)

print(top_10[["Date", "Open", "Close", "Daily Delta"]])
```

This identifies the 10 days with the largest positive difference between the opening and closing prices.

### 6. Calculate Daily Return

```python
data["Daily Return"] = (
    (data["Close"] - data["Open"]) / data["Open"]
) * 100

data.head()
```

Daily Return shows the percentage change between the opening and closing prices.

Formula:

```text
Daily Return = ((Close - Open) / Open) × 100
```

### 7. Find Top 10 Daily Returns

```python
top_10_returns = data.sort_values(
    "Daily Return", ascending=False
).head(10)

print(top_10_returns[["Date", "Open", "Close", "Daily Return"]])
```

This displays the 10 days with the highest daily percentage returns.

## Results

### Top Daily Delta

The highest Daily Delta in the dataset was:

```text
Date: 2022-02-24
Open: 152.580002
Close: 162.740005
Daily Delta: 10.160003
```

### Top Daily Return

The highest Daily Return in the dataset was:

text
Date: 1998-01-02
Open: 0.121652
Close: 0.145089
Daily Return: 19.265610%
## Output
<img width="1287" height="702" alt="image" src="https://github.com/user-attachments/assets/6900dcbd-1895-4cf3-9107-bad8def847d2" />
<img width="1317" height="612" alt="image" src="https://github.com/user-attachments/assets/5e3c4a33-09f5-4667-9f44-e227033b599b" />
<img width="1316" height="707" alt="image" src="https://github.com/user-attachments/assets/6f5c96ef-e48f-4a44-bcdd-8127a5126979" />


## Conclusion

This project demonstrates how Python and Pandas can be used to analyze historical stock market data.

The analysis calculates daily price changes and percentage returns and identifies the dates with the highest positive movements in Apple's stock price.

## Files in This Repository

```text
AAPL-Stock-Analysis/
│
├── AAPL.csv
├── AAPL_Stock_Analysis.ipynb
└── README.md
```

## How to Run

1. Download or clone this repository.
2. Open the Jupyter Notebook in Google Colab.
3. Upload `AAPL.csv` to the Colab environment.
4. Run the notebook cells in order.

## Author

Bala Suthan

BCA Student
