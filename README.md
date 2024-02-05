# Marketing-Campaign-Analysis


### Project Overview

An exploratory data analysis dive into the aftermath of a marketing campaign by a small skincare business called O'Honey and forecasts for future marketing decisions



![‎Marketing Campaign ‎002](https://github.com/fireball777/Marketing-Campaign-Analysis/assets/147949298/b570decf-0986-42e5-9fda-081716efd215)


### Problem Statement

O'Honey is a skincare brand that launched its innovative marketing campaign in early 2022, upon launching the campaign, they encountered a few challenges such as an unexpected upturn of customers and unpredictable sales and revenue during certain times. The data analysis was created to give meaning to customer behaviour and reinforce good marketing choices as well as discard unprofitable ones.

### Data Source

The data was collected from a repository on Kaggle: [Click here to view]( https://www.kaggle.com/datasets/shashankshukla123123/marketing-campaign/data)

### Tools

- Numbers - data cleaning 
- Tableau - creating the dashboard
- SQL Server - Data analysis

### Data Preparation

there were a few things done to make the data enough for the data analysis 

1. Data cleaning
2. making up for missing values
3. data loading and inspection

### Exploratory data analysis

- what demographic is most receptive to the marketing campaigns
- what are the factors that affect the acceptance rate of the marketing campaign
- why are households with teenagers more likely to patronise as compared to households with kids
- How does age factor in when dealing with customers who patronise more due to purchase deals

### Data analysis 

to include some interesting code I played around with in this project 

```sql
WITH ProductPreferences AS (
    SELECT
        ID,
        CASE
            WHEN MntWines > MntFruits AND MntWines > MntMeatProducts THEN 'Wine Lover'
            WHEN MntFruits > MntWines AND MntFruits > MntMeatProducts THEN 'Fruit Enthusiast'
            WHEN MntMeatProducts > MntWines AND MntMeatProducts > MntFruits THEN 'Meat Lover'
            ELSE 'Diverse Tastes'
        END AS PreferredProductCategory
    FROM
        customer_data
)

SELECT
    c.ID,
    c.Year_Birth,
    c.Education,
    c.Marital_Status,
    c.Income,
    pp.PreferredProductCategory
FROM
    customer_data c
JOIN
    ProductPreferences pp ON c.ID = pp.ID
ORDER BY
    c.Income DESC;
```

### Findings 

- Married couples are more reactive and responsive to marketing campaigns and people who live alone a least likely to be responsive
- Graduates are more positively responsive to marketing campaigns than their counterpart customers in basic school
- Households with teenagers have a higher acceptance rate than households with kids
- There are recurring peaks and troughs in the values over time or across categories.

### Recommendations

By virtue of the analysis performed, I recommend that;

1. O'honey focuses on more profitable customer categories
2. They should focus on servicing customer segments that don't respond well to the current marketing campaign
3. The business should focus on maintaining the positive results of the marketing campign over time

### 
