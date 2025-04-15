# Task-6

## Online Sales SQL Analysis

This project showcases a basic SQL-based analysis on an online sales dataset using MySQL. It includes the creation of a database, data insertion, and several queries to extract meaningful insights such as monthly revenue and order volumes.

## Database: online_sales.sql

The project begins by creating a simple sales database and a table named online_sales containing

order_id (INT): Unique ID for each order  
order_date (DATE): Date when the order was placed  
amount (DECIMAL): Total order amount  
product_id (INT): Identifier for the product  

## Screenshorts of each Query table : Query_1,Query_2,Query_3,Query_4,Query_5,Query_6

## Final query data stored in : Task_6.sql

##  SQL Queries & Insights

###  1. View All Data
sql
SELECT * FROM online_sales;
### 2. Extract Month from Order Date
sql
Copy
Edit
SELECT EXTRACT(MONTH FROM order_date) AS month FROM online_sales;
### 3. Monthly Revenue & Order Volume
sql
Copy
Edit
SELECT 
  EXTRACT(YEAR FROM order_date) AS year,
  EXTRACT(MONTH FROM order_date) AS month,
  SUM(amount) AS monthly_revenue,
  COUNT(DISTINCT order_id) AS order_volume
FROM online_sales
GROUP BY year, month
ORDER BY year ASC, month ASC;
### 4. Total Number of Orders
sql
Copy
Edit
SELECT COUNT(DISTINCT order_id) AS order_volume FROM online_sales;
### 5. Orders Placed in 2024
sql
Copy
Edit
SELECT * 
FROM online_sales 
WHERE order_date BETWEEN '2024-01-01' AND '2024-12-31';
## How to Use
Clone this repository.

Run the SQL scripts inside your MySQL environment.

Analyze and visualize monthly trends and performance.

## Tools Used
MySQL: For data storage and querying

SQL: For writing all analytical queries
