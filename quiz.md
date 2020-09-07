# Data Visualization Quiz
___
**Instructions**

This quiz is part of Algoritma Academy assessment process. Congratulations on completing the Data Visualization course! We will conduct an assessment quiz to test practical data visualization techniques you have learned on the course. The quiz is expected to be taken in the classroom, please contact our team of instructors if you missed the chance to take it in class.

We will analyze the dataset from **Kiva**, a non-profit organization that allows people to lend money using a P2P(peer-to-peer) model. Read the data from `loan_kiva.csv`. The data has 165,040 observations with 14 variables and consists of a historical detail loan request in 2015. 

For more detailed guide on each questions, you can look at the quiz.Rmd file on this repository.

Here is the list of the column description:

* `id`: Unique ID for loan (Loan ID)
* `funded_amount`: The amount disbursed by Kiva to the field agent(USD)
* `loan_amount`: The amount disbursed by the field agent to the borrower(USD)
* `activity`: More granular category
* `sector`: High level category
* `country`: Full country name of country in which loan was disbursed
* `region`: Full region name within the country
* `currency`: The currency in which the loan was disbursed
* `partner_id`: ID of partner organization
* `posted_time`: The time at which the loan is posted on Kiva by the field agent
* `funded_time`: The time at which the loan posted to Kiva gets funded by lenders completely
* `term_in_months`: The duration for which the loan was disbursed in months
* `lender_count`: The total number of lenders that contributed to this loan
* `repayment_interval`: Interval for the repayment of the loan

## Analyzing Data Distribution
By visualizing the distribution of variable `lender_count`, we can find out which numerical range has the highest frequency of data occurrence. Say we are interested in finding out the range of the highest frequency of `lender_count` for all loans in the United States. Therefore, the first thing we need to do is to filter the data so it only contain all data from United States. After the data is ready, you can start to make a plot to visualize the data. You may need to check the distribution of the `lender_count` using a histogram or density chart.

    First, you need to subset all loan posted from the United States:
```
# your code here
```

    Then, try to visualize the data distribution of the lender count. You can use either the base plot or the ggplot to visualize the data.
```
library(ggplot2)
# your code here
```
___

1. At what range does the `lender_count` in United States has the highest frequency?

   - [ ] 0-100
   - [ ] 100-200
   - [ ] 200-400
   

___
## Understanding Data Relationship

Say we are interested in analyzing the loans posted in the Manufacturing sector. We would like to see the relationship or pattern between the amount of loan (`loan_amount`) and number of lenders (`lender_count`). To do that, we can use a scatter plot. 

    First, You will need to subset the initial loan dataset to acquire all loans from the Manufacturing sector:
```
# your code here
```

    Then, we can create the scatterplot to see if there’s any existing pattern between the amount of loan and the number of lenders:
```
# your code here
```
___
   
2. How would you describe the relationship between the amount of loan and the number of lenders from all loans within the `Manufacturing` sector?

   - [ ] The higher the loan amount, the lower the lender count
   - [ ] The higher the loan amount, the higher the lender count
   - [ ] Loan amount and lender count don't have any meaningful relationship


3. Which statement is true based on the scatterplot you have created?

   - [ ] There are some loan that has big loan amount but little number of lender count
   - [ ] There are some loan that has big lender count but little loan amount
   - [ ] Most of the loan request has loan amount more than 7500
   
___
## Using Line Chart for Trend Analysis

Consider the following case: One of the data analysts in Kiva is tasked to analyze the time duration of a loan from the first time being posted to be fully funded in the Philippines according to each repayment interval types. The analyst then tried to visualize the monthly trend of the average funded time duration in hourly units each month.

Pay attention to the resulting plot of the analyst’s task in `guatemala.png`. 

![](guatemala.png)

Now your task is to recreate the previous plot for country of Philippines using your data.

In order to analyze the trend, first we need to subset the data for the country of **Philippines**. We will also need to convert any date data into the proper date and time format. You can use the `lubridate` package to manipulate the date and time data.

```
library(lubridate)
# your code here
```

Get the range of the posted time.
```
# your code here
```
___

4. What is the earliest and latest posted time of any loan in 2015?

   - [ ] 2015-01-01 01:27:00 UTC and 2015-12-31 05:54:25 UTC
   - [ ] 2015-01-01 03:34:51 UTC and 2015-12-31 05:54:25 UTC
   - [ ] 2015-01-01 01:27:00 UTC and 2015-12-31 14:44:55 UTC
   - [ ] 2015-01-01 00:42:30 UTC and 2015-12-31 05:54:25 UTC
   
___
Now we are set to calculate the duration from a loan is posted until it is fully funded. We need to create a new column that contains the difference between the funded time and the posted time. We will call it **funding duration**.  This column will have a data type of *time* and presented in unit of minutes. We need to convert them into *numeric* type and divide it by 60, so the time would be in hourly value. 

Create a new column `funding_duration` which is the result of the difference between `funded_time` and `posted_time`. 
```
# your code here
```

Since we want to visualize the monthly average funding duration, you need to create a new column called `month` which contains the month of the posted time before aggregating the data. 
```
# your code here
```

Finally, you can aggregate the data based on the `month` of the posted time and the `repayment interval` to get the average (mean) `funding duration`. 
```
# your code here
```
___

5. Which repayment interval has the longest fund duration and at what month did it happen?

   - [ ] monthly repayment interval in April
   - [ ] bullet repayment interval in January
   - [ ] monthly repayment interval in March

___   
The data has been properly prepared. Now it is your time to create the line plot to visualize the trend. Fill in the code below to produce the plot.

```
# ggplot(loan_agg, aes(x = ........, y = ........., color = ......, group = repayment_interval))+
#   geom_....()+
#   geom_point()+
#   labs(title = "Funding Duration Trend on Guatemala, 2015",
#        x = NULL, y = "Funding Duration",
#        color = "Repayment Interval")+
#    theme_minimal()+
#    theme(legend.position = "top")
```
___

6. Which statement is **TRUE** based on the line plot?

   - [ ] Monthly repayment interval has almost the same funding duration with Irregular repayment interval in August
   - [ ] Bullet repayment interval has longer funding duration than Irregular repayment interval in June
   - [ ] Monthly repayment interval never funded faster than Irregular repayment interval
