A complete end-to-end analytics project designed to explore pizza sales performance, identify trends, evaluate KPIs, and uncover insights using SQL and Power BI.
This project demonstrates your ability to work with data extraction, transformation, visualization, and business intelligence.

🚀 Project Highlights

📌 KPI-driven dashboard

📈 Trend analysis (daily, monthly)

🧮 SQL for aggregation, ranking & performance metrics

📊 Power BI interactive visualizations

🏆 Best & Worst selling pizzas

🎯 Category & size contribution analysis

🗂️ Project Files
File	Description
pizza_sales.csv	Raw dataset
pizza project.pbix	Power BI dashboard
pizza sql Document.rtf	SQL queries (KPIs, trends, performance analysis)
README.md	Documentation
🎯 Business Problem

The restaurant wants to understand:

How much revenue is being generated?

Which pizzas are performing the best?

What sizes or categories are most profitable?

What are the daily & monthly sales patterns?

How many pizzas are sold per order on average?

These insights help improve marketing, inventory, menu design, and operational decisions.

📊 Key Performance Indicators (KPIs)
KPI	Icon	Description
Total Revenue	💰	Total earnings from all pizza sales
Average Order Value (AOV)	🧾	Revenue per order
Total Pizzas Sold	🍕	Total quantity sold
Total Orders	📦	Unique orders placed
Avg. Pizzas per Order	➗	Ratio of quantity sold to number of orders
🧠 SQL Analysis
🔧 KPI Queries
SELECT SUM(total_price) AS total_revenue FROM pizza_sales;

SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS average_order_value 
FROM pizza_sales;

SELECT SUM(quantity) AS total_pizza_sold FROM pizza_sales;

SELECT COUNT(DISTINCT order_id) AS total_order FROM pizza_sales;

SELECT 
  CAST(CAST(SUM(quantity) AS DECIMAL(10,2)) / 
       CAST(COUNT(DISTINCT order_id) AS DECIMAL(10,2)) 
  AS DECIMAL(10,2)) AS average_pizza_per_order
FROM pizza_sales;

📆 Trend Analysis
🔸 Daily Orders
SELECT DATENAME(dw, order_date) AS order_day,
       COUNT(DISTINCT order_id) AS total_order
FROM pizza_sales
GROUP BY DATENAME(dw, order_date);

🔸 Monthly Orders
SELECT DATENAME(month, order_date) AS month_day,
       COUNT(DISTINCT order_id) AS total_order
FROM pizza_sales
GROUP BY DATENAME(month, order_date)
ORDER BY total_order DESC;

🧩 Category & Size Contribution
SELECT pizza_category,
       SUM(total_price) * 100 / (SELECT SUM(total_price) FROM pizza_sales) AS pct
FROM pizza_sales
GROUP BY pizza_category
ORDER BY pct DESC;

SELECT pizza_size,
       SUM(total_price) * 100 / (SELECT SUM(total_price) FROM pizza_sales) AS pct
FROM pizza_sales
GROUP BY pizza_size
ORDER BY pct DESC;

🏆 Best & Worst Sellers
🔝 Top 5 (Revenue / Quantity / Orders)
SELECT TOP 5 pizza_name, SUM(total_price) AS total_revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY total_revenue DESC;

🔻 Bottom 5 (Revenue / Quantity / Orders)
SELECT TOP 5 pizza_name, SUM(total_price) AS total_revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY total_revenue ASC;

📊 Power BI Dashboard Overview
🔹 Visuals Built:

🟦 Daily Sales Trend (Bar Chart)

📉 Monthly Sales Trend (Line Chart)

🥧 % Sales by Category (Pie Chart)

🥧 % Sales by Size (Pie Chart)

🔺 Best Sellers (Revenue, Quantity, Orders)

🔻 Worst Sellers (Revenue, Quantity, Orders)

🎯 Quantity Sold by Category (Funnel Chart)

🖼️ Optional: Add dashboard screenshots for more impact!
🛠 Tools & Technologies
Category	Tools
Database / Querying	SQL Server
Visualization	Power BI
Data Analysis	SQL Aggregations, Joins, Date Functions
File Formats	CSV, PBIX, RTF
Skills Demonstrated	KPI design, trend analysis, ranking, BI reporting
📌 Key Insights

Revenue is driven by specific high-performing pizzas

Large size pizzas contribute highest revenue

Friday/Saturday show peak order volumes

Supreme & Deluxe pizzas dominate performance

Some categories underperform consistently

Summer months show highest activity

🏁 Conclusion

This project demonstrates your ability to perform:

✔ SQL-based business analysis

✔ KPI calculation

✔ Trend identification

✔ Power BI dashboard creation

✔ Data storytelling

A strong example of Business Intelligence & Analytics for real-world retail/restaurant data.
