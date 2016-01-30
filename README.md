# ETL EXAMPLE STEP 3

**Designing Tables and Formalizing "Manual" Steps**

You are reading the `README.md` file in the `ETL_03` repository for Russ Robbins. This repository shows files related to indicating the:

 - design of proposed Household tables in terms of primary keys, foreign keys, and other fields
 - lock down the steps to "manually" take the household data, extract it, transform it, and load it into Oracle 12c.

----------

Inputs to Step 3
===

**from Step 1**

 - `06724-Codebook.pdf` in https://github.com/robbinsr/ETL_2/tree/master/DS1_Household 
 - `06724-0001-Data.txt` in https://github.com/robbinsr/ETL_2/tree/master/DS1_Household/DS0001

and

**from Step 2**

- `robbins_etl_06724-0001-Data.xlsx`
- `robbins_etl_06724-0001-Data-Crosswalk-1994.xlsx`
- `robbins_etl_06724-0001-Data-Analysis-1994.accdb`
- `robbins_etl_06724-0001-Data-Analysis-1994.xlsx`
- Each of these files can be found at: https://github.com/robbinsr/ETL_2/tree/master/DS1_Household/DS0001
 
---------
Processing for Step 3
===


- Designing the database tables
- Indicating the necessary steps in a plan

---

Outputs for Step 3
===

**Tables Design**

   
-  `robbinsr_etl_06724-0001-Data-Code-Tables-Design-1994.vsdx`
-  `robbinsr_etl_06724-0001-Data-Code-Tables-Design-1994.pdf`
-  Both of these files can be found at: https://github.com/robbinsr/ETL_3/tree/master/DS1_Household/DS0001


**Manual" ETL Plan**


1.  - Download NHIS 1994 Household data from [ICPSR](http://bit.ly/1ddSUOC)
1.  - Review data element descriptions in `06724-Codebook.pdf`
1.  - Import data from `06724-0001-Data.txt` into `etl_robbinsr_06724-0001-Data.xlsx` using record positions from `06724-Codebook.pdf`
1.  - Decide upon field name standardization scheme
1.  - Apply field name standardization scheme to field names in `etl_robbinsr_06724-0001-Data.xlsx`
1.  - Import `etl_robbinsr_06724-0001-Data.xlsx` into `etl_robbinsr_06724-0001-Data.accdb`
1.  - Create queries that indicate unique values for every field
1.  - Compare results from queries with information in `06724-Codebook.pdf`
1.  - Note discrepancies
1.  - Create queries that indicate counts of particular values for particular fields if these are provided in `06724-Codebook.pdf`
1.  - Compare results from queries and information in `06724-Codebook.pdf`
1.  - Note discrepancies
1.  - Design database tables to handle each type of data (primary key, foreign key, code, count, and identification field
1.  - Create CDB in Oracle 12c
1.  - Create PDB in CDB in Oracle 12c
1.  - Use SQL*Developer to create tables in PDB as per design
1.  - Use SQL queries from `etl_robbinsr_06724-0001-Data.accdb` as well as data from from `06724-Codebook.pdf` to build csv files for each affiliated code table
1.  - Build control files for SQL*Loader for each csv file
1.  - Load code tables using SQL*Loader, control files, and csv files
1.  - Export `etl_robbinsr_06724-0001-Data.xlsx` to `etl_robbinsr_06724-0001-Data.csv` file
1.  - Build control files for SQL*Loader for `etl_robbinsr_06724-0001-Data.csv` load
1.  - Load data table using using SQL*Loader, control file, and `etl_robbinsr_06724-0001-Data.csv`
1.  - Compare each Oracle table's content with tables in `etl_robbinsr_06724-0001-Data.accdb`
1.  - Rework

**and Step 1 outputs passed through**

 - `06724-Codebook.pdf` in https://github.com/robbinsr/etl_example_step_03/tree/master/DS1_Household 
 - `06724-0001-Data.txt` in https://github.com/robbinsr/etl_example_step_03/tree/master/DS1_Household/DS0001

**and Step 2 outputs passed through**

- `robbins_etl_06724-0001-Data.xlsx`
- `robbins_etl_06724-0001-Data-Crosswalk-1994.xlsx`
- `robbins_etl_06724-0001-Data-Analysis-1994.accdb`
- `robbins_etl_06724-0001-Data-Analysis-1994.xlsx`
- Each of these files can be found at: https://github.com/robbinsr/ETL_3/tree/master/DS1_Household/DS0001


Please feel free to move to the ETL_4 repository at this point or at some future moment at your convenience.
