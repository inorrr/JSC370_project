# JSC370 Midterm Project

This repository is created for the midterm project of JSC370H1: Data Science II at the University of Toronto under the instruction of Jenny(Junni Du) and Professor Meredith Franklin.

## Introduction

For this project, my question of Interest is: **"How does crime rate relate to income in Canada?"**

In order to answer this question, data on both crime and socioeconomic status are needed. However, I found no existing data set that contains all desired information, therefore this needs to be achieved through merging more than one data sets. Aftering choosing carefully, the following two separate data sets are obtained: 

  1. **"Income of individuals by age group, sex and income source, Canada, provinces and selected census metropolitan areas"**. Released 2023-05-02. This data set is annually updated and maintained by Statistics Canada (Table 11-10-0239-01). Data is collected through the Survey of Labor and Income Dynamics, Survey of Consumer Finances, and Canadian Income Survey. 
  
  2. **"Incident-based crime statistics, by detailed violations, Canada, provinces, territories, Census Metropolitan Areas and Canadian Forces Military Police"**. Released 2023-07-27. This data set is also annually updated and maintained by Statistics Canada (Table 35-10-0177-01, formerly CANSIM 252-0051). Data is collected through the Uniform Crime Reporting Survey. 

Understanding the relationship between crime rates and income in Canada is crucial for policymakers, law enforcement agencies, and social welfare programs. Exploring this correlation can shed light on the socioeconomic factors driving criminal behavior and help formulate targeted interventions to alleviate poverty and reduce crime. Additionally, elucidating this connection can inform broader discussions on social inequality, justice, and community well-being in Canadian society.
  
Both data sets are downloaded directly from **Statistics Canada**, which is usually considered to be an reliable source. Because they share the same source, the data sets follows similar structure and all contains the two columns `GEO` and `REF_DATE` where the former one refers to the geographical region and the second one refers to the year of data. Thus, it's possible to combine the two data sets to obtain all information needed.

However, it is worth mentioning that both data sets are huge and contains **unrelated information**. Therefore, cleaning and wrangling are needed for more convenient analysis and more efficient computing & uploading, as the original data sets are oversize thus cannot be pushed to github repository.

Reference:

1. The census data set: https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=1110023901
2. The crime data set: https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3510017701

## Summary of Findings 

1. **Looking at Crime Data:**
  + Saskatchewan consistently exhibits a significantly higher total crime rate compared to other provinces throughout the period of 1998 to 2021.
  + Quebec and Ontario consistently demonstrate the lowest total crime rates.
  + Across all provinces, there is a discernible decreasing trend in total crime rates over the years.
  + Many provinces experiencing peak total crime rates in 2003-2004.
  + There is a decreasing trend in the rates of break and enter, robbery, and prostitution in all provinces.
  + British Columbia stands out with a significantly high rate of prostitution in 2004, doubling the number reported in Saskatchewan, which held the second-highest rate that year.
  + Across all provinces, there is a discernible decreasing trend in the average crime rate of all types, from year to year.
  
2. **Looking at Income Data:**
  + On the whole, the average total income for all provinces exhibits a steady upward trend.
  + Since 2003, Alberta has surpassed Ontario to become the province with the highest average total income.
  + There is a slight decrease in average total income across all provinces around 2019, likely attributed to the impact of the COVID-19 pandemic.
  + Employment income, investment income, and market income of provinces are all increasing. 
  + Employment and market income show a more steady growth pattern, while investment income fluctuates dramatically from year to year.
  
3. **Examining Crime and Income Together:**
  + Average total income and total crime rate are negatively correlated across all provinces.
  + Quebec exhibits the strongest correlation between average total income and total crime rate as the correlation is close to -1.
  + In the relationship between robbery crime rate and employment income, all provinces display a negative trend except for Newfoundland and Labrador. Manitoba demonstrates a weak relationship, as evidenced by the considerable dispersion of points around the line.
  + Property crime rate decreases with increasing market income in all provinces.
  + Employment income and prostitution crime rate have varying degrees of association across provinces, with many showing a weak relationship. Notably, Ontario exhibits a positive relationship between employment income and prostitution crime rate while it is negative for other provinces.
  
4. **Zoom on Province - Ontario:**
  + Major crimes in Ontario are property crime and weapon violations.
  + Strongest correlation is observed between self-employment income and production under the Cannabis Act. However, it’s important to note that this relationship may not be entirely reliable due to the limited data available.
  + The second strongest correlation, with a coefficient of 0.98, is observed between total income and incidents of possession of other Controlled Drugs and Substances Act drugs. As income levels increase, the number of incidents of possession of these drugs also tends to rise.
  
5. **Group by Income Level**
  + Created 4 levels for average total income using the quarantines, from negative infinity to the first quantile is “Low”, from first quantile to mean is “Med_Low”, from mean to 3rd quantile is “Med_High”, from 3rd quantile above is “High”.
  + Total crime rate does not exhibit a clear trend of decreasing with higher levels of total income, which contradicts previous observations when examining the relationship between total crime rate and average total income by province.  while a relationship exists, it may be influenced by other factors related to the demographics of each province. Consequently, when considering all observations collectively, the relationship becomes less apparent.

6. **Fitting Statistical Models**
  + The linear regression model analyzed the relationship between Crime Rate per 100,000 population and Average income (excluding zeros) across different provinces represented by the categorical variable GEO.
  + Findings suggest a negative correlation between average income and total crime rate, implying that higher average income tends to coincide with lower crime rates.
  + Provinces exhibit varying baseline rates, with British Columbia notably showing a significantly higher rate compared to the reference province.
  + Interaction terms between income and provinces reveal differing effects across regions, such as a more pronounced negative association between income and crime rate in British Columbia.
  + The model demonstrates a robust fit with an adjusted R-squared value of 0.9328, indicating significant influences of both income and province on the crime rate per 100,000 population, with nuanced variations across different regions.
