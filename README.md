**Capital Bikeshare**

**Introduction**

A Capital Bikeshare is a service in which users can rent bikes available for shared use on a short-term basis for a price. The number of users on any given day can vary greatly for such systems. The ability to predict the number of hourly users can allow the business to manage them in a more efficient and cost-effective manner. 

**goal is to use analytics and optimize Machine Learning models to make informed prediction about daily bikes rebalancing to ensure bikes and docks availability in stations 21st & 1st St. NW and 21st St & Pennsylvania Ave NW.**

**Assumptio**
We assumed the total number of spots available at both the staHons are 50(25 – 25
each), maximum number of bikes available are 40, and rest 10 are docked. Some predictors (e.g.,
hour of the day) were provided as numbers, we assumed that these are factored levels as they are
limited in range (e.g., 0hrs to 23hrs) and will not take decimal places during prediction.

**Data Collection**
After downloading the Capital bikeshare source zip files, the files were extracted and
converted to CSV file. To process the data we used the Python library. We used the Scikit-learn library
to provide implementations of the statistical techniques. Data was collected from two staHons "21st &
I St NW" and “21st St & Pennsylvania Ave NW” from 1st January 2022 to 30th April 2022 for "21st & I St
NW". The missing values from the data was checked and removed. To prepare the data, started- atcolumn and end -at-column is converted to started- at date and end- of- date to collect the total pickup and drop-off counts.
We tested different models even if they didn’t seem like a good fit, so that we could compare the results
to other approaches. To test the success of each technique, we trained the model on 60% of the data,
and then tested for accuracy on the remaining 40% of data. Some of the techniques tested mentioned
include Linear Regression, LASSO, Ridge Regression and Elastic net. The Mean square error and best
alpha value of each model were noted, to select the best model for predicHon.
Excluded Predictors-Certain predictors were intenHonally excluded from the analysis. These include
the following: “instant” (removed as it is an idenHfier for each measurement), “dteday” (as this field is
specific to the day, month, and year which would differ in future predictions.

**Exploratory Data Analysis**

**A. Number of users each month (Jan, Feb, March, April)*


**Observation**
As depicted in figure 1 and 2 above we can predict that “21st & 1st St. NW” has more
users than ‘21st St & Pennsylvania Ave NW’ based on the range of pick-up and drop-off counts.
StaHon“21st & 1st St. NW” range is between 2 and 70, whereas for “21st St & Pennsylvania Ave NW”
is between 2 and 38. In the iniHal analysis it can be inferred that the “21st & 1st St. NW” is busier
staHon than “21st St & Pennsylvania Ave NW”. The lowest count (both pickup and drop off) at both the
staHons was in the month of January and maximum bike pick-up and drop-off was in the month of
April (The blue line represents pick-up and red line represent drop-off). This can be ahributed to the
weather condiHons, for example the reason for low demand of bikes may be due to snowy and cold
weather in January, however, the demand gradually picked up as the weather improved i.e. in spring. 

**Recommendation**

We need to strategize the bikes rebalancing based on above data to arrive at beher
decision in allocaHng the number of bikes to the staHons in the future. For instance, on around 18-
April-2022, the number of pick-ups at “21st & 1st St. NW” is around 20 whereas the drop-off count is
around 38. On the contrary on same day at “21st St & Pennsylvania Ave NW” the number of pick-ups
and drop-offs are 5 and 6 respecHvely. So out of the 40 bikes we would allocate around 10 bikes to
“21st St & Pennsylvania Ave NW” and rest 30 bikes to “21st & 1st St. NW”. However this is only iniHal
assessment we will take other factors like weather data and models to arrive at beher decision.

**B.	Bike  Utilization on hourly basis (Pick-up and Drop-oﬀ counts for the months Jan.,Feb.,March,April)**


**Observation**

As depicted in figure 1 and 2 above we can see the pick-up and drop-off count is higher
for ‘21st & 1st St. NW’ so we may infer that this staHon is busier than ‘21st St & Pennsylvania Ave
NW.’ Both staHons have significant bike drop-off count (represented by red line) during early hours of
the day i.e from 06:00hours to 12:00hours. The pick-up count gains momentum during the alernoon
from 13:00 hours to 17.00 hours at both staHons.

**Recommendation**

As seen from the graph we can recommend that in the alernoon during peak
hours the demand for pick-up is more at ‘21st & 1st St. NW’ so bikes from other staHon should be
allocated to ‘21st & 1st St. NW’ during 13.00 to 17.00 hours.

**Predictive Modeling**




