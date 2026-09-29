# Week 2 – Exploratory Data Analysis and Visualization

## Project Overview

This project was completed as part of Week 2 of the Data Science with Python internship.

The objective of this week was to perform Exploratory Data Analysis (EDA) on the cleaned Adult Income Dataset and identify patterns, distributions, relationships, and differences within the data using statistical analysis and data visualization.

The cleaned dataset prepared during Week 1 was used as the starting point for this analysis.

## Dataset

The dataset used is the Adult Income Dataset, also known as the Census Income Dataset.

The cleaned dataset contains:

- 45,175 observations
- 15 variables
- No missing values
- No duplicate rows

The dataset contains demographic, educational, occupational, financial, and income-related information.

## Objectives

The main objectives of this project were:

- To understand the structure and characteristics of the cleaned dataset.
- To calculate descriptive statistics for numerical variables.
- To analyze the distribution of important categorical and numerical variables.
- To identify patterns and relationships within the data.
- To compare income categories across different features.
- To examine correlations between numerical variables.
- To create meaningful visualizations using Python.
- To document the findings and interpretations from the exploratory analysis.

## Tools and Technologies

- Python
- Google Colab
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook / Google Colab
- Microsoft Word

## Analysis Performed

The following exploratory analyses were performed:

### Descriptive Statistics

Statistical summaries were calculated for numerical variables including:

- Age
- Final sampling weight (`fnlwgt`)
- Education number
- Capital gain
- Capital loss
- Hours per week

### Distribution Analysis

The distributions of important variables were examined using visualizations, including:

- Income distribution
- Education distribution
- Workclass distribution
- Age distribution
- Hours-per-week distribution

### Comparative Analysis

The following relationships were explored:

- Income across education levels
- Hours worked per week across income categories
- Age across income categories

### Correlation Analysis

A correlation heatmap was created to examine relationships between numerical variables.

### Income Proportion Analysis

Income proportions were also examined across:

- Workclass categories
- Education levels

These analyses helped identify differences in income composition across groups.

## Visualizations

The project contains the following visualizations:

- `income_distribution.png`
- `education_distribution.png`
- `workclass_distribution.png`
- `age_distribution.png`
- `hours_per_week_distribution.png`
- `income_across_education.png`
- `hours_by_income.png`
- `age_by_income.png`
- `correlation_heatmap.png`
- `income_proportions_workclass.png`
- `income_proportions_education.png`

## Project Structure

```text
Week_2_EDA_and_Visualization/
├── data/
│   └── adult_cleaned.csv
├── notebooks/
│   └── Week_2_EDA_and_Visualization.ipynb
├── images/
│   ├── income_distribution.png
│   ├── education_distribution.png
│   ├── workclass_distribution.png
│   ├── age_distribution.png
│   ├── hours_per_week_distribution.png
│   ├── income_across_education.png
│   ├── hours_by_income.png
│   ├── age_by_income.png
│   ├── correlation_heatmap.png
│   ├── income_proportions_workclass.png
│   └── income_proportions_education.png
├── report/
│   └── Week_2_EDA_and_Visualization_Report.docx
└── README.md
