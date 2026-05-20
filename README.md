# logistics-sql-business-analysis
## Project Overview
This project focuses on analyzing logistics and delivery operations data using advanced SQL queries in MySQL Workbench.

The goal of this analysis was to identify operational inefficiencies, delivery delays, return trends, customer ordering behavior, and partner performance insights using real-world business scenarios.

## Tools & Technologies Used
- SQL
- MySQL Workbench
- Data Analysis
- Business Intelligence

## SQL Concepts Applied
- Joins
- Aggregate Functions
- Subqueries
- CASE WHEN Statements
- Common Table Expressions (CTEs)
- Window Functions
- RANK() & DENSE_RANK()
- LAG() & LEAD()
- GROUP BY & HAVING
- Conditional Analysis

## Business Problems Solved

### 1. Orders with Above Average Delivery Delays
Identified orders where delivery delays exceeded the overall average delay time.

### 2. Cities with Highest Return Rates
Analyzed return behavior across cities to identify high-return locations.

### 3. Partner Performance Analysis
Evaluated logistics partners whose average delivery delays were higher than overall benchmarks.

### 4. Customer Ranking Analysis
Ranked customers based on total order frequency using window functions.

### 5. Product Ranking Analysis
Identified top-performing products based on order frequency.

### 6. Delivery Delay Trend Analysis
Compared previous and next delivery times using LAG() and LEAD() functions.

### 7. Payment Failure Detection
Detected cases where orders were delivered despite failed payment statuses.

### 8. Category-Wise Product Performance
Identified top-selling products across different categories.

## Key Insights
- Certain cities showed significantly higher return activity.
- Multiple logistics partners had above-average delivery delays.
- Customer ordering patterns revealed strong repeat-order behavior.
- Delivery timing analysis highlighted inconsistent operational performance.
- Several payment-risk cases were identified where deliveries succeeded despite payment failures.

## Sample SQL Analysis

### Window Function Example
```sql
select c.Customer_ID,
count(distinct o.Order_ID) as total_order,

rank() over(
order by count(distinct o.Order_ID) desc
) as customer_rank

from orders o
join customers c
on o.Customer_ID = c.Customer_ID

group by c.Customer_ID;
```

---

## Project Structure


logistics-sql-business-analysis/
│
├── README.md
├── logistics_queries.sql
├── screenshots/
│   ├── cte_query.png
│   ├── window_function.png
│   ├── case_when.png
│   └── results.png
```

## Screenshots
Add your SQL query screenshots and result outputs inside the `screenshots` folder.

---

## Conclusion
This project demonstrates how SQL can be used beyond querying data — helping generate actionable business insights for logistics and operational decision-making.

---
