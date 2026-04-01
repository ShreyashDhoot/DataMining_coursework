# Experiment 4: Data Preprocessing on Airline Passenger Satisfaction Dataset

## Overview
This experiment focuses on cleaning and preprocessing the airline passenger satisfaction dataset using Python and pandas.

Primary notebook:
- experiment_4.ipynb

Reference notebook:
- DM_Exp_4_demo.ipynb (demo/starter notebook)

## Objective
Prepare raw airline passenger data for further analysis and modeling by applying common preprocessing operations.

## Files
- airline_passenger_satisfaction.csv: Main dataset used in the experiment
- data_dictionary.csv: Column descriptions and metadata
- experiment_4.ipynb: Practical implementation submitted for Experiment 4
- DM_Exp_4_demo.ipynb: Demonstration/starter notebook

## Libraries Used
- pandas
- numpy

## Workflow Implemented
1. Import required libraries.
2. Load dataset from CSV file.
3. Preview records using `head()`.
4. Inspect dataset structure and data types using `info()`.
5. Check missing values using `isnull().sum()`.
6. Handle missing values:
- Numerical columns filled with column mean.
- Remaining columns filled with mode.
7. Remove duplicate records using `drop_duplicates()`.
8. Detect and remove outliers using the IQR method:
- Compute Q1, Q3, and IQR for numeric columns.
- Define lower and upper bounds as:
	- lower = Q1 - 1.5 x IQR
	- upper = Q3 + 1.5 x IQR
- Remove rows where any numeric value lies outside bounds.

## Output of Experiment
At the end of preprocessing, the dataframe is cleaner and ready for downstream tasks such as:
- Exploratory Data Analysis (EDA)
- Feature engineering
- Machine learning model training

## How to Run
1. Open experiment_4.ipynb.
2. Run all cells from top to bottom.
3. Verify outputs after each preprocessing step.

## Learning Outcomes
After completing this experiment, you can:
- Assess dataset quality using summary inspection methods
- Handle missing values for numeric and categorical fields
- Remove duplicates from tabular data
- Apply IQR-based outlier detection and filtering