# Surfs Up! An Analysis of Weather Data in Oahu
## Analysis Overview
For this analysis, we are pulling data from a SQLite database in order to analyze the weather on Oahu. This data will assist a potential investor in determining whether or not the weather is conducive to opening up a year-round 'Ice Cream and Surf Shop'.
## Analysis Results
The potential investor asked us to analyze temperature data in Oahu for the months of June and December over the course of 7 years.
### June Results
As seen in the figures below, the average temperature in June is about 75° F, with a low reading of 64° F, and a high reading of 85° F, and the highest frequency of temperatures falling in the 75°-78° F range.

![June Summary](https://github.com/Ian-T-Dixon/Surfs_Up/blob/main/Resources/june_summary.PNG)
![June Histogram](https://github.com/Ian-T-Dixon/Surfs_Up/blob/main/Resources/june_temps.PNG)

### December Results
As seen in the figures below, the average temperature in December is about 71° F, with a low reading of 56° F, and a high reading of 83° F, and the highest frequency of temperatures falling in the 68°-73° F range.

![December Summary](https://github.com/Ian-T-Dixon/Surfs_Up/blob/main/Resources/dec_summary.PNG)
![December Histogram](https://github.com/Ian-T-Dixon/Surfs_Up/blob/main/Resources/dec_temps.PNG)

## Analysis Summary
Analysis of the temperatures during the months of June and December indicate that temperatures in Oahu are relatively stable year round with the temperature generally staying in the low to mid 70° F. This indicates that from a temperature perspective, the shop would be able to function all year round (*assuming that people in Oahu have any interest in eating ice cream in 70° weather!* Further analysis on this may be required). However, this analysis does not take into account precipitation for the months of June and December, which could also tell us whether or not there is any difference between the amount of rain in the Summer vs Winter.

This information could easily be found by slightly modifying our query to the below and performing the same analysis on the results.
`june_results = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 6).all()`

`dec_results = session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date) == 12).all()`
