# Analytical analysis of COVID-19’s impact on unemployment and travel in Australia
### Emily Dunkin,  Brandon Tiley,  Danielle Cahill,  Waqas Zahick,  Tom Peddlesden

This project aims to investigate the impact of COVID-19 and whether it had a significant influence on the Australian Economy. Further to this, we were motivated by an interest in whether COVID-19 will notably impact us in the future.

Technologies Used:
* Python
* Matplotlib
* Pandas
* Numpy
* Functools
* Scipy.stats
* Ipywidgets
* Sklearn

## Hypothesis

That COVID-19 would have a significant impact on unemployment rate and international travel, leading to greater unemployment and reduced international travel.

Null: That COVID-19 has no significant impact on unemployment rate and international travel, the trend before and after COVID-19 began  would be the same.

To investigate this hypothesis we considered four specific hypotheses:

1.  If Covid-19 impacted unemployment, it is expected that the states would be impacted differently, in line with their experiences with covid.

2. If Covid-19 impacted unemployment, it is expected that it would affect both genders equally, and this trend would be seen across multiple states.

3. If Covid-19 impacted both employment and the national arrivals of Australian citizens, it is expected that there will be a negative correlation between these variables during Covid-19. 

4. If Covid-19 impacted both employment and the national departures of Australian citizens, it is expected that there will be a negative correlation between these variables during Covid-19.


## Data Selection

Data was sourced from the Australian Bureau of Statistics in the form of excel spreadsheets. The data was current, detailed and enabled the exploration of our hypotheses. 

**Australian Unemployment Data**

URL: https://www.abs.gov.au/statistics/labour/employment-and-unemployment/labour-force-aus
tralia-detailed/nov-2020
Name: Table 02. Labour force status by State, Territory, Greater capital city, Rest of state (ASGS) and Sex
Date retrieved: 12/1/21

**Australian Arrivals and Departures Data**

URL:  https://www.abs.gov.au/statistics/industry/tourism-and-transport/overseas-travel-statistics-provisional/nov-2020
Name: Total Movement, Arrivals and Departures - Country of Citizenship
Date retrieved: 12/1/21


## Data Cleanup

#### Cleanup Process:
- Read in csvs, indexing the header, columns and footer locations and 
- Merge data sheets into one
- Reset indexes
- Split date column into two new columns of date and year
- Transposed the data
- Renamed columns 
- Checked data types and corrected when needed

#### Difficulties:
- Column names were very complicated and weren’t easily called
- Over 883 columns in merged final dataframe


## Data Exploration

Line graphs where used when exploring the unemployment data, and scatter plots were used when considering the relationship between travel and unemployment.

To examine the impact of COVID-19 we considered the timepoints before and after COVID-19 was declared a Public Health Emergency (PHE) by the World Health Organisation on January 30, 2020. [^1]

## Findings

### Does Unemployment rate differ across Australian states?

- States were not statistically different based on ANOVA test (pvalue=0.71855) 
- Most states had a general steep increase in unemployment after COVID-19 was deemed a Public Health Emergency (PHE)
- However Queensland, Victoria and WA were deemed to have the most interesting trend with a steep increase from 5% to almost 9%.

### Is there a difference in unemployment rate between genders across states?

#### Victoria

- Genders significantly different (p-val = 0.00032).
- Gender inversely correlated after PHE. After unemployemnt rate increases for both genders, the unemployment rate for males drops, while the unemployment rate for females continues to rise.

#### Queensland

- Genders significantly different (p-val = 0.00923).
- Males higher rate of unemployment, but similar trend between genders

#### Western Australia

- Non-significant difference between the genders (p > 0.05).
- Little difference in gender unemployment rate.  

#### In conclusion:

- Each state presented different findings.
- Western Australia showed little difference between the unemployment rate of each gender when dealing with COVID-19.
-  However, Victoria and Queensland showed some differences.
- Therefore, the null hypothsis was supported and the hypothesis rejected.


### Is there a negative correlation between the unemployment rate and national arrivals of Australian citizens? 

#### Before COVID-19

- The correlation coefficient value of 0.0601 and the r squared value of 0.0036, suggests that there is no real relationship between the unemployment rate and national arrivals in Australia.
- This means that the amount of national arrivals over time before coronavirus was not influenced by the unemployment rate. 

#### During COVID-19

- The correlation coefficient of 0.7155 displays that there is a strong positive correlation between arrivals and unemployment after covid had been declared a public health emergency.
- The r squared value of 0.512  indicates there was a moderate effect of arrivals on the national unemployment rate. 

- However, the data representing the time during covid was much more limited than the data representing the time before covid. It is also important to note that border closures and lockdowns may have influened the number of arrivals.


### Is there a negative correlation between Unemployment and the national departures of Australian citizens during Covid-19?

#### Before COVID-19

- The correlation coefficient of r = -0.45, implies there is a low to moderate, negative relationship between the variables. The r squared value indicates that within the regression model, 20% of the variation in National Departures can be explained by the variation in Unemployment rate. These values indicate that the data does not fit a regression model and is not related linearly.

#### During COVID-19

- The correlation coefficient of r = -0.81, indicates there is a strong, negative, linear relationship between the two variables. This means that as the unemployment rate increases, the number of departures decreases. The r squared value indicates that within the regression model, 66% of the variation in the National Departures can be explained by the variation in Unemployment rate. The values produced indicate that the variables are related in the context of covid.

- However, there was significalty less data representing the time during covid compared with the amount of data points for the time before covid, which may affect the outcome. Also, the linear regression model for during covid produced negative values for national departures. This is not suitable, nor logical considering the context of the data. This indicates that although the r and r squared values imply a linear relationship, the data may actually not support the linear regression model.


## Conclusion

The analysis showed that Covid-19 did influence the unemployment rate of Australians and their ability to travel. 

In particular: 

- **Unemployment Across states:** The changes in unemployment rate across the states was not found to be statistically significant.


- **Unemployment between genders across states:** The analysis did not support the hypothesis as the unemployment rates of the genders followed different trends in each state. There was not a common trend in the way COVID-19 affected unemployment.


- **Unemployment vs Arrivals:** In contrast to the  hypothesis, there is a positive correlation between the unemployment rate in Australia and the arrivals of Australians into the country during COVID-19. However, due to the border closures and other circumstances, the data used to come to this conclusion was limited. 


- **Unemployment vs Departures:** In line with the hypothesis, a negative correlation was seen between unemployment rate and the national departure of Australian citizens during COVID-19. However, the data leading to this result was limited.  


## Difficulties and Future Research

#### Challenges that arose:

- Were unable to consider state based travel, as data was only available in a National context.
    - Resulted in an update of the hypotheses

- Difficulties in predicting future trends as the data is limited and Covid-19 is ongoing.  

#### Possible Future Research for the effect of Covid-19:

-  Unemployment rate per industry
    -   Were some industries more affected than others?
    -  Can this explain the differences in unemployment between sexes?

- Tourism data
    - Considering the travel data for non Australian citizens
    - Does tourism have an impact on unemployment rate? 



[^1]: Public Health Emergency Reference : https://www.who.int/news/item/30-01-2020-statement-on-the-second-meeting-of-the-international-health-regulations-(2005)-emergency-committee-regarding-the-outbreak-of-novel-coronavirus-(2019-ncov)


