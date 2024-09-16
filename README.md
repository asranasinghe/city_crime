# Big City Crime

## I. Introduction

Ahead of the 2024 presidential election, crime has been a contentious topic. Democratic leaders point to recent FBI stats that show crime rates are lowering. Meanwhile Republicans question the validity of the stats due to significant changes in crime reporting systems around 2021, maintaining that many police departments are no longer reporting and thus crime rates are artifically lowered. 

To get a general feel of what direction crime rates are moving in, I look at 10 largest cities in the U.S. and compile/analyze data provided by their respective police departments. 


## II. Cities

The top 25 most populated cities in the U.S. according to [Wikipedia](https://en.wikipedia.org/wiki/List_of_United_States_cities_by_population) were looked at as part of this analysis. See below for the listing:

| City | 2023 Population Estimate |
| :-----------    |   :-----------:  |
| New York, NY | 8,258,035 |
| Los Angeles, CA | 3,820,914 |
| Chicago, IL | 2,664,452 |
| Houston, TX | 2,314,157 |
| Phoenix, AZ | 1,650,070 |
| Philadelphia, PA | 1,550,542 |
| San Antonio, TX | 1,495,295 |
| San Diego, CA | 1,388,320 |
| Dallas, TX | 1,302,868 |
| Jacksonville, FL | 985,843 |
| Austin, TX | 979,882 |
| Fort Worth, TX | 978,468 |
| San Jose, CA | 969,655 |
| Columbus, OH | 913,175 |
| Charlotte, NC | 911,311 |
| Indianapolis, IN | 879,293 |
| San Francisco, CA | 808,988 |
| Seattle, WA | 755,078 |
| Denver, CO | 716,577 |
| Oklahoma City, OK | 702,767 |
| Nashville, TN | 687,788 |
| Washington, DC | 678,972 |
| El Paso, TX | 678,958 |
| Las Vegas, NV | 660,929 |
| Boston, MA | 653,833 |


## III. Raw Data Sources

The crime stats for each city are compiled using either UCR SRS metrics or NIBRS, depending on the year. 

Crime statistics have historically been reported using SRS guidelines, which is a summary-based accounting of crime evsnts. In more recent years many police agencies have transitioned to using the [National Incident-Based Reporting System](https://bjs.ojp.gov/sites/g/files/xyckuh236/files/sarble/data_common/nibrs-user-manual-2021-1041521.pdf), which is incidence based. The difference between the two methods can cause significant difference in terms of total crime committed, see (see "Section V: Additional Info On UCR") for more information. 

Moreover the actual place wherein the stats were pulled from are either in official publications found on a given police department website, and/or from resources provided by the FBI such as the [Crime Data Explorer](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/explorer/crime/crime-trend) or the [National Archive of Criminal Justice Data (NACJD)](https://www.icpsr.umich.edu/web/pages/NACJD/index.html). 

This means that sometimes there can be two sets of data for the same reporting year. For example, a given police department may have its own annual crime report for 2023 that is based on NIBRS, AND also have reported their 2023 NIBRS data to the FBI, which can be found in the NACJD NIBRS data extracts. Theoretically these numbers should be the same, however if there are differences, the police department official publications will take precedence. 

Below is a list of respective data sources for each city. 

### 1. New York City, NY

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2000-2023       | UCR SRS              | PD/City Publication | [Historical NYC Crime Data](https://www.nyc.gov/site/nypd/stats/crime-statistics/historical.page)

### 2. Los Angeles, CA

Very disappointingly, LAPD data was not available at the time of this analysis. Apparently there is an ongoing effort to overhaul their crime reporting systems, and for now the department has only posted very limited data (2022 onwards) to their website. For more information see the following [article](https://www.latimes.com/california/story/2024-06-07/lapd-crime-stats-disappear-records-overhaul).

### 3. Chicago, IL

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2017-2023       | UCR SRS            | PD/City Publication | [Annual Reports](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/)
| 2016            | UCR SRS             | PD/City Publication | [2017 Annual Report](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/), Page 17 "Index Crime Total" table (See note below)
| 2012-2015       | UCR SRS, Violent/Property Crime Totals Only | PD/City Publication | [2017 Annual Report](https://home.chicagopolice.org/statistics-data/statistical-reports/annual-reports/), Page 17 "Violent Crime Vs Property Crime 2012-2017" table (See note below)

For some reason annual reports for 2012-2016 are not available. There are some reporting of 2012-2016 data within the 2017 Annual Report, which was used as a substitute. 

### 4. Houston, TX

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2019-2023       | NIBRS            | PD/City Publication | [Monthly Crime Data By Street and Police Beat](https://www.houstontx.gov/police/cs/Monthly_Crime_Data_by_Street_and_Police_Beat.htm)
| 2012-2018       | UCR SRS              | PD/City Publication | [Monthly Historical Files](https://www.houstontx.gov/police/cs/crime-stats-archives.htm)

For information on how the differing reporting protocols were reconciled, see "Section III. About UCR-NIBRS + Bridging the Gap". 

### 5. Phoenix, AZ

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2023            | UCR SRS              | PD/City Publication | [Monthly Count of Actual Offenses Known to Police Part 1 Crimes 2023 YTD](https://www.phoenix.gov/policesite/Documents/Crime%20Stats%20and%20Maps/UCR%20Website%20December%202023.pdf). 
| 2010-2022       | UCR SRS              | PD/City Publication | [UCR SRS Annual Comparison](https://www.phoenix.gov/policesite/Documents/Crime%20Stats%20and%20Maps/UCR_2010-2022.pdf)

### 6. Philadephia, PA

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2012-2023       | UCR SRS              | PD/City Publication | [Crime Map and Stats](https://www.phillypolice.com/crimestats), "Latest Crime Stats Report" Section

The link to the Philadelphia PD crime data archive (which supposedly contains crime data from 2006-present) was not working when I checked. So instead I extracted data from the Year End Reports.

NOTE: Year End Reports were not available for 2012, 2013, 2020. Instead the latest weekly report of each respective year was used, which contains cumulative YTD data. However, presumably due to reporting timelines, the cumulative YTD stats results in some cutoff. Thus 2012 stats report up to 12/30/2012, 2013 stats report up to 12/29/2013, and 2020 stats report up to 12/27/2020. 

### 7. San Antonio, TX

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2022-2023       | NIBRS            | NACJD NIBRS | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128)
| 2011-2021       | UCR SRS              | PD/City Publication | [sapd-ucrs-2011-2021.pdf](https://www.sa.gov/files/assets/main/v/1/sapd/sapd-ucrs-2011-2021.pdf). 

For information on how the differing reporting protocols were reconciled, see "Section IV. Methodology". 

For additional verification of NIBRS data, official department publications of homicide data for 2022-2023 was taken from the [Crime Statistics 2022 vs 2023: January - December](https://www.sa.gov/files/assets/main/v/1/sapd/nibrs/crime-statistics-2022vs2023-jan-dec.pdf) report.

### 8. San Diego, CA

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2023            | NIBRS            |  NACJD NIBRS | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128)
| 2010-2022       | UCR SRS              | PD/City Publication | [San Diego Historical Crime Actuals 1950-2022](https://www.sandiego.gov/sites/default/files/crime-actuals1950-2022.pdf). 

For information on how the differing reporting protocols were reconciled, see "Section IV. About UCR-NIBRS + Bridging the Gap". 

For additional verification of NIBRS data, official department publications of homicide data for 2023 was taken from the [Crime Against Persons January-December 2023](https://www.sandiego.gov/sites/default/files/2024-02/2023cumneighborhood.pdf) report. 

### 9. Dallas, TX

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2010-2023       | NIBRS            |  NACJD NIBRS |[Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128)

--NEED TO CHECK--

### 10. Jacksonville, FL

Jacksonville Sheriff's Office does not provide data aggregates. Row-level UCR and NIBRS data would presumably need to be downloaded and filtered from nationwide NIBRS. Due to storage limitations this cannot be done. 

### 11. Austin, TX

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2021-2023       | NIBRS            | PD/City Publication | [Crime Reports](https://datahub.austintexas.gov/widgets/i7fg-wrk5?mobile_redirect=true)
| 2012-2020       | UCR SRS              | PD/City Publication | [Crime Reports](https://datahub.austintexas.gov/widgets/i7fg-wrk5?mobile_redirect=true)

For information on how the differing reporting protocols were reconciled, see "Section IV. Methodology". 

### 12. Fort Worth,TX

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2010-2023       | NIBRS            | NACJD NIBRS | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128)

--NEED TO CHECK--

### 13. San Jose, CA

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| Apr2023-Dec2023       | NIBRS            | NACJD NIBRS | [Download NIBRS data](https://www.icpsr.umich.edu/web/NACJD/series/128)
| Jan2023-Mar2023 | UCR SRS            | PD/City Publication | [Crime Statistics-Monthly](https://www.sjpd.org/records/crime-stats-maps/crime-statistics-monthly), "UCR Part One Reported Jan-Mar 2023" table
| 2013-2022       | UCR SRS           | PD/City Publication | [Annual Crime Stats](https://www.sjpd.org/records/crime-stats-maps/crime-statistics-annual), Table 2

SJPD uses UCR to report  for 2013-2022, under Table 2. SJPD again  UCR for Jan - Mar 2023, but switches to NIBRS for April 2024 onwards. 

### 14. Columbus, OH

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2010-2023       | UCR SRS              | State Publication | [OIBRS](https://dpsoibrspext.azurewebsites.net//)

### 15. Charlotte, NC

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2023            | UCR SRS             | PD/City Publication | [2023 End-of-Year Public Safety Report](https://www.charlottenc.gov/cmpd/News-Information/Newsroom/2023-End-of-Year-Public-Safety-Report#:~:text=Violent%20crimes%3A%207%2C221%20offenses%20in,compared%20to%20286%20in%202022.)
| 2010-2022       | UCR SRS              | State Publication | [Summary Statistics Report Viewer]((https://www.ncsbi.gov/SSRV?report=/UCR/IndexOffenses)

### 16. Indianapolis, IN

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2010-2022       | UCR SRS             | FBI | [Crime Data Explorer](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/explorer/crime/crime-trend)

### 17. San Francisco, CA

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2018-2023       | UCR SRS              | PD/City Publication | [CompStat Reports](https://www.sanfranciscopolice.org/stay-safe/crime-data/crime-reports), December 2023 reports contain each year's YTD figures
| 2013-2017       | UCR SRS              | PD/City Publication | [CompStat Reports](https://www.sanfranciscopolice.org/sites/default/files/2018-11/SFPD-CompStat-YearEnd-2017.pdf), Page 2

NOTE: Data for 2013-2017 are all derived from the 2017 Year End report. Specifically data for 2013-2016 uses the 2017 report as opposed to their own respective year's reporting because my impression is this data is more up to date because it lives in a more recent report.  

### 18. Seattle, WA

--NEEDS WORK--

### 19. Denver, CO

| Year(s) Pulled  | Reporting Format | Source Location |             Source              |
| :-----------    |   :-----------:  |  :-----------:  |          :-----------:          |
| 2023            | NIBRS (See note below)  | PD/City Publication | [Denver Overall Crime Dashboard](https://www.denvergov.org/Government/Agencies-Departments-Offices/Agencies-Departments-Offices-Directory/Police-Department/Crime-Information)
| 2013-2022       | NIBRS (See note below)  | FBI | [Crime Data Explorer](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/explorer/crime/crime-trend)

NOTE: There are several sources that provide Denver crime statistics including the [Denver Overall Crime Dashboard](https://www.denvergov.org/Government/Agencies-Departments-Offices/Agencies-Departments-Offices-Directory/Police-Department/Crime-Information), the [FBI Crime Data Explorer](https://cde.ucr.cjis.gov/LATEST/webapp/#/pages/explorer/crime/crime-trend), and the [Denver Crime Statistics Archive](https://www.denvergov.org/content/denvergov/en/police-department/crime-information/crime-statistics-maps/crime-statistics-archives.html). 

The "/data/denver/denver_crime_comparison.xlsx" workbook makes a comparison of denver crime stats across these three different sources for 2019 (the only year where data was available from all three sources). The violent/property crime counts for each of these sources vary slightly. Because the FBI Crime Data Explorer contains the earliest data (up to 2022), this source was used along with the dashboard for 2023 data. Colorado law enforcement transitioned to NIBRS in 2013, so this was treated as the cutoff. 




## IV. Methodology

Another way in which UCR data can be compared to NIBRS is by using homicides as a proxy. Because homicides are at the top of UCR heirarchy, an incident that involves a homicide should ALWAYS have that respective incident be marked as homicide. 


## V. Additional Info On UCR

How crime is reported by police departments is very important. The below is a response from [ChatGBT](https://openai.com/chatgpt/) to the prompt "Write me a summary about police UCR and its history. Be sure to include a description of SRS, NIBRS, and how the differences can impact crime counts."

The Uniform Crime Reporting (UCR) Program is a nationwide effort coordinated by the FBI to collect and standardize crime statistics in the United States. It was launched in 1930 to create a reliable set of data that law enforcement agencies, policymakers, and researchers could use to understand and track crime trends across the country. The UCR program collects data on serious crimes, known as Part I offenses (e.g., murder, robbery, aggravated assault), and other less severe offenses, known as Part II offenses.

**UCR’s Traditional System: Summary Reporting System (SRS)**

The Summary Reporting System (SRS) is the original method of data collection under UCR. It relies on a summary of crime incidents, where only the most serious offense in a multi-offense event is reported. For example, if a robbery and assault occurred during the same incident, only the robbery would be counted. This simplified approach provided a basic overview of crime trends but had limitations, as it did not capture all the details of every incident, potentially leading to underreporting of crime complexities.

**National Incident-Based Reporting System (NIBRS)**

The National Incident-Based Reporting System (NIBRS) was introduced in the 1980s as an enhancement to the UCR system. Unlike SRS, NIBRS collects detailed data on every crime incident, including information on victims, offenders, and the nature of the crime. It allows for the reporting of multiple offenses in a single incident and captures a broader range of crime types. NIBRS also includes data on relationships between offenders and victims, location of the crime, weapon use, and other relevant factors. This provides a more comprehensive and nuanced view of crime.

**Differences Between SRS and NIBRS**

Incident Complexity: SRS reports only the most serious crime in an incident (hierarchy rule), while NIBRS includes all offenses.

Scope of Crimes: SRS covers 8 major crime categories (e.g., murder, robbery, burglary), while NIBRS captures data on 52 Group A offense categories, including more detailed and diverse crime types.

Data Depth: NIBRS provides more information about the nature of crimes, such as demographics, relationships, and specific details, whereas SRS offers a more general snapshot of crime occurrences.

Impact on Crime Counts: The shift from SRS to NIBRS can have a significant impact on crime counts. NIBRS often leads to higher crime counts because it reports all offenses in an incident rather than just the most severe one. For example, under SRS, an event involving both robbery and assault would count as one crime (robbery), but under NIBRS, both offenses would be reported. As a result, crime statistics may appear to rise after transitioning to NIBRS, even if actual crime rates remain unchanged, simply due to the more detailed reporting method.

Overall, NIBRS offers a more accurate and comprehensive understanding of crime patterns, but it requires more detailed reporting by law enforcement agencies. The FBI is encouraging agencies to switch to NIBRS, as it provides a clearer picture of crime in the U.S.




