#DS0001 Directory Explanation

In addition to the `README.md` file that you are reading, this directory contains the following files:

- `06724-0001-Data.txt`
- `robbins_etl_example_06724-0001-Data-Crosswalk-1994.xlsx`
- `robbins_etl_example_06724-0001-Data-1994.xlsx`
- `robbins_etl_example_06724-0001-Data-Analysis-1994.accdb`
- `robbins_etl_example_06724-0001-Data-Analysis-1994.xlsx`

--

 `06724-0001-Data.txt` stores household-level responses to questions about households on the National Health Interview Survey, 1994. The file has 48,584 records that record 52 values in 335 fixed width record positions. This is the household data downloaded from this [ICPSR site](http://bit.ly/1PNSDlW). 

`robbins_etl_example_06724-0001-Data-Crosswalk-1994.xlsx` provides the ICPSR 6724 NHIS 1994 field names and their corresponding proposed Oracle field name after applying transformation rules. The file has two sheets: crosswalk, transformation_rules

`robbins_etl_example_06724-0001-Data-1994.xlsx` is an spreadsheet that contains the data from `06724-0001-Data.txt` after field names have been standardized.

`robbins_etl_example_06724-0001-Data-Analysis-1994.accdb` includeds the data from the `robbins_etl_example_06724-0001-Data-1994.xlsx` spreadsheet. It also includes 75 SQL queries that are used to assess the accuracy of the meta-data (data dictionary) information provided in `06724-Codebook.pdf`. The two types of queries are 1) queries that identify distinct values for each of the 52 fields, and 2) queries that identify the counts of the various distinct values for some of the fields. (Not all fields had associated count information in `06724-Codebook.pdf`.

`robbins_etl_example_06724-0001-Data-Analysis-1994.xlsx` provides a field by field analysis with regards to the actual types of values in fields, as well as when possible, a field-by-field comparison of distinct value counts indicated in `06724-Codebook.pdf` and found in queries using `robbins_etl_example_06724-0001-Data-Analysis-1994.accdb`. It includes two primary worksheets (Unique_Values_Analysis, Unique_Values_Counts_Analysis) as well as four supplementary worksheets that provide additional data or discrepencies between the files. 

Note 1: 
==

This directory contains Excel and Access files. These two desktop applications were used so that as little code as possible might misrepresent the actual data in the `06724-0001-Data.txt` file. Misrepresentation of source/input data attributes, early in a ETL project, when using code to summarize the data, is particularly likely. An example of misinterpretation that could easily occur in a program but not be seen identified would be importing codes such as 01, 02 without assuring that their data type stays as character/string. This would lead to data in the final database that is different from the original data source. 

Note 2:
===

The representation of distinct data values in Excel or Access, which is relatively easy to create, also provides information that can be used as benchmarks when testing that the data in the final storage location (in this case, Oracle tables) is accurate.

Note 3:
===

Most importantly, this information allows the person (or program) performing the ETL to first validate the claims made by the organization that provided the ETL source data. Indeed, I did find discrepancies between the description of the data and the actual data itself.
