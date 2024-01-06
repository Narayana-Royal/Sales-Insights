# Sales-Insights
## Files : db_dump.sql - database of tables
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

#### Few sample screenshots of the queries: 

<img width="800" height="500" alt="Screenshot 2024-01-06 at 2 49 05 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/3a233c4d-5d9e-478f-9998-573876ab552f">


## Tableau
#### Performing ETL Operations
E - Extracting the database which is in localhost to tableau

T - Transforming the database in tableau (i.e basically cleaning the incorrect data among all the tables in tableau itself)

L - Loading the Transformed data into Tableau for dashboarding.

> Star Schema: It is nothing but connecting the main table to the peripherals
#### Screenshot of this database schema after extracting it from mysql server:

#### Step1: Extracting

<img width="800" height="500" alt="Screenshot 2024-01-06 at 3 59 04 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/398bea4b-dfcc-41d3-9fc2-b8e3a3f7198b">

#### Step2: Transforming
