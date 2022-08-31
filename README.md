# Surfs Up
## Overview of the statistical analysis:
##### The purpose of the analysis is to use in order to determine if the surf and ice cream shop business is sustainable year-round. This was done by getting the temperatures for the the month of June and December as requested by the buisiness owner. By using sqlalchemy and sqlite to extract Hawaiian weather data by date, I filtered the temperature measurments from these two spaecific months. The describe function allowed me to gain a table of statistics from the list of temperatures from these months.
---
## Results:
### June Temperature Data:
Below, the first table is of all of the temperatures recorded within the month of June. The second table summarizes this long list into a condinced list of statistics.
![image](https://user-images.githubusercontent.com/105329532/187705680-77b1268d-6b86-482a-8755-641a2883a8a9.png)

### December Temperature Data:
Below, the first table is of all of the temperatures recorded within the month of December. The second table summarizes this long list into a condinced list of statistics.
![image](https://user-images.githubusercontent.com/105329532/187708520-5622f703-16f8-4669-a14a-763d324386c7.png)

---
## Summary:
### Key differences in June and December Weather Data:
* ##### There are more recorded counts of temperature data in the month of June, 1700 records than there is in the month of December, 1517 records. More data allows for a better average and range of statistics. 
* ##### The minimu temperature in December is 56 degrees and is lower than the temperature in June which is recorded to be around 64. This is a 10 degree difference and is the largest difference between all of the temperature data.
* ##### The December data only collect temperatures from 2010 - 2016 and the June month data was from 2010 - 2017. 
Overall, the results from the data are relatively within the same temperature ranges. Most of the statistics are only a few numbers away from eachother in diffrence. Most of the differences are from the the collection of the data than the temperature data itself. 
More queries can be made from this data by changing the month you are intersted in looking at or if you were interested in looking a precipitation or or a previous year's weather data. A lot of these lines of code can be slightly refractored.



# Design a query to retrieve the last 12 months of precipitation data and plot the results. 
#Starting from the last data point in the database. 
prev_year = dt.date(2017, 8, 23)
# Calculate the date one year from the last date in data set.
prev_year = dt.date(2017, 8, 23) - dt.timedelta(days=365)
# Perform a query to retrieve the data and precipitation scores
results = session.query(Measurement.date, Measurement.prcp).filter(Measurement.date >= prev_year).all()
#print(results)
