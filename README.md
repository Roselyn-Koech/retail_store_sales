Data Cleaning, Transformation and Feature Preparation Using Python

1. Introduction
Data preprocessing is an essential stage in the data analysis process because raw datasets often contain errors, inconsistencies, duplicate records, missing values, and incorrect data types. These issues reduce data quality and can lead to inaccurate analysis and poor machine learning model performance.
The objective of this practical assignment was to preprocess a retail sales dataset using Python and the Pandas library. The dataset was cleaned, transformed, and prepared into an analysis-ready format suitable for further business analysis and predictive modeling.

2. Dataset Description
The dataset used in this practical consisted of retail store sales transactions. 
Dataset Link: C:\Users\cheru\retail_store_sales.csv
Clean Dataset:C:\Users\cheru\retail_store_sales.ipynb

It contained 12,575 records and 11 variables.
The dataset attributes included:
Variable	Description
Transaction ID	Unique transaction identifier
Customer ID	Unique customer identifier
Category	Product category
Item	Product purchased
Price Per Unit	Price of one unit
Quantity	Number of items purchased
Total Spent	Total transaction amount
Payment Method	Payment method used
Location	Store or customer location
Transaction Date	Date of purchase
Discount Applied	Indicates whether a discount was applied

The dataset initially required inspection for missing values, duplicate records, incorrect data types, and inconsistent formatting before analysis.
3. Data Cleaning Process
Several preprocessing techniques were applied to improve the quality of the dataset.
3.1 Dataset Loading
The dataset was imported into Jupyter Notebook using the Pandas library.
Activities performed:

Imported Pandas and NumPy libraries.

Loaded the CSV dataset.

Displayed the first records.

Examined dataset structure using info().



Generated descriptive statistics using describe().


3.2 Data Inspection
The dataset was inspected to determine:

Number of rows and columns

Variable data types

Missing values

Duplicate records


This step helped identify the preprocessing tasks required before analysis.

3.3 Handling Missing Values
Missing values were identified using:
df.isnull().sum()

The following strategies were applied:
Numerical Variables
Missing numerical values were replaced using the median to minimize the influence of extreme values.

Examples:
Price Per Unit
Quantity
Total Spent
Categorical Variables

Missing categorical values were replaced using the most frequently occurring (mode) value.
Examples:

Category
Item
Payment Method
Location
Discount Applied

This ensured that the dataset contained no unnecessary missing information.






3.4 Duplicate Removal
Duplicate records were identified using:
df.duplicated().sum()

Any duplicate transactions detected were removed using:
df.drop_duplicates()
This ensured that each transaction appeared only once in the cleaned dataset.

3.5 Data Type Conversion
The Transaction Date column was converted from an object data type into a proper datetime format.
df["Transaction Date"] = pd.to_datetime(df["Transaction Date"])
This enabled date-based analysis and feature extraction.


3.6 Text Standardization
Text variables were standardized to improve consistency by:

Removing leading and trailing spaces

Converting text to title case

The following variables were standardized:

Category

Item

Payment Method

Location

Discount Applied



3.7 Outlier Detection
Outliers were identified using the Interquartile Range (IQR) method on numerical variables.

The process involved:

Computing the first quartile (Q1)

Computing the third quartile (Q3)

Calculating the Interquartile Range (IQR)


Determining lower and upper limits

Identifying observations outside these limits

Boxplots were also used to visualize outliers where appropriate.



4. Feature Engineering
Several new variables were created to enhance analysis.
Purchase Month

The purchase month was extracted from the transaction date.
Purchase Year

The purchase year was extracted to enable yearly analysis.
Purchase Day

The day of the week was extracted to support sales trend analysis.

These engineered features make the dataset more useful for business intelligence and reporting.


5. Data Transformation
Normalization was performed using the MinMaxScaler from Scikit-learn.
The following variables were normalized:

Total Spent
Quantity 

Normalization scales values between 0 and 1, making variables comparable and improving the performance of many machine learning algorithms.


6. Validation of the Clean Dataset
After preprocessing, the dataset was validated to ensure quality.
Validation included:

Checking for remaining missing values.
Confirming duplicate records had been removed.
Verifying correct data types.
Confirming standardized text formatting.

The dataset was found to be clean and suitable for further analysis.



7. Results
The preprocessing exercise successfully achieved the following:

1.Loaded the retail sales dataset into Python.


2.Inspected the dataset structure.

3.Identified and handled missing values.

4.Removed duplicate records.

5.Converted transaction dates into datetime format.

6.Standardized text variables.

7.Detected outliers using the IQR method.

8.Created additional analytical features.

9.Applied Min-Max normalization to numerical variables.

10.Validated the final cleaned dataset.

The final dataset was successfully prepared for exploratory data analysis, visualization, and machine learning applications.
8. Conclusion
Data preprocessing is a fundamental stage in every data analytics project because it ensures data quality, consistency, and reliability. During this practical, the retail sales dataset was successfully cleaned, transformed, and validated using Python, Pandas, NumPy, and Scikit-learn.

The resulting dataset is free from major quality issues and is suitable for business reporting, statistical analysis, and predictive modeling. The practical also strengthened skills in data cleaning, feature engineering, and data transformation, which are essential competencies for a data analyst or data scientist.






