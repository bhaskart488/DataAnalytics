# Data Analytics using PowerBI

## Sales Insights Data Analysis Project

### Here, I used MySQL to import the data and later did the ETL in Power BI with 3 key dashboards as follows



![image](https://github.com/bhaskart488/DataAnalytics/assets/73813983/14f506ee-c87a-4da9-924d-3469d24a0457)


1. SQL database dump is in db_dump.sql file above. Download `db_dump.sql` file to your local computer and import it

### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

2. Show total number of customers

    `SELECT count(*) FROM customers;`

3. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

4. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

5. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

6. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

7. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
8. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

9. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`


Data Analysis Using Power BI
============================

- Formula to create norm_amount column

`= Table.AddColumn(#"Filtered Rows", "norm_amount", each if [currency] = "USD" or [currency] ="USD#(cr)" then [sales_amount]*75 else [sales_amount], type any)`

## Find the PowerBI dashboard at the following link: https://app.powerbi.com/groups/me/reports/4d5c8a94-1e4c-4970-ae11-394bd8c5be4c/ReportSection?experience=power-bi

### Screenshots attahched for reference:

![image](https://github.com/bhaskart488/DataAnalytics/assets/73813983/ad7c4f57-2aa5-4fbd-93bb-4452cfc098dc)


![image](https://github.com/bhaskart488/DataAnalytics/assets/73813983/97d60cdf-8dbf-44f9-bd09-c5dbd297519a)


![image](https://github.com/bhaskart488/DataAnalytics/assets/73813983/d6da2531-0047-44d4-bd7b-e5d8a11fb935)

