Superstore Sales and Profit Data Analysis

Project Overview

Superstore Sales and Profit Data Analysis is a Python-based exploratory data analysis (EDA) project. The project analyzes a Superstore sales dataset to understand sales performance, profit distribution, product categories, delivery duration, discounts, and relationships between numerical variables.

The project uses:

Python

Pandas

NumPy

Matplotlib

Seaborn

The analysis begins by loading samplesuperstore.csv into a Pandas DataFrame and then performs data inspection, date conversion, feature creation, category analysis, statistical analysis, and visualization. The uploaded source is an automatically generated Google Colab Python file.

Table of Contents

Project Overview

Project Title

Objectives

Technologies Used

Libraries Used

Dataset

Project Workflow

Implementation Details

Data Loading

Data Inspection

Date Processing

Delivery Days Calculation

Category Analysis

Missing Value Analysis

Sales Analysis

Profit Analysis

Sales Distribution

Profit Distribution

Discount Analysis

Correlation Analysis

Visualizations

Methods and Functions

Installation

How to Run

Google Colab Instructions

Local Execution

Expected Output

Project Structure

Business Interpretation

Advantages

Limitations

Future Enhancements

Conclusion

Author

License

Project Title

Superstore Sales and Profit Data Analysis Using Python

Objectives

The main objective of this project is to perform exploratory analysis on Superstore business data and generate useful visual insights.

Specific Objectives

Load the Superstore CSV dataset.

Inspect the structure of the dataset.

Display the first few records.

Analyze data types and non-null values.

Generate descriptive statistics.

Convert Order Date into datetime format.

Convert Ship Date into datetime format.

Calculate delivery duration in days.

Identify unique product categories.

Check for missing values.

Calculate total sales by category.

Visualize sales by category.

Analyze the distribution of sales.

Analyze profit by category.

Compare sales across categories.

Analyze the distribution of profit.

Analyze profit variation across categories.

Inspect unique discount values.

Study the relationship between discount and profit.

Calculate correlations between numerical variables.

Visualize the correlation matrix using a heatmap.

Technologies Used

Technology

Purpose

Python

Main programming language

Pandas

Data loading, cleaning, transformation, grouping, and analysis

NumPy

Numerical data support

Matplotlib

Data visualization

Seaborn

Statistical visualization

Libraries Used

The project imports the following libraries:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

Pandas

Pandas is used as the primary data-analysis library.

Major operations include:

pd.read_csv()
pd.to_datetime()
df.head()
df.info()
df.describe()
df.groupby()
df.isnull()
df.select_dtypes()
df.corr()

NumPy

NumPy is imported for numerical computing support.

Matplotlib

Matplotlib is used to create and customize plots, including bar charts and figure layouts.

Seaborn

Seaborn is used for statistical visualizations such as:

Histograms

Bar plots

Box plots

Scatter plots

Heatmaps

Dataset

Dataset Name

Superstore Dataset

Input File

samplesuperstore.csv

The Python source loads the dataset with:

df = pd.read_csv("/content/samplesuperstore.csv")

Therefore, when running the original code in Google Colab, the CSV file is expected at:

/content/samplesuperstore.csv

The source code explicitly references columns including:

Order Date

Ship Date

Category

Sales

Profit

Discount

The uploaded Python source does not contain the actual CSV dataset, so this README does not claim additional dataset columns or numerical results that are not present in the source.

Project Workflow

The project follows this workflow:

             Superstore CSV Dataset
                       |
                       v
                Load Dataset
                       |
                       v
               Data Inspection
                       |
                       v
             Descriptive Statistics
                       |
                       v
               Date Conversion
                       |
                       v
            Delivery Days Feature
                       |
                       v
             Category Exploration
                       |
                       v
              Missing Value Check
                       |
                       v
          Sales and Profit Analysis
                       |
                       v
              Data Visualization
                       |
                       v
           Discount vs Profit Study
                       |
                       v
             Correlation Analysis
                       |
                       v
             Correlation Heatmap

Implementation Details

1. Import Required Libraries

The project starts by importing the required libraries:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

These libraries provide the required functionality for data processing and visualization.

Data Loading

The dataset is loaded using Pandas:

df = pd.read_csv("/content/samplesuperstore.csv")

The resulting DataFrame is stored in the variable:

df

The DataFrame is the main object used throughout the analysis.

Data Inspection

View First Records

The first records are displayed using:

df.head()

Purpose

This is used to:

Confirm that the dataset loaded successfully.

Preview the available records.

Understand the general structure of the data.

Display Dataset Information

The project uses:

df.info()

This provides information about:

Number of entries

Column names

Data types

Non-null values

Memory usage

The source performs df.info() before and after date conversion.

Descriptive Statistics

The project uses:

df.describe()

This generates descriptive statistics for numerical columns.

Typical statistics produced by this operation include:

Count

Mean

Standard deviation

Minimum

25th percentile

Median

75th percentile

Maximum

This gives an initial statistical understanding of the dataset.

Date Processing

The project processes two date columns.

Order Date

The Order Date column is converted to datetime format:

df['Order Date'] = pd.to_datetime(df['Order Date'])

This allows Python/Pandas to perform date-based calculations.

Ship Date

The Ship Date column is converted similarly:

df['Ship Date'] = pd.to_datetime(df['Ship Date'])

Date conversion is necessary before subtracting one date from another.

Delivery Days Calculation

The project creates a new feature called:

Delivery Days

The calculation is:

df['Delivery Days'] = (df['Ship Date'] - df['Order Date']).dt.days

Formula

Delivery Days = Ship Date - Order Date

The .dt.days operation converts the resulting time difference into a number of days.

Purpose

This feature provides a simple measure of the time between ordering and shipping.

Category Analysis

The project identifies unique categories using:

df['Category'].unique()

This returns the distinct values present in the Category column.

The category information is later used for sales and profit comparisons.

Missing Value Analysis

Missing values are checked using:

df.isnull().sum()

This calculates the number of missing values for each column.

Why Missing Value Analysis Is Important

Missing values can affect:

Statistical calculations

Visualizations

Grouped analysis

Correlation calculations

Machine-learning models

The uploaded source checks for missing values but does not perform an explicit missing-value replacement or deletion operation.

Sales Analysis

Total Sales by Category

The project calculates category-wise total sales:

category_sales = (df.groupby('Category')['Sales'].sum())

This operation:

Groups records according to Category.

Selects the Sales column.

Calculates the total sales for each category.

The result is stored in:

category_sales

Sales by Category Visualization

A bar chart is created using:

category_sales.plot(
    kind='bar',
    figsize=(8,5)
)

plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()

Purpose

The chart provides a visual comparison of total sales between product categories.

Chart Type

Bar Chart

X-Axis

Product category.

Y-Axis

Total sales.

Sales Distribution

The project uses a histogram:

plt.figure(figsize=(8,5))

sns.histplot(
    df['Sales'],
    bins=30
)

plt.title("Sales Distribution")
plt.show()

Purpose

The histogram shows how sales values are distributed throughout the dataset.

Chart Type

Histogram

Variable

Sales

Number of Bins

30

The histogram can help identify the general shape and spread of sales values.

Profit Analysis

Profit by Category

The project creates a Seaborn bar plot:

sns.barplot(
    data=df,
    x="Category",
    y="Profit"
)

plt.title("Profit by Category")
plt.show()

Purpose

This visualization compares profit across the available product categories.

Chart Type

Bar Plot

X-Axis

Category.

Y-Axis

Profit.

Sales Distribution by Category

Another category-wise sales visualization is created:

sns.barplot(
    data=df,
    x="Category",
    y="Sales"
)

plt.title("Sales Distribution by Category")
plt.show()

This provides a visual comparison of sales values among the categories.

Profit Distribution

The project uses a box plot:

sns.boxplot(
    data=df,
    y="Profit"
)

plt.title("Profit Distribution")
plt.show()

Purpose

A box plot helps examine the distribution and variation of profit values.

It can visually represent:

Central tendency

Spread

Potential extreme values

The source code does not separately calculate or label outliers.

Profit Variation Across Categories

The project creates a category-wise box plot:

sns.boxplot(
    data=df,
    x="Category",
    y="Profit"
)

plt.title("Profit Variation Across Categories")
plt.show()

Purpose

This visualization allows profit variation to be compared between categories.

Chart Type

Category-wise Box Plot

X-Axis

Category.

Y-Axis

Profit.

Discount Analysis

The project checks the unique discount values:

df["Discount"].unique()

This displays the distinct values present in the Discount column.

Impact of Discount on Profit

A scatter plot is used:

sns.scatterplot(
    data=df,
    x="Discount",
    y="Profit"
)

plt.title("Impact of Discount on Profit")
plt.show()

Purpose

The visualization is used to examine the relationship between:

Discount

and

Profit

Chart Type

Scatter Plot

X-Axis

Discount.

Y-Axis

Profit.

The source presents this as an analysis of the possible impact of discount on profit. It does not calculate a causal effect.

Correlation Analysis

The project selects numerical columns using:

numeric_df = df.select_dtypes(
    include="number"
)

This creates a DataFrame containing columns recognized as numerical.

Correlation Matrix

The correlation matrix is calculated using:

corr = numeric_df.corr()

The matrix is then displayed:

corr

Purpose

Correlation analysis helps identify the degree and direction of linear relationships between numerical variables.

The source calculates the correlation matrix but does not specify a particular correlation threshold for interpreting relationships.

Correlation Heatmap

The project visualizes the correlation matrix:

sns.heatmap(
    corr,
    annot=True
)

plt.title("Correlation Heatmap")
plt.show()

Features

Uses Seaborn.

Displays correlation values.

Uses annotations.

Provides a visual representation of numerical-variable relationships.

Chart Type

Correlation Heatmap

Visualizations

The project includes the following visualizations:

No.

Visualization

Purpose

1

Sales by Category

Compare total sales across categories

2

Sales Distribution

Study the distribution of sales

3

Profit by Category

Compare profit across categories

4

Sales Distribution by Category

Compare category-wise sales

5

Profit Distribution

Study overall profit variation

6

Profit Variation Across Categories

Compare profit distributions by category

7

Discount vs Profit

Study the relationship between discount and profit

8

Correlation Heatmap

Visualize correlations among numerical variables

Methods and Functions

Function / Method

Purpose

pd.read_csv()

Reads the CSV dataset

df.head()

Displays the first records

df.info()

Shows DataFrame structure

df.describe()

Generates descriptive statistics

pd.to_datetime()

Converts values to datetime

.dt.days

Extracts number of days from time differences

.unique()

Finds unique values

df.isnull()

Identifies missing values

.sum()

Calculates totals

.groupby()

Groups records

.select_dtypes()

Selects columns based on data type

.corr()

Calculates correlation matrix

plot()

Creates a Matplotlib plot

sns.histplot()

Creates a histogram

sns.barplot()

Creates a bar plot

sns.boxplot()

Creates a box plot

sns.scatterplot()

Creates a scatter plot

sns.heatmap()

Creates a heatmap

Installation

Requirements

Install Python 3.x.

Then install the required libraries:

pip install pandas numpy matplotlib seaborn

Or:

python -m pip install pandas numpy matplotlib seaborn

How to Run

Step 1: Download the Project

Place the following files in one project folder:

Task_1_BDA.py
samplesuperstore.csv
README.md

Step 2: Install Dependencies

Run:

pip install pandas numpy matplotlib seaborn

Step 3: Check Dataset Path

The original code uses:

df = pd.read_csv("/content/samplesuperstore.csv")

This path is designed for Google Colab.

For local execution, change it to:

df = pd.read_csv("samplesuperstore.csv")

Step 4: Run the Program

python Task_1_BDA.py

The program will execute the analysis and display the visualizations.

Google Colab Instructions

The source file was automatically generated from Google Colab.

To run it in Colab:

Step 1

Open Google Colab.

Step 2

Upload the Python notebook/code.

Step 3

Upload:

samplesuperstore.csv

Step 4

Make sure the file is accessible at:

/content/samplesuperstore.csv

Step 5

Run the code sequentially.

Step 6

Review the generated outputs and charts.

Local Execution

For a local system, use:

df = pd.read_csv("samplesuperstore.csv")

instead of:

df = pd.read_csv("/content/samplesuperstore.csv")

Then run:

python Task_1_BDA.py

Expected Output

After successfully running the project, the following outputs are expected:

Data Inspection

First records of the dataset.

Dataset information.

Descriptive statistics.

Data Processing

Converted Order Date.

Converted Ship Date.

New Delivery Days column.

Data Exploration

Unique categories.

Missing-value counts.

Unique discount values.

Analysis

Category-wise sales totals.

Correlation matrix.

Visualizations

Sales by Category.

Sales Distribution.

Profit by Category.

Sales Distribution by Category.

Profit Distribution.

Profit Variation Across Categories.

Impact of Discount on Profit.

Correlation Heatmap.

Project Structure

A recommended GitHub repository structure is:

Superstore-Sales-Analysis/
│
├── README.md
├── Task_1_BDA.py
├── samplesuperstore.csv
│
└── outputs/
    ├── sales_by_category.png
    ├── sales_distribution.png
    ├── profit_by_category.png
    ├── sales_distribution_by_category.png
    ├── profit_distribution.png
    ├── profit_variation_by_category.png
    ├── discount_vs_profit.png
    └── correlation_heatmap.png

The outputs folder is a recommended project organization. The uploaded source itself displays the plots but does not contain code that saves them as image files.

Business Interpretation

This project demonstrates how business transaction data can be explored using Python.

Sales Performance

Category-wise sales analysis can be used to compare the contribution of different product categories.

Profitability

Profit analysis helps examine differences in profitability and profit variation.

Delivery

The Delivery Days feature provides a simple measure of the time between order and shipping dates.

Discounts

The discount-versus-profit scatter plot allows the relationship between discount values and profit to be visually investigated.

Correlation

The correlation matrix provides an overview of relationships among numerical variables.

Advantages

Simple and easy-to-understand Python implementation.

Uses widely used data-analysis libraries.

Provides multiple types of visualizations.

Includes date-based feature creation.

Includes category-wise aggregation.

Includes missing-value checking.

Includes correlation analysis.

Suitable for learning exploratory data analysis.

Can be extended into a larger business analytics project.

Limitations

The uploaded source is primarily an exploratory data-analysis script. It does not include:

Machine-learning models.

Sales forecasting.

Profit prediction.

Customer segmentation.

Interactive dashboard development.

Automated report generation.

Advanced statistical hypothesis testing.

Explicit outlier removal.

Explicit missing-value treatment.

Time-series forecasting.

Model evaluation.

The source checks missing values but does not define a cleaning strategy. Similarly, the discount-versus-profit visualization investigates a relationship visually but does not establish causation.

Future Enhancements

The project can be expanded in several ways.

1. Data Cleaning

Add:

Duplicate detection.

Missing-value treatment.

Invalid-date checks.

Data-type validation.

Outlier analysis.

2. Time-Series Analysis

Analyze:

Daily sales.

Monthly sales.

Quarterly sales.

Yearly sales.

Seasonal sales trends.

3. Regional Analysis

Add analysis based on:

Region.

State.

City.

Postal code.

4. Product Analysis

Analyze:

Sub-category.

Individual products.

Best-selling products.

Most profitable products.

Low-profit products.

5. Customer Analysis

Analyze:

Customer purchasing patterns.

Customer-level sales.

Customer-level profit.

Repeat purchasing behavior.

6. Advanced Discount Analysis

Investigate:

Average profit by discount level.

Sales by discount level.

Profit margin by discount level.

Category-specific discount behavior.

7. Dashboard Development

The project can be converted into an interactive dashboard using tools such as:

Streamlit

Power BI

Tableau

Dash

8. Machine Learning

Possible future machine-learning tasks include:

Sales prediction.

Profit prediction.

Customer segmentation.

Demand forecasting.

These enhancements are proposed future work and are not implemented in the uploaded source.

Reproducibility

To reproduce the analysis:

Obtain the same Superstore CSV dataset.

Save it as:

samplesuperstore.csv

Install the required libraries.

Use the same Python source code.

Ensure the dataset path is correct.

Run the program.

Compare the generated tables and plots.

Quick Start

# Install required packages
pip install pandas numpy matplotlib seaborn

# Put the dataset in the project directory
# samplesuperstore.csv

# Run the Python program
python Task_1_BDA.py

For Google Colab, upload the CSV and use the original path:

/content/samplesuperstore.csv

Example Core Code

The major operations performed by the project are:

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("/content/samplesuperstore.csv")

df.head()
df.info()
df.describe()

df['Order Date'] = pd.to_datetime(df['Order Date'])
df['Ship Date'] = pd.to_datetime(df['Ship Date'])

df['Delivery Days'] = (
    df['Ship Date'] - df['Order Date']
).dt.days

df['Category'].unique()
df.isnull().sum()

category_sales = (
    df.groupby('Category')['Sales'].sum()
)

category_sales.plot(
    kind='bar',
    figsize=(8,5)
)

plt.title("Sales by Category")
plt.ylabel("Total Sales")
plt.show()

The project then continues with the sales, profit, discount, and correlation visualizations described in this README.

Learning Outcomes

After completing this project, a learner can understand how to:

Load CSV data with Pandas.

Work with DataFrames.

Inspect dataset information.

Generate descriptive statistics.

Convert string dates into datetime objects.

Calculate date differences.

Create derived columns.

Find unique values.

Detect missing values.

Group data by categories.

Calculate aggregated sales.

Create bar charts.

Create histograms.

Create box plots.

Create scatter plots.

Select numerical columns.

Calculate correlation matrices.

Create correlation heatmaps.

Present business data visually.

Conclusion

The Superstore Sales and Profit Data Analysis project demonstrates a practical exploratory data-analysis workflow using Python.

The project starts by loading the Superstore dataset and inspecting its structure. It then converts order and shipping dates into datetime format and calculates delivery duration. The analysis continues with category exploration, missing-value checking, sales aggregation, profit analysis, sales and profit distribution analysis, discount-versus-profit visualization, and correlation analysis.

The project is useful as an academic or beginner-to-intermediate data-analysis project because it demonstrates the complete basic process of moving from a raw CSV dataset to meaningful tables and visualizations.

The analysis can be further developed into an advanced business-intelligence solution by adding time-series analysis, regional analysis, product analysis, interactive dashboards, and machine-learning models.

Author

Name: Dhanush G

Project: Superstore Sales and Profit Data Analysis

Programming Language: Python

Project Type: Exploratory Data Analysis / Business Data Analytics

License

This project is intended for educational and academic purposes.

The license and usage rights of the samplesuperstore.csv dataset should be verified according to the original dataset source.

Repository Description

Python-based Superstore Sales and Profit Data Analysis project using Pandas, NumPy, Matplotlib, and Seaborn. Includes data inspection, date processing, delivery-day calculation, category-wise sales analysis, profit analysis, discount-versus-profit visualization, and correlation heatmap analysis.

Keywords

Python
Pandas
NumPy
Matplotlib
Seaborn
Data Analysis
Exploratory Data Analysis
EDA
Business Analytics
Superstore Dataset
Sales Analysis
Profit Analysis
Data Visualization
Correlation Analysis
Data Science
