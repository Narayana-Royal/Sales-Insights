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
### Performing **ETL** Operations
E - Extracting the database which is in localhost to tableau

T - Transforming the database in tableau (i.e basically cleaning the incorrect data among all the tables in tableau itself)

L - Loading the Transformed data into Tableau for dashboarding.

> Star Schema: It is nothing but connecting the main table to the peripherals
### Steps along with screenshots:

#### Step1: Extracting

<img width="800" height="500" alt="Screenshot 2024-01-06 at 3 59 04 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/398bea4b-dfcc-41d3-9fc2-b8e3a3f7198b">

#### Step2: Transforming

> Removing the null value records and changing the sales amount range which was from -1 to 1 (i.e because amount cannot be in negative).

<img width="1400" alt="Screenshot 2024-01-06 at 4 29 08 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/10c3e1a4-d464-4c81-bdfb-dba4158ad213">

> Also changed the USD sales amount to INR amount as normalised amount (so that will maintain the same currency).

<img width="1400" alt="Screenshot 2024-01-06 at 4 28 55 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/a78b584f-de4c-422a-a76d-35a6c9aa3a55">

#### Step3: Loading

> Loading the cleaned data to the tableau dashboard, Created a sheets of individual widgets of finding the total revenue and total number of products etc...
> And then created a dashboard with all of the sheets which was created earlier and combine them into one dashboard with adding filter to it, so that if we toggle and click on one area it gets reflected everywhere inside the dashboard.

<img width="1400" alt="Screenshot 2024-01-08 at 4 03 11 PM" src="https://github.com/Narayana-Royal/Sales-Insights/assets/88378136/1613f531-0998-41e3-b84c-dca05183030f">

> In the above picture you can see there's a sheets of individual widgets and those where combined in a single dashboard and for every year and every month we can view the total revenue and total number of products sold etc..
