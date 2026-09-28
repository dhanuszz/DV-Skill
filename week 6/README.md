## Week6

# Healthcare Dataset Analysis

## Project Overview

This project performs basic **data analysis and data cleaning** on a healthcare dataset using Python and Pandas.

The dataset contains patient information such as gender, age, medical condition, admission type, medical code, billing amount, admission date, and discharge date.

## Dataset

The dataset contains:

* **500 rows**
* **9 columns**

Main columns:

* Patient_ID
* Gender
* Age
* Medical_Condition
* Admission_Date
* Admission_Type
* Medical_Code
* Billing_Amount
* Discharge_Date

## Technologies Used

* Python
* Pandas
* Matplotlib
* Seaborn
* Google Colab

## Data Cleaning

The following data-cleaning operations were performed:

1. Checked the dataset using `head()`.
2. Checked column names using `columns`.
3. Checked data types using `dtypes`.
4. Checked the number of rows and columns using `shape`.
5. Checked missing values using `isnull().sum()`.
6. Replaced missing medical codes with `"Unknown"`.
7. Converted admission and discharge dates into date format.
8. Cleaned admission types using `strip()` and `lower()`.

## Data Analysis

The project performs basic analysis on the dataset.

For `Admission_Type`, the number of:

* Routine admissions
* Emergency admissions
* Urgent admissions

was calculated using `value_counts()`.

Statistical measures were also calculated for `Billing_Amount`, including:

* Mean
* Standard deviation
* Minimum
* Maximum
* Q1
* Median
* Q3

## Example

The `Billing_Amount` analysis includes:
## Output
<img width="1250" height="777" alt="image" src="https://github.com/user-attachments/assets/aa0f3942-97ed-4f55-b40f-5d9bf16729a9" />
<img width="1216" height="726" alt="image" src="https://github.com/user-attachments/assets/6cd95d33-0338-4c20-a296-2087a08595af" />
<img width="1313" height="703" alt="image" src="https://github.com/user-attachments/assets/7f28235f-98a7-41e7-ae20-8ebfd427b019" />
<img width="731" height="620" alt="image" src="https://github.com/user-attachments/assets/678c8b08-26bd-46d5-bd74-f67fa670b557" />


```python
df["Billing_Amount"].describe()
```

This provides the main statistical measures of the billing amounts.

## Conclusion

This project demonstrates basic **data cleaning, data inspection, and statistical analysis** using Python and Pandas on a healthcare dataset.
