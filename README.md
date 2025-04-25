# Walmart-Sales-Analysis

### Project Overview
This project aims to develop a sales forecasting model to accurately predict Walmart's sales and demand. The model considers factors like holidays, economic conditions, and promotional markdowns, using historical sales data from 45 stores. Holiday weeks are weighted five times higher than non-holiday weeks in the evaluation.

### Data Sources
The analysis is based on a “Walmart.csv dataset” containing hisstoric sales  data for 45 Walmart stores.

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
The EDA process involves analyzing the walmart dataset to understand the distribution of variables, identify patterns and trends, detect potential issues, and answer key questions:
1. How do weekly sales vary by store and date?
2. What is the impact of holidays(holiday flag) on weekly sales?
3. Sales by time of the year
4. Top-performing store/ underperforming stores
5. How do changes in CPI affect weekly sales?
6. How do changes in unemployment rates affect weekly sales?
7. Impact of fuel price on weekly sales.

### Data Analysis

Data analysis was done in SQL Server. 
~~~sql
--Q1. How do weekly sales vary by store and date?

SELECT Store, Date, SUM(Weekly_Sales) AS Weekly_Sales
FROM Walmart
GROUP BY Store, Date;
~~~
![image](https://github.com/user-attachments/assets/9873da0c-605e-4e6b-b1d4-7aef8dc96040)
~~~sql
--Q2. What is the impact of holidays(holiday flag) on weekly sales?

 SELECT Holiday_Flag, AVG(Weekly_Sales) AS AverageSales
 FROM Walmart
 GROUP BY Holiday_Flag;
~~~
![image](https://github.com/user-attachments/assets/0e46d4cf-6ed3-435f-8e76-0a45123714b0)
~~~sql
--Q3. Sales by time of the year

 SELECT Month, AVG(Weekly_Sales) AS AverageSales
 FROM Walmart
 GROUP BY Month
 ORDER BY AverageSales DESC;
~~~
~~~sql
--Q4. Top-performing store/ underperforming stores

SELECT Store, SUM(Weekly_Sales) AS TotalSales
FROM Walmart
GROUP BY Store
ORDER BY TotalSales DESC;

SELECT Store, SUM(Weekly_Sales) AS TotalSales
FROM Walmart
GROUP BY Store
ORDER BY TotalSales ASC;
~~~
![image](https://github.com/user-attachments/assets/add7ebec-7626-41b2-bbe8-50f68f0d3d45)
![image](https://github.com/user-attachments/assets/763c995b-8d51-4e7f-ae26-e8b938532f0c)
~~~sql
--Q5. How do changes in CPI affect weekly sales?

SELECT CPI, SUM(Weekly_Sales) AS WeeklySales
FROM Walmart
GROUP BY CPI
ORDER BY CPI DESC;
~~~
![image](https://github.com/user-attachments/assets/901f063f-b8f9-4a02-9789-acebc759c86f)
~~~sql
--Q6. How do changes in unemployment rates affect weekly sales?

SELECT Unemployment, SUM(Weekly_Sales) AS WeeklySales
FROM Walmart
GROUP BY Unemployment
ORDER BY Unemployment DESC;
~~~
![image](https://github.com/user-attachments/assets/5adcad08-96c9-48a6-9f6a-a582b1a6c7e3)
~~~sql
--Q7. Impact of fuel price on weekly sales.

SELECT Fuel_Price, SUM(Weekly_Sales) AS TotalSales
FROM Walmart
GROUP BY Fuel_Price
ORDER BY Fuel_Price DESC;
~~~
![image](https://github.com/user-attachments/assets/8f3a5120-c554-40f8-bbd3-d3ba4cdf913a)

### Results/Findings

1. Holiday Impact: Sales significantly increased during major holidays like Super Bowl, Labour Day, Thanksgiving, and Christmas.
2. Promotional Markdowns: Markdowns preceding holidays resulted in substantial sales boosts, with varying degrees of impact across different stores.
3. Store Variations: Sales patterns differed across the 45 stores, indicating regional and store-specific factors influencing sales.
These findings provide valuable insights for Walmart's sales forecasting and strategic planning.

### Recommendations

1. Increase Stock: Ensure sufficient stock levels for high-demand holidays and promotional markdown events.
2. Targeted Promotions: Focus promotional markdowns on high-impact holidays and stores with high sales potential.
3. Economic Factor Analysis: Monitor economic indicators (CPI, Unemployment Index) to adjust pricing and promotional strategies.
These recommendations can help Walmart improve sales forecasting, inventory management, and marketing strategies.

### Limitationa

1. Historical Data: The analysis relies on historical sales data, which may not fully capture future trends or unexpected events.
2. Store Variations: While the analysis accounts for store-specific variations, the findings may not be directly applicable to new or differently located stores.
Acknowledging these limitations can help Walmart refine its sales forecasting and strategic planning efforts.












