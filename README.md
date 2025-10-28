# Sqlserver-online-sales-analysis
Sales data analysis using SQL Server | SUM, COUNT, GROUP BY, ORDER BY | Monthly and yearly revenue insights.


Sales Data Analysis using SQL Server (SSMS)
📘 Overview

This project demonstrates data analysis using SQL Server Management Studio (SSMS) on an online sales dataset.
The goal is to calculate key sales insights such as total orders, total turnover, and monthly sales distribution using SQL aggregation and date functions.

📊 Objectives

Calculate total number of unique orders

Extract year and month from order dates

Summarize sales using GROUP BY and ORDER BY

Compute total turnover (revenue)

Filter data for specific time ranges (e.g., 2019)

🧩 Dataset Information

The dataset (sales_data.xlsx) contains the following columns:

Column Name	Description
Order Date	Date and time of purchase
Order ID	Unique identifier for each order
Product	Product name
Quantity Ordered	Number of items sold
Price Each	Price per unit
Turnover	Total sale value
Margin	Profit margin per sale
Purchase Address	Customer’s purchase location
🧠 SQL Queries Used
🔹 1. Count Total Unique Orders
SELECT 
    COUNT(DISTINCT [Order ID]) AS total_orders
FROM sales_data$;


📈 Result: 178,437 total unique orders

🔹 2. Extract Year and Month from Order Date
SELECT 
    YEAR([Order Date]) AS order_year,
    MONTH([Order Date]) AS order_month
FROM [dbo].[sales_data$];


🧩 Result: Extracted year and month components from each order.

🔹 3. Group by Year and Month
SELECT 
    YEAR([Order Date]) AS order_year,
    MONTH([Order Date]) AS order_month
FROM [dbo].[sales_data$]
WHERE [Order Date] BETWEEN '2019-01-01' AND '2019-12-31'
GROUP BY 
    YEAR([Order Date]), 
    MONTH([Order Date]);


📊 Result: Grouped all orders month-wise for 2019.

🔹 4. Order by Sorting (Chronologically)
SELECT 
    YEAR([Order Date]) AS order_year,
    MONTH([Order Date]) AS order_month
FROM [dbo].[sales_data$]
WHERE [Order Date] BETWEEN '2019-01-01' AND '2019-12-31'
GROUP BY 
    YEAR([Order Date]), 
    MONTH([Order Date])
ORDER BY 
    order_year, 
    order_month;


📅 Result: Sorted output showing months in chronological order.

🔹 5. Sum of Turnover (Total Revenue)
SELECT 
    SUM(turnover) AS total_turnover
FROM [dbo].[sales_data$];


💰 Result: Total turnover = ₹34,492,035.97

🧾 Insights & Observations

Total Orders: 178,437 unique orders recorded.

Sales Period: Data covers all months of 2019.

Monthly Sales Trend: Every month (Jan–Dec) shows active order data.

Total Turnover: Over ₹34 million in revenue generated.

Efficient Use of SQL: Queries demonstrate grouping, aggregation, sorting, and filtering effectively.

⚙️ Tools Used

SQL Server Management Studio (SSMS) – Query execution and data analysis

Excel (.xlsx) – Source data file

Windows OS – Execution environment

GitHub – Project version control and sharing

📁 Project Structure
📦 Online_sales-data-sql-analysis
├── Online_sales_data.xlsx
├── Queries/
│   ├── total_orders.sql
│   ├── extract_month_year.sql
│   ├── group_by_year_month.sql
│   ├── order_by_sorting.sql
│   └── total_turnover.sql
├── Screenshots/
│   ├── count of total orders.jpg
│   ├── extract month from order date.jpg
│   ├── group by year&month.jpg
│   ├── order by sorting.jpg
│   └── sum of turnover.jpg
└── README.md

📈 Learning Outcomes

Understanding of SQL aggregate functions (SUM, COUNT, etc.)

Practical usage of date functions (YEAR(), MONTH())

Importance of GROUP BY and ORDER BY for trend analysis

How to calculate KPIs like revenue and order count using SQL
