## WEEK 7
# Student Performance Data Analysis

## Project Overview

This project performs basic data cleaning and statistical analysis on the Student Performance dataset using Python and Pandas.

The project focuses on cleaning categorical data and calculating statistical measures for students' math, reading, and writing scores.

## Dataset

The dataset contains **1000 student records** with the following columns:

* gender
* race/ethnicity
* parental level of education
* lunch
* test preparation course
* math score
* reading score
* writing score

## Technologies Used

* Python
* Pandas
* NumPy
* Google Colab

## Data Cleaning

The categorical columns were cleaned using:

* `strip()` to remove extra spaces
* `lower()` to convert text into lowercase

The cleaned categorical columns are:

* Gender
* Race/Ethnicity
* Parental Level of Education
* Lunch
* Test Preparation Course

## Statistical Analysis

Statistical measures were calculated for:

* Math Score
* Reading Score
* Writing Score

The following measures were calculated:

* Mean
* Median
* Standard Deviation
* Q1
* Q2
* Q3

## Results

### Mean

| Subject |   Mean |
| ------- | -----: |
| Math    | 66.089 |
| Reading | 69.169 |
| Writing | 68.054 |

### Median

| Subject | Median |
| ------- | -----: |
| Math    |     66 |
| Reading |     70 |
| Writing |     69 |

### Standard Deviation

| Subject | Standard Deviation |
| ------- | -----------------: |
| Math    |             15.163 |
| Reading |             14.600 |
| Writing |             15.196 |

### Quartiles

| Subject |    Q1 | Q2 | Q3 |
| ------- | ----: | -: | -: |
| Math    |    57 | 66 | 77 |
| Reading |    59 | 70 | 79 |
| Writing | 57.75 | 69 | 79 |

## Objective

The main objectives of this project are:

1. To clean categorical features.
2. To calculate the mean of subject scores.
3. To calculate the median of subject scores.
4. To calculate standard deviation.
5. To calcul
