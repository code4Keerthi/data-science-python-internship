# Week 1 – Data Cleaning and Preprocessing

## Project Overview

This project focuses on acquiring, exploring, cleaning, and preprocessing the Adult Income dataset.

The main objective was to investigate the quality of a public dataset, identify missing values, unknown-value placeholders, duplicate records, inconsistent categorical labels, and unusual numerical values, and then apply appropriate preprocessing techniques.

The project was completed using Python and Pandas in Google Colab.

---

## Dataset

The dataset used for this project is the **Adult dataset** from the UCI Machine Learning Repository.

The dataset contains demographic and employment-related information and an income classification target.

### Dataset Characteristics

- Original observations: 48,842
- Original columns: 15
- Target variable: `income`
- Numerical and categorical variables
- Missing and unknown values were present
- Duplicate records were identified

---

## Objectives

The objectives of this project were to:

1. Acquire a public dataset.
2. Explore the structure and characteristics of the dataset.
3. Identify missing and unknown values.
4. Investigate duplicate records.
5. Examine categorical variables for inconsistencies.
6. Investigate unusual numerical values.
7. Apply appropriate data-cleaning techniques.
8. Verify the quality of the cleaned dataset.
9. Save the cleaned dataset for future analysis.

---

## Tools and Technologies

- Python
- Pandas
- Google Colab
- UCI Machine Learning Repository
- GitHub

---

## Data Quality Investigation

Several data-quality checks were performed before cleaning.

### Missing and Unknown Values

The dataset contained both actual missing values (`NaN`) and unknown-value placeholders represented by `?`.

The `?` values were identified in:

- `workclass`
- `occupation`
- `native-country`

After converting `?` to missing values, the following missing-value counts were observed:

| Column | Missing Values |
|---|---:|
| workclass | 2,799 |
| occupation | 2,809 |
| native-country | 857 |

A total of 3,620 rows originally contained at least one missing or unknown value.

### Duplicate Records

An initial duplicate check identified 29 duplicate rows that could be removed.

A second duplicate check was performed after standardizing the income labels. This identified 19 additional duplicate rows created by the standardization process.

### Income Label Inconsistency

The original target contained four textual representations:

- `<=50K`
- `<=50K.`
- `>50K`
- `>50K.`

The trailing periods were removed so that equivalent categories were represented consistently.

### Numerical Values

Numerical columns were investigated using descriptive statistics and targeted checks.

Potentially unusual values were investigated for:

- Age
- Hours worked per week
- Capital gain
- Capital loss

These values were not automatically removed because an extreme value is not necessarily an erroneous value.

---

## Data Cleaning Process

The following preprocessing steps were performed:

1. Converted `?` placeholders to missing values.
2. Removed duplicate records.
3. Standardized the `income` labels.
4. Removed rows containing missing values.
5. Reset the DataFrame index.
6. Performed a final duplicate check.
7. Removed the remaining duplicate records.
8. Verified the final dataset.
9. Saved the cleaned dataset as `adult_cleaned.csv`.

---

## Before and After

| Metric | Original Dataset | Final Cleaned Dataset |
|---|---:|---:|
| Rows | 48,842 | 45,175 |
| Columns | 15 | 15 |
| Missing values | Present | 0 |
| Duplicate rows | Present | 0 |
| Income labels | 4 representations | 2 standardized labels |

### Final Income Distribution

| Income Category | Rows |
|---|---:|
| `<=50K` | 33,973 |
| `>50K` | 11,202 |

---

## Final Data Quality

The final verification confirmed:

- 45,175 rows
- 15 columns
- 0 missing values
- 0 duplicate rows
- 2 standardized income categories

The cleaned dataset was saved as:

```text
adult_cleaned.csv