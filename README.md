
# Project : Sales Insights Data Analysis

![WhatsApp Image 2024-01-10 at 12 25 01](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/d1db5776-2fe5-4150-a41b-355773e1f005)

## Problem Statement

In this project performed India based AtliQ hardware company sales insights - A Data Analysis project.

AtliQ Hardware is a company which supplies computer hardware and peripherals to many of clients such as surge stores, Nomad stores etc. across India. AtliQ Hardware head office is situated in Delhi, India and they have many regional office through out the India.

Sales director for this company is facing a lot of challenges is this the market is growing dynamically and sales director is facing issue in terms of tracking the sales in this dynamical growth market and he is having issues with growth of this bussiness, as overall sales was declining. He has regional manager for North India, South and Central India. Whenever he wants to get insights of thses region he would call these people and on the phone regional manager give some insights to him that this was the sales last quarter and we are going to grow by this much in the next quarter.

The problem was that all thses thing happening is verbal and these was mo proof with facts that how his business is affected and which made him frustraed as he can see that overall sales is declining but when he can ask regional manager, he is not getting complete picture of this bussiness and when he and this AtliQ hardware is big business. so to see insights clearly. and he will get proper insights anbd can take data driven decision to increase sales of hos company. All he wants is a simple data visualization tool which he can access on daily basis. By using such tools and technology one can make data driven decisiions which helps to increase the sales of the company. So, In this projects we will help a company make its own sales related dashboard using power BI.

## Data Discovery :

#### Project Planning using AIMS Grid -

It is a project management tool which consists of four components-

1 ) Purpose - (What to do exactly)

2 ) Stackholder - (Who will be involved)

3 ) End result - (What do you want to achieve)

4 ) Success Criteria - (Cost optimization and time save)

## AIMS Grid -

![AIMS grid sales insights](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/3cb5f16d-5d3b-4fb4-899d-a8a072fc7748)

## Project Execution :



![231545034-7f6cc437-5683-44f1-92df-a671540ccae9](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/2418fd4d-5d24-4b9e-8666-7b31c076ee1f)

## Data Analysis using MySQL :

1 ) Completed the Data discovery and then used mySQL for data analysis.

2 ) SQL database dump is in db_dump_version_2.sql file above. Download db_dump.sql file to your local computer

#### Importing Data to MySQL workbench :

![2024-01-10](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/b7f71761-ab50-4678-a3f1-b35a0f9b6df1)

The import of data is done from an already existing MySQL file. This file has to be loaded into MySQL workbench for further data analysis.

Analysis of data by looking into different tables and reflecting garbage values

We can see that garbage value that the table market cantains certain values which are incorrect.

                         SELECT * FROM sales.market;

And then we can check that transacation table we can see that ceratin negative value in amount which is not possible. and we can see that certain transactions are in USD. Hence, filtration of that is also needed by converting into INR.

                         SELECT * FROM sales.transactions;

Analysis of different SQL statement on data base

1.To find of all customers records

                        SELECT * FROM sales.customers;

2.To find total number of customers

                        SELECT count(*) From sales.customers;

3.To find transactions for Chennai market (market code for chennai is Mark001

                        SELECT * FROM sales.transactions where market_code='Mark001';

4.To find distrinct product codes that were sold in chennai

                        SELECT distinct product_code FROM sales.transactions where market_code='Mark001';

5.To find transactions for Chennai market (market code for chennai is Mark002

                        SELECT * FROM sales.transactions where market_code='Mark002';

6.To find distrinct product codes that were sold in mumbai

                        SELECT distinct product_code FROM sales.transactions where market_code='Mark002';

7.To find transactions where currency is US dollars

                        SELECT * from sales.transactions where currency="USD";

8.To find transactions in 2020 join by date table

                        SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020;

8.To find transactions in 2019 join by date table

                        SELECT sales.transactions.*, sales.date.* FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2019;

9.To find total revenue in year 2020,

                         SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

10.To find total revenue in year 2019,

                        SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2019 and sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r";

11.To find total revenue in year 2020, January Month,

                        SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

12.To find total revenue in year 2020, February Month,

                        SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="February" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

13.To find total revenue in year 2019, January Month,

                        SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="January" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

14.To find total revenue in year 2019, February Month,

                        SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.date.month_name="February" and (sales.transactions.currency="INR\r" or sales.transactions.currency="USD\r");

15.To find total revenue in year 2020 in Chennai

                         SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark001";

16.To find total revenue in year 2020 in Mumbai

                        SELECT SUM(sales.transactions.sales_amount) FROM sales.transactions INNER JOIN sales.date ON sales.transactions.order_date=sales.date.date where sales.date.year=2020 and sales.transactions.market_code="Mark002";

Similarly, if we want different of any other particular city the market code of that city is used on the mysql workbench.

## Data Cleaning and ETL (Extract, Transform, Load):

In this process, we are work on data cleaning and ETL.

Step 1: Connect the MySQL database with the PowerBI desktop.

Step 2: Loading data into the Power BI deskstop. This step load all the tables and created in the data base. This load option will connect with the SQL and pull all the records into power BI environment.

![2024-01-10 (3)](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/60a9ced8-70e2-476f-ade8-33cd97d4c841)


In that DATA MODELING  view looking up for model which form the STAR schema thats modeling look like STAR.

![2024-01-10 (1)](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/259ee2a8-d22c-4982-b552-36876cbb3284)

Setp 3: Transform data with the help of Power Query

Perform filtration in market’s table: In the tables perform when we click on the transform data option, we are directed to Power query editor. Power query editor is where we perform out ETL.and then we can perform data transformation i.e. Data Cleaning, Data Wrangling, Data Munging. we need to filter the rows where the values are null and filtering the data and deselecting the blank option.

Perform filtration in Transaction’s table: In the table perform when we check the query in the MySQL to filter some negative values and also 0 values that appears in the table, the desired output is received.and we will perform the similar filtration in PowerBI. we have deselecting the values, don’t want in the table. The result after filtration. the zero values represent some garbage values which is not possible so we need to clean that data.

Convert USD into INR in the transaction’s table: the AtliQ Hardware only works in India so the USD values are not possible. we need to convert those USD values into INR by using some formulas. Add new column - Conditional column - normalized currency where sales amount will be in INR

In power query editore finding the total values having USD as currency.

![2024-01-10 (2)](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/09de48ae-9eb6-4d60-96c4-52483ae5c4cb)


norm_sales_amount

                 norm_sales_amount`=Table.AddColumn(#"Filtered Rows", "norm_sales_amount",each if [currency] = "USD" then [sales_amount]*75 else [sales_amount]`

using this correct formula of the conversion,and converted the USD currency into INR.

In MySQL Workbench find that there are duplicates of USD and INR:

                        `SELECT count(*) from sales.transactions where sales.transactions.currency="INR\r";` 
                        150000 - can't removed as it is large amount

                        `SELECT count(*) from sales.transactions where sales.transactions.currency="INR";` 
                        279 - we can remove it as it is small record and can be considered as bad data

                        `SELECT count(*) from sales.transactions where sales.transactions.currency="USD\r";` 

                        `SELECT count(*) from sales.transactions where sales.transactions.currency="USD";`

                        `SELECT * from sales.transactions where sales.transactions.currency='USD\r' or sales.transactions.currency='USD';`

## Data Modeling:

![2024-01-10 (1)](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/259ee2a8-d22c-4982-b552-36876cbb3284)

## Data Analysis (DAX):

#### Key Measures:

                        Profit Margin % = DIVIDE([Total Profit Margin],[Revenue],0)

                        Profit Margin Contribution % = DIVIDE([Total Profit Margin],CALCULATE([Total Profit Margin],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))

                        Revenue = SUM('sales transactions'[sales_amount])

                        Revenue Contribution % = DIVIDE([Revenue],CALCULATE([Revenue],ALL('sales products'),ALL('sales customers'),ALL('sales markets')))
                        Revenue LY = CALCULATE([Revenue],SAMEPERIODLASTYEAR('sales date'[date]))

                        sales quntity = SUM('sales transactions'[sales_qty])

                        Total Profit Margin = SUM('Sales transactions'[Profit_Margin])

## Insights

- In this dashboard, we can see company has generated total revenue in 4 years ₹ 984.8M , total profit margin ₹24.7M , Profit margin% 2.5% , Sales Qty ₹2.4M. in 2020 company has generated total revenue of ₹ 142.2M by selling a total of 350.2K and earned a profit of ₹ 2.1M.

- In 4 years Delhi NCR is our largest market in terms of revenue with ₹ 520M and total contribution of 52.8% with total revenue but if you look at the profit margin Delhi NCR is generating only 2.3% profit margin.

- If we check the profit margin then here In 2020 Bhubaneshwar comes into the picture which is generating the highest profit margin of 10.5%. Similarly, if we can check the Profit Contribution % by Market then here Mumbai is the largest player with 24% of total contribution in total profit.

- In 4 years Bengaluru generating the lowest profit margin of -20.8%.if we can check the Profit Contribution % by Market.

- In our top 5 customers, the Electricalsara Stores is our biggest customer who has generated total ₹ 413 M revenue generated in 4 years.

- Highest revenue generated from North zone that is 675.5M.

- Revenue Trend is showing that in June 2020 revenue has been decreased drastically compared to the revenue last year and the profit margin was the least in April 2020.

## Build Dashboard Or a Report:

![Sales Insights (Atlq Hardware) By Virat Tiwari_pages-to-jpg-0001](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/00a96f6f-133f-4780-a529-acd936a51728)


![Sales Insights (Atlq Hardware) By Virat Tiwari_pages-to-jpg-0003](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/af20027f-dfb4-4e0a-b5b5-578e57164fcc)


![Sales Insights (Atlq Hardware) By Virat Tiwari_pages-to-jpg-0002](https://github.com/Virat-Tiwari/Sales-Insights-Analysis-/assets/66154941/7fb59c46-1c47-4e5b-a1e8-e89a702f3029)

## Tools Used :

1 ) MySQL

2 ) Microsoft Power BI

3 ) Power Query Editor

3 ) DAX Language

## THANK YOU SO MUCH !!
