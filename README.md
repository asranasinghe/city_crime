# Big City Crime

## I. Introduction

Ahead of the 2024 presidential election, crime has been a contentious topic. Democratic leaders point to recent FBI stats that show crime rates are lowering. Meanwhile Republicans question the validity of the stats due to significant changes in crime reporting systems around 2021, maintaining that many police departments are no longer reporting and thus crime rates are artifically lowered. 

To get a general feel of what direction crime rates are moving in, I look at 10 largest cities in the U.S. and compile/analyze data provided by their respective police departments. 


## II. Cities + Raw Data Sources

Below is a list of the cities looked at and the their respective sources for crime stats. 

### 1. New York City, NY

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2000-2023       | UCR              | [Historical NYC Crime Data](https://www.nyc.gov/site/nypd/stats/crime-statistics/historical.page)

### 2. Los Angeles, CA

Very disappointingly, LAPD data was not available at the time of this analysis. Apparently there is an ongoing effort to overhaul their crime reporting systems, and for now the department has only posted very limited data (2022 onwards) to their website. For more information see the following [article](https://www.latimes.com/california/story/2024-06-07/lapd-crime-stats-disappear-records-overhaul).

### 3. Chicago, IL

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2017-2023       | UCR              | [Annual Reports](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/)
| 2016            | UCR              | [2017 Annual Report](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/), Page 17 "Index Crime Total" table (See note below)
| 2012-2015       | UCR, Violent/Property Crime Totals Only | [2017 Annual Report](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/), Page 17 "Violent Crime Vs Property Crime 2012-2017" table (See note below)

For some reason annual reports for 2012-2016 are not available. There are some reporting of 2012-2016 data within the 2017 Annual Report, which was used as a substitute. 

### 4. Houston, TX

| Year(s)         | Reporting Format |             Source             |
| :-----------    |   :-----------:  |          :-----------:          |
| 2019-2023       | NIBRS            | [Monthly Crime Data By Street and Police Beat](https://www.houstontx.gov/police/cs/Monthly_Crime_Data_by_Street_and_Police_Beat.htm)
| 2012-2018       | UCR              | [Monthly Historical Files](https://www.houstontx.gov/police/cs/crime-stats-archives.htm)

For information on how the differing reporting protocols were reconciled, see "Section III. Standardizing UCR-NIBRS Reporting Differences". 

### 5. Phoenix, AZ

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2023            | UCR              | [Monthly Count of Actual Offenses Known to Police Part 1 Crimes 2023 YTD](https://www.phoenix.gov/policesite/Documents/Crime%20Stats%20and%20Maps/UCR%20Website%20December%202023.pdf). 
| 2010-2022       | UCR              | [UCR SRS Annual Comparison](https://www.phoenix.gov/policesite/Documents/Crime%20Stats%20and%20Maps/UCR_2010-2022.pdf)

### 6. Philadephia, PA

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2012-2023       | UCR              | [Crime Map and Stats](https://www.phillypolice.com/crimestats), "Latest Crime Stats Report" Section

The link to the Philadelphia PD crime data archive (which supposedly contains crime data from 2006-present) was not working when I checked. So instead I extracted data from the Year End Reports.

NOTE: Year End Reports were not available for 2012, 2013, 2020. Instead the latest weekly report of each respective year was used, which contains cumulative YTD data. However, presumably due to reporting timelines, the cumulative YTD stats results in some cutoff. Thus 2012 stats report up to 12/30/2012, 2013 stats report up to 12/29/2013, and 2020 stats report up to 12/27/2020. 

### 7. San Antonio, TX

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2022-2023       | NIBRS            | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128); Filtered for San Antonio only
| 2011-2021       | UCR              | [sapd-ucrs-2011-2021.pdf](https://www.sa.gov/files/assets/main/v/1/sapd/sapd-ucrs-2011-2021.pdf). 

For information on how the differing reporting protocols were reconciled, see "Section III. Standardizing UCR-NIBRS Reporting Differences". 

For additional verification of NIBRS data, official department publications of homicide data for 2022-2023 was taken from the [Crime Statistics 2022 vs 2023: January - December](https://www.sa.gov/files/assets/main/v/1/sapd/nibrs/crime-statistics-2022vs2023-jan-dec.pdf) report.

### 8. San Diego, CA

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2023            | NIBRS            | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128); Filtered for San Antonio only
| 2010-2022       | UCR              | [San Diego Historical Crime Actuals 1950-2022](https://www.sandiego.gov/sites/default/files/crime-actuals1950-2022.pdf). 

For information on how the differing reporting protocols were reconciled, see "Section III. Standardizing UCR-NIBRS Reporting Differences". 

For additional verification of NIBRS data, official department publications of homicide data for 2023 was taken from the [Crime Against Persons January-December 2023](https://www.sandiego.gov/sites/default/files/2024-02/2023cumneighborhood.pdf) report. 

### 9. Dallas, TX

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2010-2023       | NIBRS            | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128); Filtered for Dallas only

### 10. Jacksonville, FL

Jacksonville Sheriff's Office does not provide data aggregates. Row-level UCR and NIBRS data would presumably need to be downloaded and filtered from nationwide NIBRS. Due to storage limitations this cannot be done. 

### 11. Austin, TX

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2021-2023       | NIBRS            | [Crime Reports]([https://datahub.austintexas.gov/widgets/i7fg-wrk5?mobile_redirect=true)](https://data.austintexas.gov/Public-Safety/Crime-Reports/fdj4-gpfu/data_preview))
| 2012-2020       | UCR              | [Crime Reports]([https://datahub.austintexas.gov/widgets/i7fg-wrk5?mobile_redirect=true)](https://data.austintexas.gov/Public-Safety/Crime-Reports/fdj4-gpfu/data_preview))

For information on how the differing reporting protocols were reconciled, see "Section III. Standardizing UCR-NIBRS Reporting Differences". 

### 12. Fort Worth,TX

| Year(s)         | Reporting Format |             Source              |
| :-----------    |   :-----------:  |          :-----------:          |
| 2010-2023       | NIBRS            | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128); Filtered for Dallas only

Dallas switched over to NIBRS in 2005. 

### 13. San Jose, CA

SJPD uses UCR to report [annual crime stats](https://www.sjpd.org/records/crime-stats-maps/crime-statistics-annual) for 2013-2022, under Table 2. SJPD again [reports](https://www.sjpd.org/records/crime-stats-maps/crime-statistics-monthly) UCR for Jan - Mar 2023, but switches to NIBRS for April 2024 onwards. 

### 14. Columbus, OH

Columbus crime stats uses UCR reporting and is available via the [OIBRS](https://dpsoibrspext.azurewebsites.net//). Data from 2010-2023 was pulled. 

### 15. Charlotte, NC

CMPD reports


## III. Standardizing UCR-NIBRS Reporting Differences

Another way in which UCR data can be compared to NIBRS is by using homicides as a proxy. Because homicides are at the top of UCR heirarchy, an incident that involves a homicide should ALWAYS have that respective incident be marked as homicide. 




