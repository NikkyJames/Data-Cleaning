# Data Cleaning

# Project Overview

This project demonstrates a systematic approach to cleaning and preparing a deliberately messy transaction dataset for analysis.

The dataset contains 10,000 transaction records and 8 columns with missing values, invalid placeholders, inconsistent data types, and data consistency issues.

The objective was to transform the raw dataset into a clean, reliable, and analysis-ready dataset while documenting the cleaning decisions made throughout the process.

# Objectives

Identify and handle missing values
Standardize invalid ERROR and UNKNOWN entries
Correct inappropriate data types
Check and handle duplicate records
Standardize categorical values
Detect and evaluate outliers using the IQR method
Validate relationships between related numerical fields
Produce a clean, analysis-ready dataset

# Tools & Technologies

Python
Pandas
NumPy
Jupyter Notebook

## Data Cleaning Process
# Data Quality Assessment

The original dataset contained:

10,000 rows
8 columns
Missing values across several columns
ERROR and UNKNOWN placeholder values
Incorrect data types
Potential numerical inconsistencies
No exact duplicate rows were present in the original dataset.

# Missing Value Handling
Missing values were handled using appropriate strategies based on the nature of each column:

Item: Mode imputation
Quantity: Median imputation
Price Per Unit: Median imputation
Total Spent: Calculated using Quantity × Price Per Unit
Payment Method: Mode imputation
Location: Mode imputation
Transaction Date: Mode date imputation

This approach preserved the available transaction records while maintaining consistency within the dataset.

# Data Standardization

Invalid placeholder values such as ERROR and UNKNOWN were converted to missing values and subsequently handled.

Categorical values were also standardized to ensure consistent formatting.

 # Duplicate Check

The dataset was checked for duplicate records.

Result: 0 duplicate rows were found.

No transaction records were removed due to duplication.

 # Data Type Correction
The columns were converted to appropriate data types:

Transaction ID → String
Item → String
Quantity → Integer
Price Per Unit → Float
Total Spent → Float
Payment Method → String
Location → String
Transaction Date → Datetime

# Outlier Detection
The Interquartile Range (IQR) method was used to identify potential numerical outliers.

Quantity: No outliers detected
Price Per Unit: No outliers detected
Total Spent: 240 potential outliers identified

The Total Spent outliers were all valued at 25.0 and were validated against the transaction quantities and prices.

Since these values were valid and consistent with the underlying transactions, they were retained rather than removed or capped.

#  Data Consistency Validation
An additional validation was performed by comparing:

Total Spent with Quantity × Price Per Unit

# The check identified:
733 inconsistent transactions
7.33% of the dataset

These inconsistencies were corrected using the calculated value:
Total Spent = Quantity × Price Per Unit

# After correction:
Remaining inconsistencies: 0

This additional validation ensured that related numerical fields were internally consistent.

## Before vs After Cleaning

# Rows
Before: 10,000
After: 10,000

# Columns
Before: 8
After: 8

# Missing Values
Before: 6,826
After: 0

# Duplicate Rows
Before: 0
After: 0

# Correct Data Types
Before: 0 / 8
After: 8 / 8

# Total Spent Inconsistencies
Before: 733
After: 0


# Final Dataset Quality
The final dataset contains:

10,000 rows
8 columns
0 missing values
0 duplicate rows
Appropriate data types
0 remaining Total Spent inconsistencies
The cleaned dataset was also exported as a CSV file for potential downstream analysis and visualization.

# Conclusion

This project demonstrates a complete data cleaning workflow, from initial data quality assessment through missing value treatment, standardization, data type correction, outlier evaluation, and consistency validation.
An additional consistency check was particularly important because it identified 733 transactions where Total Spent did not agree with Quantity × Price Per Unit. Correcting these values resulted in a fully consistent dataset.
The final dataset is clean, validated, and ready for further analysis or machine learning applications.

# Internship

Organization: Oasis Infobyte
Program: Data Analytics Internship
Hashtags: #OasisInfobyte #OIBSIP

# Author
Adenike Adetuberu


