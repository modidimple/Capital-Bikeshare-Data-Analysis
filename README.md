**Capital Bikeshare Data Analysis**

**Introduction**

Capital Bikeshare is a bike rental service that allows users to rent bikes for short-term use. Predicting the number of hourly users can help optimize bike rebalancing and ensure bike and dock availability at specific stations. This project aims to use analytics and machine learning models to make informed predictions about daily bike rebalancing at stations 21st & 1st St. NW and 21st St & Pennsylvania Ave NW.

**Assumptions**
- Total number of spots at both stations: 50 (25 at each station)
- Maximum number of available bikes: 40
- Rest of the spots (10) are docked
- Predictors, such as hour of the day, are treated as factored levels within a limited range (0hrs to 23hrs).

**Data Collection**

The Capital Bikeshare source files were downloaded and extracted, then converted to CSV format. Python and the Scikit-learn library were used for data processing and statistical techniques implementation. Data was collected from two stations, "21st & I St NW" and "21st St & Pennsylvania Ave NW," for the period from January 1, 2022, to April 30, 2022. Missing values were checked and removed. Start and end timestamps were converted to date format to calculate the total pickup and drop-off counts.

Various models, including Linear Regression, Lasso, Ridge Regression, and Elastic Net, were tested to determine the best model for prediction. The models were trained on 60% of the data and evaluated for accuracy on the remaining 40%.

**Exploratory Data Analysis**

**A. Number of Users Each Month (Jan, Feb, March, April)**

- 21st & 1st St. NW 

![Image Description](https://github.com/modidimple/gw-rml-assignment/blob/main/1.png)


- 21st St & Pennsylvania Ave NW

![Image Description](https://github.com/modidimple/gw-rml-assignment/blob/main/21st%20St%20%26%20Pennsylvania%20Ave%20NW.png)

**Observation**
Based on the pickup and drop-off counts, it can be inferred that "21st & 1st St. NW" has more users compared to "21st St & Pennsylvania Ave NW." The pickup and drop-off ranges for "21st & 1st St. NW" are between 2 and 70, while for "21st St & Pennsylvania Ave NW" it is between 2 and 38. The demand for bikes gradually increased from January to April, which can be attributed to improved weather conditions.

**Recommendation**

Considering the higher demand at "21st & 1st St. NW," allocating more bikes to this station would be beneficial. For instance, on April 18, 2022, there were around 20 pickups and 38 drop-offs at "21st & 1st St. NW," compared to 5 pickups and 6 drop-offs at "21st St & Pennsylvania Ave NW." Allocating approximately 10 bikes to "21st St & Pennsylvania Ave NW" and the remaining 30 bikes to "21st & 1st St. NW" would be an initial allocation strategy. However, additional factors such as weather data and advanced models should be considered for a more informed decision.

**B. Bike Utilization on Hourly Basis (Pick-up and Drop-off Counts for Jan., Feb., March, April)**

![Image Description](https://github.com/modidimple/gw-rml-assignment/blob/main/21st%20%26%201st%20St.%20NW%20bike_Utiliztion.png)


**Observation**

Both stations experience significant drop-offs during early hours (06:00 to 12:00), while the pickup count gains momentum during the afternoon (13:00 to 17:00) at both stations. "21st & 1st St. NW" shows higher pick-up and drop-off counts, indicating it is busier than "21st St & Pennsylvania Ave NW."

**Recommendation**

During peak hours in the afternoon (13:00 to 17:00), when the demand for pickups is higher at "21st & 1st St. NW," bikes should be reallocated from other stations to meet the demand.

**Predictive Modeling**

Multiple modeling techniques, including Linear Regression, Lasso, Ridge Regression, and Elastic Net, were employed to predict total pick-up and drop-off counts at the two stations. A 60:40 train-test split was used, and Mean Square Error (MSE) was computed for each model. Cross-validation was utilized to identify the best alpha value, balancing penalty and model fit.

**Performance Evaluation**

The following table shows the MSE values for pick-up and drop-off predictions:

| Model                | MSE (pick-up) | MSE (drop-off) |
|----------------------|---------------|----------------|
| Linear Model         | 213.57        | 233.96         |
| KNN                  | 227           | 210.54         |
| LASSO                | 143.92        | 133.14         |
| Ridge Regression     | 147.98        | 128.59         |
| Elastic Net          | 144.57        | 129.26         |

**Best Alpha values**

| Model                | MSE (pick-up) | MSE (drop-off) |
|----------------------|---------------|----------------|
| LASSO (Best alpha)   | 1.51           | 1.14           |
| Ridge Regression (Best alpha) | 65.79 | 91.11 |
| Elastic Net (Best alpha) | 0.84 | 0.80 |

Based on the MSE values, the Lasso model was selected to predict the total pick-up and drop-off counts. In April, the pick-up count ranged from 66 to 19, while the drop-off count ranged from 60 to 32 at the two stations. These predictions align with the exploratory data analysis, highlighting the higher demand at "21st & 1st St. NW" compared to "21st St. & Pennsylvania Ave." Consequently, it is recommended to allocate more bikes to "21st & 1st St. NW" to meet the demand, while ensuring an adequate number of docks at "21st St. & Pennsylvania Ave." Regular bike rebalancing should be performed to maintain optimal service levels at both stations.

**Recommendation**
Based on the above result we can allocate 20 more bikes at ‘21st & 1st St. NW’
as the pick-up demand is high in this staHon and on a safer side, we should account for any
uncertainHes in bike demand. At 21st&Pennsylvania Ave, we should allocate around 5-8 more bikes as
the pick-up demand is relaHvely less. The drop-off is more at this staHon so focus should be to make
the docks available for the riders. So, with regular bike rebalancing we will maintain opHmum service
level at these staHons and meet the demand of bikes. This commensurate with the assumpHon we
made at the starHng of the project (the total number of spots available at both the staHons are 50(25
– 25 each), maximum number of bikes available are 40, and rest 10 are docked)

**Limitation**

- The data under study was small i.e only four months. So, the predicHon may not be
- The analysis was based on a small dataset, covering only four months. Consequently, the predictions may not be highly accurate.
- The analysis focused primarily on weather patterns, and other uncertainties were not considered.
- The suggested bike rebalancing is a basic approach, and additional factors such as demand variations throughout the day and sudden weather changes should be taken into account for more - precise and dynamic rebalancing strategies.






