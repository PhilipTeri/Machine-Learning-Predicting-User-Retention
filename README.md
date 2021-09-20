# Machine Learning - Predicting User Retention

## Part 3 - Predictive Modeling

### Purpose
Create features that will help predict user retention.

### EDA & Data Cleaning

The first thing I did was remove rows with missing data.

The following columms contained missing data:
<br>avg_rating_of_driver      8122-n/a
phone                      396-n/a
avg_rating_by_driver       201-n/a


![image](https://user-images.githubusercontent.com/41071502/134080487-cbecdf0b-0982-43b9-802f-1cb68c5f128d.png)

![image](https://user-images.githubusercontent.com/41071502/134080493-abdc5d01-ce6b-4c0a-a6d5-e1bdd28af540.png)

![image](https://user-images.githubusercontent.com/41071502/134080506-02a132c9-c8c7-43e7-bbc4-0d2b530c76b8.png)

![image](https://user-images.githubusercontent.com/41071502/134080522-498938dc-7373-43b7-ae92-fe3cc5e5d651.png)

### Feature Engineering

### Results
![image](https://user-images.githubusercontent.com/41071502/134080538-859184ec-6885-4de7-bcba-3ffe7a1e334e.png)

![image](https://user-images.githubusercontent.com/41071502/134080543-ba85b2ff-6528-4d95-a073-c9c5e04f86f9.png)

The accuracy of the random forest model is 0.8320868516284681

The accuracy of the logistic regression model is 0.8494571773220748


## Part 2 - Experiment and Metrics Design

#### Questions
What would you choose as the key measure of success of this experiment in encouraging driver partners to serve both cities, and why would you choose this metric?
Describe a practical experiment you would design to compare the effectiveness of the proposed change in relation to the key measure of success. Please provide details on: a. how you will implement the experiment b. what statistical test(s) you will conduct to verify the significance of the observation c. how you would interpret the results and provide recommendations to the city operations team along with any caveats.
#### Question 1 Answer:
The goal of this experiment is to encourage drivers from each city to work in both cities. The reason for this is because each city has a different time of day where people are most active. This means that there is a surge multiplier to the price during those times because there is high demand for drivers.

A key measure of success would be a decrease in the average surge applied to each users trip. This would mean drivers from one city during their slow period(non-surge) have gone into the other city and during their peak times. Surge prices are calculated based on demand for drivers, so the hypothesis is that this should drop.

#### Question 2 Answer:
I would use a two sample t-test to see if there is a significant difference in the mean of the current average surge multiplier and the average after removing tolls from the bridge. The Null hypothesis is that there will be no significant change in the aeverage of both.

The t-test would give a t-value that represents the probability of getting a value above or below the mean of the t-distribution. I can then calculate the p-value of the tails of the t-distibution to determine whether the null should be rejected or not. If I set my significance level to 0.05 and the p-value is less than the significance level I can reject the null hypothesis. This would suggest that there is a significant difference the the two averages in surge prices.

A caveat to study is that drivers may not want to drive to another city, or may not want other drivers coming to their city, especially since this may reduce profits.

## Part 1 - Exploratory Data Analysis

Aggregate these login counts based on 15­minute time intervals, and visualize and describe the resulting time series of login counts in ways that best characterize the underlying patterns of the demand. Please report/illustrate important features of the demand, such as daily cycles. If there are data quality issues, please report them.

#### All Logins
![image](https://user-images.githubusercontent.com/41071502/134080891-28a520e1-8294-4b40-a0c3-329b9a580d86.png)


#### Logins Between Jan 1, 1970 and Jan 31, 1970
There appears to be ajor spikes in logins throughout january that are evenly spaced out, this means they are likely occuring during the same time of the week.
![image](https://user-images.githubusercontent.com/41071502/134080950-00453dbf-ea7e-4ecf-bf8c-40179988ee6b.png)

#### Logins during a 2 week period
Jan 5, 1970 is a monday I plotted 2 weeks to see is there is a pattern and there appears to be an increase in logins during the weekends and then a dropoff in logins starting monday.
![image](https://user-images.githubusercontent.com/41071502/134081206-11b80872-acc7-4ea1-bd7e-47b1b9850771.png)


#### Logins during a weekday
On weekdays there is a spike in logins around noon
![image](https://user-images.githubusercontent.com/41071502/134081059-18ee19fc-ba54-42f9-8720-24f3f633dd39.png)
![image](https://user-images.githubusercontent.com/41071502/134081070-b1084958-46e2-4554-a274-7c75ddc04972.png)

#### Logins during a weekend
Weekends also follow a pattern, Jan 10 and Jan 11 are both saturday and have similar highs and lows throughout the day.
![image](https://user-images.githubusercontent.com/41071502/134081098-bac1d378-0e9d-4a97-a753-1bee9636e3c0.png)
![image](https://user-images.githubusercontent.com/41071502/134081142-72604c26-5a76-4a5d-b350-4c3eec6624b8.png)

