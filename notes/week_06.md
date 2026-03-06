# What is the Imputation?

Imputation in Data Science is the process of replacing missing values in a dataset with some meaningful substitute value. In real-world data, missing values are very common. For example, a survey form might have unanswered questions, a medical dataset may have missing test results, or an e-commerce dataset might have incomplete customer information. Since most machine learning algorithms cannot work with missing values (NaN), we need to handle them before modeling. The method we use to fill those missing values is called imputation.

Suppose we have a dataset of employees where one person’s salary is missing. If we simply delete that row, we lose information about that employee’s age, experience, and other details. If many rows have missing values, deleting them can reduce the dataset size significantly and weaken the model. Instead, we can replace the missing salary with a reasonable estimate, such as the average salary of other employees. This replacement process is imputation.

Imputation is important because it allows us to keep as much data as possible while making the dataset usable for analysis and modeling. However, it must be done carefully. Poor imputation can introduce bias into the dataset and affect model performance.

## Real-Life Example

Suppose we have this dataset:

| Age | Salary |
| --- | ------ |
| 25  | 30000  |
| 30  | NaN    |
| 35  | 50000  |
| 40  | 60000  |

Here salary for age 30 is missing.

Instead of deleting that row, we can fill it using:

* Mean salary
* Median salary
* Most frequent value
* Predicted value

This process is **Imputation**.



## Types of Imputation

### 1) Mean Imputation

Replace missing value with the **mean (average)** of that column.

**Example:**
If salaries are 30000, 50000, 60000
Mean = 46666
We replace NaN with 46666.

Best for: Normally distributed numeric data.


### 2) Median Imputation

Replace with **median (middle value)**.

Best for: Data with outliers.

Why?

Because median is not affected by extreme values.


### 3) Mode Imputation

Replace with **most frequent value**.

Used for:

* Categorical data
* Gender column
* Country column

**Example:**
If most people are “Male”, fill missing Gender with “Male”.


### 4) Forward Fill / Backward Fill

Used in time-series data.

**Example:**
Stock prices missing on one day → use previous day's price.


### 5) Model-Based Imputation

We use machine learning to predict missing values.

**Example:**
- Use regression to predict missing salary based on age and experience.
- More advanced and accurate.

