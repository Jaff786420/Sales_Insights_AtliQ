# Sales_Insights_AtliQ

AtliQ Hardware is a Computer Hardware and Peripheral Manufacture company which supplies those items to their Clients and their office is spread across different regoins of India.

## Problem Statement

It is seen that from past few years, the Sales of the company has been declining and the Sales Director is wants to know the reason and solution for the Sales trend.

To find this out, Analysis is performed where Datasets are provided (in Excel sheet) and from the Analysis, reasons and solutions are provided.

Analysis is perfomed using
1. SQL - where basic queries are provided
2. Tableau - where the data is visualized and the solution is generated.

Database Dump is present in the above file. DB_TABLES_DUMP.sql file needs to be downloaded and needs to be exported into the Database.


## Data Analysis using SQL

1. Show all customer records
A. SELECT * FROM customers;


2. Show total number of customers
A. SELECT count(*) FROM customers;


3. Show transactions for Chennai market (market code for chennai is Mark001)
A. select count(*) from markets m, transactions t where m.markets_code = t.market_code and m.markets_name = 'Chennai';


4. Show distrinct product codes that were sold in chennai
A. select distinct product_code from markets m, transactions t where m.markets_code = t.market_code and m.markets_name = 'Chennai';


5. Show transactions where currency is US dollars
A. select * from transactions where currency = 'USD';


6. Show transactions in 2020 join by date table
A. select t.* from date d, transactions t where d.date = t.order_date and d.year = '2020';


7. Show total revenue in year 2020,
A. select sum(t.sales_amount) from transactions t inner join date d on d.date = t.order_date where d.year = 2020 and t.currency = "INR" or t.currency = "USD";


8. Show total revenue in year 2020, January Month.
A. select sum(t.sales_amount) from transactions t inner join date d on d.date = t.order_date where d.year = 2020 and d.month_name = 'January' and t.currency = "INR" or t.currency = "USD";


9. Show total revenue in year 2020 in Chennai
A. SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";


## Data Analysis using Tableau

Tableau Link: https://public.tableau.com/app/profile/mohamed.jaffar/viz/SalesInsightsofAtliQCompany/Dashboard-RevenueAnalysis
