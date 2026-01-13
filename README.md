# World Population Data Analysis

## Overview

This project analyzes world population data using Python. The dataset contains population figures for multiple countries across several years. The goal is to clean the data, explore trends, and visualize population distributions, with a focus on identifying the most populous countries.

## Dataset Description

The dataset includes the following structure:

* **Country Name**: Name of the country (categorical variable)
* **1960 – 2024**: Population values for each year (numeric variables)

There are no gender or age variables in this dataset. All analysis is based strictly on country-level population data over time.

## Objectives

* Clean the dataset by handling missing values
* Identify and rank countries by population
* Visualize population distributions using bar charts
* Perform basic exploratory data analysis

## Tools and Libraries Used

* Python
* Pandas
* Matplotlib
* Seaborn (optional, for correlation visualization)

## Data Cleaning

Missing values are handled by:

* Checking for null values across the dataset
* Dropping rows with missing population data when required for analysis

Example:

```python
df.isna().sum()
df = df.dropna()
```

## Analysis Performed

### Top 10 Most Populous Countries (2024)

The population data for 2024 is used to identify the top 10 most populous countries.

```python
top10 = df[['Country Name', '2024']] \
    .dropna() \
    .sort_values(by='2024', ascending=False) \
    .head(10)
```

## Data Visualization

### Bar Chart: Top 10 Most Populous Countries (2024)

A bar chart is used to visualize the population distribution of the top 10 countries.

```python
plt.figure(figsize=(10, 6))
plt.bar(top10['Country Name'], top10['2024'])
plt.xlabel('Country')
plt.ylabel('Population')
plt.title('Top 10 Most Populous Countries (2024)')
plt.show()
```

## Key Notes

* Bar charts are used for categorical comparisons (Country Name)
* Line charts are more appropriate for trends over time
* Correlation analysis applies only to numeric columns

## Limitations

* No age or gender breakdown is available
* Analysis is limited to country-level population totals

## How to Run the Project

1. Clone the repository
2. Install required libraries:

   ```bash
   pip install pandas matplotlib seaborn
   ```
3. Run the analysis script or Jupyter notebook

## Author

Joseph Danquah

## License

This project is for academic and learning purposes. Feel free to use and modify it.
