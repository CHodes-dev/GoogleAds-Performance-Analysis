# Cleaning Data

When cleaning the data, the CLEAN Framework is used. As the ‘C’ (Conceptualise data) stage has already been completed, this stage will focus on determining which data issues can be resolved and which cannot, as well as transforming the data to improve the quality of the analysis results.

The data was initially imported and cleaned using Microsoft Excel. This was chosen because the application is still capable of handling the volume of data contained in the dataset.

Here are the problems and their solutions as found in the data; or you can view them in the dataset file [here](https://github.com/CHodes-dev/GoogleAds-Performance-Analysis/blob/main/docs/googleads_performance_2024.xlsx).

| ID | Table | Column | Issue_type | Issues_desc | Row_count | Magnitude | Status | Resolution |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| DQ_01 | GoogleAd_Performance | Campaign_Name | Inconsistent data formats | miss spelling for "Data Analytics Course" | 1920 |  | Solvable | using CONCAT function |
| DQ_02 | GoogleAd_Performance | Clicks | Nulls | missing data | 93 | 3.6% | Unsolvable |  |
| DQ_03 | GoogleAd_Performance | Clicks | Nulls | missing data | 19 |  | Solvable | using IFS and IF |
| DQ_04 | GoogleAd_Performance | Impressions | Nulls | missing data | 54 | 2.1% | Unsolvable |  |
| DQ_05 | GoogleAd_Performance | Cost | Nulls | missing data | 97 | 3.7% | Unsolvable |  |
| DQ_06 | GoogleAd_Performance | Leads | Nulls | missing data | 48 | 1.8% | Unsolvable |  |
| DQ_07 | GoogleAd_Performance | Conversions | Nulls | missing data | 63 | 2.4% | Unsolvable |  |
| DQ_08 | GoogleAd_Performance | Conversions | Nulls | missing data | 11 |  | Solvable | using IFS and IF |
| DQ_09 | GoogleAd_Performance | Conversions_Rate | Nulls | missing data | 153 | 5.9% | Unsolvable |  |
| DQ_10 | GoogleAd_Performance | Conversions_Rate | Nulls | missing data | 474 |  | Solvable | using IFS and IF |
| DQ_11 | GoogleAd_Performance | Sales_Amount | Nulls | missing data | 139 | 5.3% | Unsolvable |  |
| DQ_12 | GoogleAd_Performance | Ad_Date | Inconsistent data formats | two different date formatting, with (-) and (/) | 551 |  | Solvable | Change data format into mm/dd/yyyy, using DATE function |
| DQ_13 | GoogleAd_Performance | Location | Inconsistent data formats | miss spelling for "Hyderabad" | 1944 |  | Solvable | Using IF and PROPER |
| DQ_14 | GoogleAd_Performance | Device | Inconsistent data formats | using uppercase and lowercase in the same category | 2600 |  | Solvable | Using PROPER function |
