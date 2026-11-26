# Preparing Data

Well-defined data determines a clear direction for analysis, while good data quality will ensure that the analysis results are of high quality and trustworthy. The data obtained cannot be directly analyzed because there may be errors and inaccuracies during the loading process from the original source. Therefore, it is important to check and improve the quality of the data obtained.

### A. Creating an Issues Log

An issues log is a table used to record data quality issues found in the data. The table 
consists of:

- ID: a unique code to identify the issue in the data 
- Table Name: the name of the table containing the data quality issue 
- Column Name: the name of the column where the issue was found 
- Issue Type: the type of data issue found (Null, Inconsistent Format, etc.) 
- Problem description: an explanation of the data quality issues found 
- Number of rows: the number of rows containing problematic data 
- Status: based on whether the issue can be resolved 
- Magnitude: the percentage of rows that could not be resolved 
- Solution: Methods used to handle data that could be resolved 

The issue log will also be included in the dataset Excel file along with the raw data and the results of the data cleaning.

### B. Mapping Issues in the Data

Once the issue log table has been created, the next step is to examine the data to identify 
what issues exist and determine which ones can be addressed and which cannot.

This analysis is performed by converting the data, which was originally in the form of a range within a worksheet into a table format, which simplifies the inspection and filtering 
process.

After that, the columns are checked one by one using the filter button located in the table 
header. In that section, values or data that differ from the majority of the other data can be clearly identified.

Once the type and description of the problematic data are identified, the number of data 
rows can be calculated to determine the magnitude or percentage of the data relative to the 
total.

The results of the dataset analysis used in this study indicate that there are two types of 
data issues: null values and inconsistent data formats. Here is a more detailed explanation.

1. Null

A null value represents the absence of data in a record or data row. This can be caused
by issues during data loading. If the data source is known, the cause of the problem can
be traced; however, at this time, this cannot be done because the data is synthetic data
obtained from a free source.

In this case, there are two types of null values: those whose cause is unknown and those
whose values can be inferred from other columns. Some data columns contain only one type, while others contain both.
- The Clicks, Conversions, and Conversions_Rate columns contain both types of null values: resolvable and unresolvable. Further details will be discussed in the next section. 
- The Impressiond, Cost, Leads, and Sale_Amount columns contain unrecoverable null values.

2. Inconsistent Data Formats

A single data column may contain different formats; this can be caused by input errors in
the system. To address this, apply a single format that applies to the entire dataset. In the dataset, inconsistent data formatting was found in the following columns.
- The Campaign_Name column contains data with spelling errors and incorrect spacing. 
- The Ad_Date column has inconsistent date formats. 
- The "Location" column contains data with incorrect spelling. 
- The "Device" column contains data with inconsistent capitalization. 
All of these formatting inconsistencies can be resolved by establishing a consistent writing format to be used throughout.

### C. Handling Problematic Data

#### Solvable

After identifying which data issues can be resolved and which cannot, the next step is to
address the data that can be resolved.

1. Null

Null data that can be addressed is found in the following columns.

- The Clicks, Conversions, and Conversions_Rate columns 

These three columns are interrelated because they are linked by the formula used, 
namely: <br>
![conversion_rate]()

Therefore, to find one of the values, you can calculate the other two. To find the Conversions value, use the following formula. <br>
![conversion]()

And to determine the value of Clicks, you can use the following formula. <br>
![click]()

Using this method, the number of null values in the Clicks column was reduced by 17%, in the Conversions column by 15%, and in the Conversions_Rate column by 76%.

2. Inconsistent data formats

This formatting issue was resolved differently for each column.

- Campaign_Name column 
Data containing spelling errors and incorrect spacing is corrected by using the CONCAT function to create a new, correctly spelled version. Since there is only one campaign name in this column, it is possible to use this function.

- Ad_Date Column  
Dates with different formats are handled by converting them to the universal mm/dd/yyyy format using the DATE function, which is specifically designed for date data.

- Location Column  
Data with incorrect spelling is handled by using the IF function to select the conditions to be changed and the PROPER function to adjust capitalization in the data.

- Device Column
Data with inconsistent capitalization can be handled by using the PROPER function to standardize capitalization throughout the entire data column.

#### Unsolved

After all resolvable data has been processed, the next step is to evaluate the data that
cannot be resolved. The purpose of this is to determine the percentage of data that cannot
be resolved, because if it exceeds 20%, it could affect the accuracy of the analysis results.

Note: The 20% threshold is not an actual standard; it applies only to this project.

Here are the results of the evaluation of the data that could not be resolved. All of it comes from null data that could not be resolved.

- Clicks Column: 3.6% 
- Impressions column: 2.1% 
- Cost Column: 3.7% 
- Leads column: 1.8% 
- Conversions Column: 2.4% 
- Conversions_Rate Column: 5.9%  
- Sale_Amount Column: 5.3% 

There is no data with a magnitude level above 20%, meaning the data is ready for analysis
and the results obtained can be more accurate.

---

Here are the problems and their solutions as found in the data; or you can view them in the dataset file [here](https://github.com/CHodes-dev/GoogleAds-Performance-Analysis/blob/main/docs/googleads_performance_2024.xlsx).


