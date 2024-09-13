# Big City Crime

## Introduction

Ahead of the 2024 presidential election, crime has been a contentious topic. Democratic leaders point to recent FBI stats that show crime rates are lowering. Meanwhile Republicans question the validity of the stats due to significant changes in crime reporting systems around 2021, maintaining that many police departments are no longer reporting and thus crime rates are artifically lowered. 

To get a general feel of what direction crime rates are moving in, I look at 10 largest cities in the U.S. and compile/analyze data provided by their respective police departments. 


## Cities + Data Sources

Below is a list of the cities looked at and the their respective sources for crime stats. 

### New York City, NY

Data from 2000-2023 is readily available for download from the NYPD website, found [here](https://www.nyc.gov/site/nypd/stats/crime-statistics/historical.page).

### Los Angeles, CA

Very disappointingly, LAPD data was not available at the time of this analysis. Apparently there is an ongoing effort to overhaul their crime reporting systems, and for now the department has only posted very limited data (2022 onwards) to their website. For more information see the following [article](https://www.latimes.com/california/story/2024-06-07/lapd-crime-stats-disappear-records-overhaul).

### Chicago, IL

Crime stats for 2017-2023 were gathered from Chicago PD in the respective year's [annual reports](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/).

For some reason annual reports for 2011-2016 are not available. For this reason, 2016 crime stats was gathered from the [2017 annual report](https://home.chicagopolice.org/wp-content/uploads/2017-Annual-Report.pdf). Specifically, 2016 stats was gathered from page 17, "Index Crime Total" table. For 2012-2015, only the violent crime totals and index crime totals were gathered from page 17, "Violent Crime Vs Property Crime 2012-2017" table. 

### Houston, TX

Crime stats from 2019 onwards can be found [here](https://www.houstontx.gov/police/cs/Monthly_Crime_Data_by_Street_and_Police_Beat.htm) using the NIBRS reporting protocol. Prior to that Houston PD uses UCR. Data from 2012-2018 were gathered from [monthly historical files](https://www.houstontx.gov/police/cs/crime-stats-archives.htm). 

Data preparation was done to address the difference in reporting between NIBRS and UCR, particularly the elimination of the heirarchy rule. 

### Phoenix, AZ

Crime stats from 2010-2022 are extracted from the following [report](https://www.phoenix.gov/policesite/Documents/Crime%20Stats%20and%20Maps/UCR_2010-2022.pdf). 2023 data is found [here](https://www.phoenix.gov/policesite/Documents/Crime%20Stats%20and%20Maps/UCR%20Website%20December%202023.pdf). 

### Philadephia, PA

The link to the Philadelphia PD crime data archive (which supposedly contains crime data from 2006-present) was not working when I checked. So instead I extracted data from the Year End Reports found under "Recent Crime Stats Reports" section of the following [page](https://www.phillypolice.com/crimestats). 

NOTE: Year End Reports were not available for 2012, 2013, 2020. Instead the latest weekly report of each respective year was used, which contains cumulative YTD data. However, presumably due to reporting timelines, the cumulative YTD stats results in some cutoff. Thus 2012 stats report up to 12/30/2012, 2013 stats report up to 12/29/2013, and 2020 stats report up to 12/27/2020. 

### San Antonio, TX

Crime stats for 2011-2021 is reported in the UCR protocol and can be found [here](https://www.sa.gov/files/assets/main/v/1/sapd/sapd-ucrs-2011-2021.pdf). 

Afterwards San Antonio PD begins using NIBRS. Unfortunately they do not provide NIBRS row-level data specific to the city; there are only aggregate NIBRS statistics made readily available for 2022-2023. Thus an adjustment to the NIBRS data to make it more comparable to UCR (similar to how Houston, TX data is treated) is not possible. 

While the NIBRS row-level data can technically be [downloaded](https://www.icpsr.umich.edu/web/NACJD/series/128) (nationwide, by year), and then filtered to San Antonio, downloading the entire file takes up over 50GBs of space, and thus is out of scope of my analysis. 

If anyone knows how to download NIBRS data specific to a certain city, please lmk [@SebbyStats](https://x.com/sebbystats). 

In order make comparisons of crime rates between 2011-2021 (which uses UCR) and 2022-2023, homicides are used as a proxy. Because homicides are at the top of UCR heirarchy, an incident that involves a homicide should ALWAYS have that respective incident be marked as homicide. Homicide data for 2022-2023 was taken from the [Crime Statistics 2022 vs 2023: January - December](https://www.sa.gov/files/assets/main/v/1/sapd/nibrs/crime-statistics-2022vs2023-jan-dec.pdf) report.

### San Diego, CA

Crime stats for 2010-2022 was reported using the UCR system, found [here](https://www.sandiego.gov/sites/default/files/crime-actuals1950-2022.pdf). 

For 2023 San Diego PD switched over to NIBRS. Stats can be found [here](https://www.sandiego.gov/sites/default/files/2024-02/2023cumneighborhood.pdf)

Similar to San Antonio, in order to bridge the gap between 2010-2022 (UCR) and 2023 (NIBRS), homicide was used as a proxy. 

### Dallas, TX

Dallas PD only provides aggregate NIBRS data for 2023. Similar to San Antonio, row-level NIBRS data would presumably need to be downloaded and filtered from nationwide NIBRS. Due to storage limitations this cannot be done. 

### Jacksonville, FL

Jacksonville Sheriff's Office does not provide data aggregates. Row-level UCR and NIBRS data would presumably need to be downloaded and filtered from nationwide NIBRS. Due to storage limitations this cannot be done. 

### Austin, TX

ADP switch to NIBRS reporting beginning in January 2021. Row-level NIBRS Group A Offense Crime data can be downloaded [here](https://datahub.austintexas.gov/widgets/i7fg-wrk5?mobile_redirect=true). 

### Dallas,TX

DWPD transitioned to NIBRS in 2005. 



