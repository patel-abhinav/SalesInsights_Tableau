# Sales Insights of AtliQ Hardware
Data analysis project for a computer hardware business aimed at addressing market challenges through real-time sales insights. **SQL** was used for data extraction and manipulation, while **Excel** supported data cleaning and analysis. The project involves building an interactive **Tableau** dashboard to help the Sales Director make data-driven decisions for improving performance and strategy.

## Problem Statement 
This project performed India-based AtliQ hardware company sales insights - A Data Analysis project.

AtliQ Hardware is a company that supplies computer hardware and peripherals to many clients such as surge stores, nomad stores etc. across India. AtliQ Hardware's head office is in Delhi, India and they have many regional offices throughout India.

The sales director for this company is facing a lot of challenges the market is growing dynamically and the sales director is facing issues in terms of tracking the sales in this dynamic growth market he is having issues with the growth of this business, as overall sales was declining. He is the regional manager for North India, South and Central India. Whenever he wants to get insights into these regions he would call these people and on the phone regional manager give some insights to him that this was the sales last quarter and we are going to grow by this much in the next quarter.

Atliq Hardware faced challenges with declining sales and lacked factual data to support decision-making, causing frustration for its owner. The regional manager failed to provide a complete business picture. To address this, I developed a Tableau sales dashboard, enabling the company to access daily insights, make data-driven decisions, and boost sales performance.

## Setting up MySQL Database
In this project, I worked with an SQL database dump provided in the `db_dump.sql` file. I began by downloading the file to my local system and then imported it onto the top of my MySQL environment to set up the database. This process initialized the necessary database structure and data, allowing me to proceed with further analysis. After the import, I performed additional queries and data exploration to extract key insights required for the project. This setup was critical in enabling a seamless workflow for my analysis.


## Data Analysis Using SQL
1. Show all customer records

    ``
    SELECT * FROM customers;
    ``

2. Show total number of customers

    ``
    SELECT count(*) FROM customers;
    ``

3. Show transactions for Chennai market (market code for chennai is Mark001

    ``
    SELECT * FROM transactions where market_code='Mark001';
    ``

4. Show distrinct product codes that were sold in chennai

    ``
    SELECT distinct product_code FROM transactions where market_code='Mark001';
    ``

5. Show transactions where currency is US dollars

    ``
    SELECT * from transactions where currency="USD"
    ``

6. Show transactions in 2020 join by date table

    ``
    SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;
    ``

7. Show total revenue in year 2020

    ``
   SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";
    ``

8. Show total revenue in year 2020, January Month

    ``
   SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");
    ``

9. Show total revenue in year 2020 in Chennai

    ``
SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.market_code="Mark001";
    ``
## Tech Stack
SQL, Tableau and Excel.

## Monogram
![AtliQ Hardware logo](https://github.com/user-attachments/assets/34676f28-418d-4055-868c-fbebbbe3d623)

