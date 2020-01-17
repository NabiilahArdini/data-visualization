# Data Visualization Quiz
___
**Instructions**

Hello, congratulations and thank you for taking part in the Data Visualization course. To test your abilities, let's do the quiz below.  
We will analyze data from **Kiva**, a non-profit organization that allows people to lend money via the Internet. Read the data from `loan_kiva.csv`. The data has 323,279 observations with 14 variables and consists of historical detail loan request throughout 2014 to 2015. 

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

For more detailed guide on each questions, you can look at the quiz.Rmd file.
___

1. At what range does the `lender_count` in `United States` has the highest frequency? You may need to check the distribution of the `lender_count`. To see the distribution of a single numerical data, we can use a histogram or density chart.

   - [ ] 0-100
   - [ ] 100-200
   - [ ] 200-400
   
   
2. What is the pattern between loan amount and lender count in `Manufacturing` Sector? Does loan with higher amount will attract more lender? To see the relationship or pattern between two variables, we can use scatterplot.

   - [ ] The higher the loan amount, the lower the lender count
   - [ ] The higher the loan amount, the higher the lender count
   - [ ] Loan amount and lender count don't have any meaningful relationship


3. Which statement is true based on the previous scatterplot?

   - [ ] There are some loan that has big loan amount but little number of lender count
   - [ ] There are some loan that has big lender count but little loan amount
   - [ ] Most of the loan request has loan amount more than 7500
   

4. Can you tell me which sector has the least amount of outlier of the `term_in_months` value? What plot can be used to detect an outlier? 

   - [ ] Wholesale
   - [ ] Entertainment
   - [ ] Services


5. Based on the previous plot, which sector has any low-valued outlier (outlier that is close to 0)? 

   - [ ] Education
   - [ ] Services
   - [ ] Health


6. Based on the plot, which sector has the biggest 3rd Quartile (Q3) of `term_in_months`? 

   - [ ] Agriculture
   - [ ] Housing 
   - [ ] Construction


7. People who requested a loan perhaps were in dire situation and need the money immediately. We want to observe the data for people in `Philippines` in year of `2015`. We want to analyze the `time_to_fund`, which is the time between the funding come (`funded_time`) with the time the loan posted (`posted_time`), in hourly unit.  We will analyze the monthly mean of `time_to_fund` for each `repayment_interval`. Plot the data with trend line or other chart that can capture periodic data. Which statement below is **WRONG** based on the trend line?
   
   - [ ] The time to fund reach the longest time in October for Irregular repayment interval
   - [ ] The time to fund reach the longest time in June for Bullet repayment interval
   - [ ] For Irregular repayment, the time to fund increase during January to April

8. Which repayment interval that perform the best (has shortest time to fund) during January to April?

   - [ ] Monthly
   - [ ] Bullet
   - [ ] Irregular
   
   
9. At what month the `Monthly` repayment interval has almost the same time to refund with `Irregular` repayment interval?

   - [ ] June
   - [ ] December
   - [ ] August
