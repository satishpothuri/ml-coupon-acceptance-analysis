# Will the Customer Accept the Coupon?

## Context
Imagine driving through town and a coupon is delivered to your cell phone for a coffee shop near where you are driving. Would you accept that coupon and take a short detour to the coffee shop? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely?

## Problem
Identify and highlight the differences between customers who did and did not accept the "coffee shop" coupons, using the statistical summaries, and visualization using Python.

## Data
The data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. 
There are 3 possible answers.

* Right away
* Later before the coupon expires
* No, I do not want the coupon

The first 2 answers are labeled as 'Y = 1' and last one is labeled as 'Y = 0' in the data set. 
There are five different types of coupons 
* Less expensive restaurants (under 20)
* Coffee houses
* Carry out & take away
* Bar
* More expensive restaurants (20 - $50).

### Dataset Investigation
Below are the findings from dataset investigation

* The 'car' column has only 108/12684 non-null values. The values are not so relevant to the current analysis, hence the car column will be dropped.
* The columns 'CoffeeHouse', 'Bar', 'CarryAway', 'RestaurantLessThan20', 'Restaurant20To50' have a few null values. Since these columns are highly relevant to the analysis, these null values will be replaced with a suitable/relevant values from the exising set of values.

### Data Cleaning and Preprocessing
The following updates are done to the data

* Drop the 'car' column
* Replace the null values in the columns 'CoffeeHouse', 'Bar', 'CarryAway', 'RestaurantLessThan20', 'Restaurant20To50' with the value 'never' as this seems to be more appropriate to the context.

## Findings Summary
**Visit Frequency & Gender**

* Coupon acceptance rates increased with more frequent visits.
* The gender did not have a notable influence on the trends.

**Time of the day & destination**

* Coupon acceptance rates were higher in the evening hours.
* Drivers heading to a non-urgent destinations are more likely to accept the coupons.

**Passanger Type**

* Drivers travelling alone or with partners are more likely to accept coupons
* Drivers travelling with kids are less likely to accept the coupons.

**Income Range**

* No strong correlation is observed between income ranges and the coupon acceptance rates.

**Coupon Expiration Time**

* Coupons with a 1-day expiration had significantly higher acceptance rates than those expiring in 2 hours.
* This trend was especially noticed during evening hours, while differences were minimal earlier in the day.

**Time of the Day & Age**

* Though coupon acceptance rate is slightly higher with drivers under the age of 30, but it is not significant to call out.

## Conclusion
Based on the above analysis, the key factors that influence the coupon acceptance rate are time of the day, passangers and coupon expiry. The drivers travelling alone or with partners tend to accept the coffee house coupons more than those travelling with friends/kids. The coupons with 1-day expiry are more popular in the evening hours while coupons with 2-hour expiry are more popular in the afternoon hours.

## Recommendation
2-hour expiry coupons are not popular during evening or late evening hours. So the recommendation is to prioritze 1-day expiry coupons during these hours. 
