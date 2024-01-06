# Sales-Insights
## SQL 

The **SQL queries** which are performed in order to get insights from the database tables are - 

1. Query used to Show all customer records

> SELECT * FROM customers;

2. Query used to Show total number of customers

> SELECT count(*) FROM customers;

3. Query used to Show transactions for Chennai market (market code for chennai is Mark001

> SELECT * FROM sales.transactions where market_code='Mark001';

4. Query used to Show distrinct product codes that were sold in chennai

> SELECT distinct product_code FROM sales.transactions where market_code='Mark001';

5. Query used to Show transactions where currency is US dollars

> SELECT * from sales.transactions where currency="USD"

6. Query used to Show transactions in 2020 join by date table

> SELECT * FROM sales.transactions as t INNER JOIN sales.date as d ON t.order_date=d.date where year=2020;

7. Query used to Show total revenue in year 2020

> SELECT SUM(transactions.sales_amount) FROM sales.transactions as t INNER JOIN sales.date as d ON t.order_date=d.date where year=2020

8. Query used to Show total revenue in year 2020, January Month,

> SELECT SUM(transactions.sales_amount) FROM sales.transactions as t INNER JOIN sales.date as d ON t.order_date=d.date where year=2020 and month_name="January"

9. Query used to Show total revenue in year 2020 in Chennai

> SELECT sum(sales_amount) FROM sales.transactions as t inner join sales.date as d on t.order_date=d.date
where year=2020 and market_code="Mark001";

Few sample screenshots of the queries: 

<img width="600" height="500" alt="Screenshot 2024-01-06 at 2 49 05 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/3a233c4d-5d9e-478f-9998-573876ab552f">


## Tableau
