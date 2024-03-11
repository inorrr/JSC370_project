# JSC370 Midterm Project

This repository is created for the midterm project of JSC370H1: Data Science II at the University of Toronto under the instruction of Jenny(Junni Du) and Professor Meredith Franklin.

Question of interest is: **“How does crime rate relate to poverty in Canada?”**

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
