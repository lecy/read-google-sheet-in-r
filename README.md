# read-google-sheet-in-r

Read a Google Spreadsheet directly into R 

## CSV OPTION 

```r
# FORMAT OF URL OF GOOGLE SHEET
# https://docs.google.com/spreadsheets/d/<KEY>/edit#gid=<GID>

# EXPORT TO CSV: 
# https://docs.google.com/spreadsheets/d/<KEY>/export?gid=<GID>&format=csv
# where <KEY> and <GID> can be obtained from your navigation's URL

# EXAMPLE: ASU SALARY DATABASE
# 'https://docs.google.com/spreadsheets/d/1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E/edit#gid=1335284952'
# <KEY>: 1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E
# <GID>: 1335284952

# NEED A DIFFERENT <gid> FOR EACH TAB IN THE SHEET 
# 2019 sheet:  https://docs.google.com/spreadsheets/d/1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E/edit#gid=1948400967
# 2018 sheet:  https://docs.google.com/spreadsheets/d/1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E/edit#gid=169937930 
# etc

# READ AS CSV
URL <- 'https://docs.google.com/spreadsheets/d/1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E/export?gid=1335284952&format=csv'
d <- read.csv( URL )
head( d )

```


| Calendar.Year|Full.Name                           |Job.Description            |Department.Description         |Salary      | FTE|
|-------------:|:-----------------------------------|:--------------------------|:------------------------------|:-----------|---:|
|          2020|xxx, xxx                            |Research/Lab Assistant     |Sch Biological & Hlth Sys Engr |$35,090.00  | 100|
|          2020|xxx, xxx                            |Lecturer                   |Sch Biological & Hlth Sys Engr |$71,400.00  | 100|
|          2020|xxx, xxx                            |Student Support Specialist |Admission Services             |$36,000.00  | 100|
|          2020|xxx, xxx                            |Project Manager            |CASGE  Tempe                   |$64,000.00  | 100|
|          2020|xxx, xxx                            |Management Intern          |Health & Clinical Partnerships |$20,800.00  |  50|
|          2020|xxx, xxx                            |Assoc Professor            |Sch Biological & Hlth Sys Engr |$107,195.00 | 100|


## Excel Option 

```r
# DOWNLOAD ALL TABS IN EXCEL WORKBOOK: 
# https://docs.google.com/spreadsheets/d/1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E/export?format=xlsx

URL <- 'https://docs.google.com/spreadsheets/d/1RoiO9bfpbXowprWdZrgtYXG9_WuK3NFemwlvDGdym7E/export?format=xlsx'
download.file( URL, "asu-salaries.xlsx" )
# then read into R using read excel package 
```
