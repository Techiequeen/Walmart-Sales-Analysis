# Walmart-Sales-Analysis

### Project Overview
This project analyzes Walmart sales data to identify trends, insights, and recommendations for business improvement. The analysis explores sales performance, customer behavior, and product trends to inform data-driven decision-making.

### Data Sources
The analysis is based on a “sample Superstore.csv dataset” containing sales data from 2014 to 2017.
{https://www.kaggle.com/datasets/yasserh/walmart-dataset}

### Tool Used
- Excel: Data Cleaning
- SQL Server: Data Analysis
- Power BI: Data Visualization


### Data Cleaning/Pre-processing
Data cleaning and pre-processing were carried out at the initial stage to ensure data quality, and the following tasks were performed;
- Data loading and inspection
- Fixing the un-standardized date format
- Handling duplicates - Data cleaning and formatting

### Exploratory Data Analysis (EDA)
The EDA process involves analyzing the Superstore sales dataset to understand the distribution of variables, identify patterns and trends, detect potential issues, and answer key questions:
1. What is the overall sales trend?
2. Who are our top 10 customers?
3. List our top 10 performing sub-categories based on profit.
4. What are our sales by state and city?

### Data Analysis
Data analysis was done in SQL Server. 
~~~sql
--Q1. How do weekly sales vary by store and date?

SELECT Store, Date, SUM(Weekly_Sales) AS Weekly_Sales
FROM Walmart
GROUP BY Store, Date;
~~~
