# Data Analytics Task 1 -- Data Cleaning and Preprocessing

## Project Overview

This project focuses on cleaning and preprocessing the Titanic dataset
to make it suitable for reliable data analysis.

The task identifies and handles common data-quality issues such as
missing values, duplicate records, inconsistent text formatting,
incorrect data types, and potential outliers.

## Objective

The main objective is to identify and fix common data-quality problems
in a raw dataset and prepare the data for further analysis.

## Dataset

**Dataset:** Titanic Dataset\
**Original size:** 891 rows × 12 columns

### Main Columns

-   PassengerId
-   Survived
-   Pclass
-   Name
-   Gender
-   Age
-   SibSp
-   Parch
-   Ticket
-   Fare
-   Cabin
-   Embarked

## Tools and Technologies

-   Python
-   Pandas
-   NumPy
-   Matplotlib
-   Google Colab
-   GitHub

## Data Cleaning Process

### 1. Missing Values

Missing values were checked using `isnull().sum()`.

The following missing values were identified:

  ------------------------------------------------------------------------
  Column                              Missing Values Treatment
  --------------------- ---------------------------- ---------------------
  Age                                            177 Filled using median

  Cabin                                          687 Created
                                                     `Cabin_Available`
                                                     indicator and removed
                                                     original column

  Embarked                                         2 Filled using mode
  ------------------------------------------------------------------------

### 2. Duplicate Records

Duplicate rows were checked using `duplicated()`.

-   Duplicate rows found: **0**
-   Duplicate Passenger IDs found: **0**

Therefore, no duplicate records required removal.

### 3. Text Standardization

Text columns were checked and standardized.

-   Unnecessary leading/trailing spaces were removed.
-   `Gender` values were standardized using consistent capitalization.
-   `Embarked` values were standardized using uppercase format.

### 4. Data Type Validation

Numeric columns were validated and converted using `pd.to_numeric()`
where required.

Important numeric columns include:

-   PassengerId
-   Survived
-   Pclass
-   Age
-   SibSp
-   Parch
-   Fare

### 5. Logical Validation

The dataset was checked for valid values, including:

-   `Survived`: 0 and 1
-   `Pclass`: 1, 2, and 3
-   Age values were checked for potentially impossible values.

### 6. Outlier Detection

Boxplots were used to inspect possible outliers in:

-   Age
-   Fare

Outliers were not automatically removed because extreme values may
represent genuine observations.

## Key Cleaning Decisions

-   **Age:** Median imputation was used because Age is numerical and the
    median is less affected by extreme values.
-   **Cabin:** A `Cabin_Available` feature was created because
    approximately 77.10% of Cabin values were missing.
-   **Embarked:** Mode imputation was used because only two values were
    missing.
-   **Duplicates:** No duplicate rows or Passenger IDs were found.
-   **Outliers:** Identified for review but genuine extreme observations
    were retained.

## Project Files

The repository can contain the following files:

``` text
DA-Task-Project/
│
├── README.md
├── Titan.ipynb
├── train_titanic.csv
├── cleaned_titanic.csv
└── change_log.xlsx
```

## Change Log

A change log documents the data-quality issues identified, the actions
taken, and the reasons for each cleaning decision.

## Final Outcome

After preprocessing, the retained dataset was validated for:

-   Missing values
-   Duplicate records
-   Data types
-   Text consistency
-   Logical values
-   Potential outliers

The cleaned dataset was exported as `cleaned_titanic.csv`.

## Interview Summary

> I used Python and Pandas in Google Colab to clean the Titanic dataset.
> I performed an initial data-quality assessment using `info()`,
> `isnull()`, and `duplicated()`. I handled missing Age values using
> median imputation, filled the two missing Embarked values using the
> mode, and addressed the highly incomplete Cabin column by creating a
> Cabin_Available feature. I also checked duplicates, standardized text
> formatting, validated data types, inspected outliers using boxplots,
> and exported the cleaned dataset and change log.

## Author

**Puja Kinhale**
