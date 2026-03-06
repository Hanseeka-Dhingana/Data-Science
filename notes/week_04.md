
# Data Preprocessing Techniques

Data preprocessing is the process of cleaning and preparing raw data before using it for analysis or machine learning. In real-world datasets, data is usually incomplete, inconsistent, or noisy. If we directly use such data, the results will be incorrect. Therefore, preprocessing is a very important step in Data Science.

Some common data preprocessing techniques include data cleaning, handling missing values, removing duplicates, encoding categorical variables, feature scaling, and data transformation. For example, if a dataset contains duplicate customer records, we remove them. If it contains text values like “Male” and “Female,” we convert them into numeric form (0 and 1) so that machine learning models can understand them.

Suppose we have a dataset of students’ marks, but some rows contain empty values or wrong entries. Before analyzing average performance, we must clean and fix these issues. That cleaning process is called data preprocessing.



# Feature Transformations

Feature transformation means changing the format or scale of data to make it more suitable for analysis or machine learning models.

Sometimes raw data is not in the correct form. For example, salary values may be very large compared to age values. If we use them directly in a model, salary may dominate the prediction. To solve this, we use techniques like normalization or standardization.

For example, suppose we have student marks out of 100 and attendance percentage out of 1000. We may divide attendance by 10 to bring it to the same scale. This is called scaling.

Another example is logarithmic transformation. If income values are very spread out, we may apply a log transformation to reduce the variation and make the data more balanced.

This is a very important exam question 
I will explain it clearly in **descriptive form**, then give you a small comparison table at the end.


When we work with data in Data Science, different features often have different ranges. For example, age may range from 18 to 60, while salary may range from 20,000 to 500,000. Because of this difference in scale, machine learning models may give more importance to salary than age. To solve this problem, we use scaling techniques such as normalization and standardization.

**Scaling** is the general process of adjusting the range of numerical features so they are on a similar scale. Normalization and standardization are two common types of scaling.

## Normalization & Standardization
**Normalization** is a technique that rescales data to a fixed range, usually between 0 and 1. It uses the minimum and maximum values of the dataset. The formula subtracts the minimum value from each data point and divides it by the range (maximum minus minimum). After normalization, the smallest value becomes 0 and the largest value becomes 1. This method is useful when we want all features to have the same bounded range. It is commonly used in image processing and neural networks.

**For example,** if student marks range from 50 to 100, normalization will convert them into values between 0 and 1. So 50 becomes 0, 100 becomes 1, and other values fall between them.

**Standardization** is a technique that transforms data so that it has a mean of 0 and a standard deviation of 1. Instead of using minimum and maximum values, it uses the mean and standard deviation of the dataset. After standardization, values are centered around zero, and most values fall between -3 and +3. This method is useful when data follows a normal distribution and is commonly used in algorithms like logistic regression, support vector machines, and k-means clustering.

For example, if the average salary is 50,000 and a person earns 60,000, standardization will calculate how many standard deviations this salary is above the mean.



# Missing Values in Python

In real datasets, missing values are very common. Missing values occur when data is not recorded or available. In Python, missing values are usually represented as NaN (Not a Number) in pandas.

Let us understand this step by step.


## Discovering What’s Missing

Before fixing missing values, we must first find them.

Example:

```python
import pandas as pd

data = {
    "Name": ["Ali", "Sara", "Ahmed", "Zara"],
    "Marks": [85, None, 90, None]
}

df = pd.DataFrame(data)

print(df.isnull())
```

This will show True where data is missing.

To quickly check if any missing values exist:

```python
print(df.isnull().any())
```

This tells us which columns contain missing values.



## Counting Missing Values

We can count how many values are missing in each column.

```python
print(df.isnull().sum())
```

If “Marks” shows 2, it means two values are missing in that column.

This step is important because it helps us understand how serious the missing data problem is.



## Filling in Missing Data

After finding missing values, we can fill them.

One common method is filling with the mean:

```python
df["Marks"] = df["Marks"].fillna(df["Marks"].mean())
```

Now missing marks are replaced with the average marks.

We can also fill with median:

```python
df["Marks"] = df["Marks"].fillna(df["Marks"].median())
```

Or fill with a specific value:

```python
df["Marks"] = df["Marks"].fillna(0)
```

The choice depends on the situation.



## Filtering Out Missing Values

Instead of filling, we can remove rows with missing values.

```python
df = df.dropna()
```

This removes all rows that contain missing data.

We can also remove only rows where a specific column has missing data:

```python
df = df.dropna(subset=["Marks"])
```

This removes rows where Marks is missing.

Filtering is useful when missing data is very small and does not affect the dataset much.



## Simple Real-Life Example

Suppose a bank has customer income data, but some income values are missing. The data scientist first checks how many values are missing. If only 5% are missing, they may fill them with the median income. If 60% are missing, they might remove the column completely. This entire process is part of data preprocessing.




# Data Preprocessing Life Cycle
In real-world problems, data is usually incomplete, inconsistent, noisy, or unstructured. Therefore, it must be properly prepared so that accurate results can be obtained.

Data preprocessing is one of the most important stages in Data Science because the quality of the final result depends on the quality of the data.


## 1. Data Cleaning

Data cleaning is the most important step. It involves fixing problems in the dataset.

This includes:

Handling missing values (filling or removing them)
Removing duplicate records
Correcting wrong or inconsistent data
Fixing formatting issues

For example, if a column contains both “Male” and “male,” we standardize them into one format.

If some salary values are missing, we may replace them with the median salary.


## 2. Data Integration

Sometimes data comes from multiple sources. In this step, we combine different datasets into one unified dataset.

For example, customer demographic data may be stored in one file, and loan repayment data in another file. These datasets are merged using a common key like customer ID.


## 3. Data Transformation

In this stage, data is converted into a suitable format for analysis.

This may include:

Normalization or standardization
Encoding categorical values into numbers
Converting dates into numerical form
Feature scaling

For example, converting “Yes” and “No” into 1 and 0 so that machine learning models can process them.



## 4. Data Reduction

Large datasets may contain unnecessary or irrelevant features. In this step, we reduce data size while keeping important information.

This can be done by:

Removing irrelevant columns
Feature selection
Dimensionality reduction

For example, if customer ID does not help in prediction, we remove it from the dataset.



## 5. Final Prepared Dataset

After completing all preprocessing steps, we get a clean and structured dataset that is ready for:

Data analysis
Machine learning modeling
Visualization


## Simple Real-Life Example

Suppose a company wants to predict employee salary.

First, it collects employee data.
Then it checks for missing values and duplicates.
Next, it fills missing salaries with the median value.
After that, it converts job titles into numeric codes.
Finally, it removes unnecessary columns like employee ID.

Now the dataset is ready for building a prediction model.


## Data Preprocessing Life Cycle (Flow Diagram)


```

Data Cleaning
        ↓
Data Integration
        ↓
Data Transformation
        ↓
Data Reduction
        ↓
Prepared Dataset (Ready for Modeling)
```

