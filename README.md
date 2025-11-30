<h1>🍕 Pizza Sales Analytics Dashboard</h1>

<p>
A complete end-to-end analytics project designed to explore pizza sales performance, identify trends, evaluate KPIs, and uncover insights using <b>SQL</b> and <b>Power BI</b>.  
This project demonstrates your ability to work with data extraction, transformation, visualization, and business intelligence.
</p>

<br>

<h2>🚀 Project Highlights</h2>
<ul>
  <li>📌 KPI-driven dashboard</li>
  <li>📈 Trend analysis (daily, monthly)</li>
  <li>🧮 SQL for aggregation, ranking & performance metrics</li>
  <li>📊 Power BI interactive visualizations</li>
  <li>🏆 Best & Worst selling pizzas</li>
  <li>🎯 Category & size contribution analysis</li>
</ul>

<br>

<h2>🗂️ Project Files</h2>

<table>
<tr><th>File</th><th>Description</th></tr>
<tr><td>pizza_sales.csv</td><td>Raw dataset</td></tr>
<tr><td>pizza project.pbix</td><td>Power BI dashboard</td></tr>
<tr><td>pizza sql Document.rtf</td><td>SQL queries (KPIs, trends, performance analysis)</td></tr>
<tr><td>README.md</td><td>Documentation</td></tr>
</table>

<br>

<h2>🎯 Business Problem</h2>

<p>The restaurant wants to understand:</p>
<ul>
  <li>💰 How much revenue is being generated?</li>
  <li>🍕 Which pizzas perform the best?</li>
  <li>📦 What sizes or categories are most profitable?</li>
  <li>📅 What are the daily & monthly sales patterns?</li>
  <li>➗ How many pizzas are sold per order on average?</li>
</ul>

<p>These insights help improve marketing, inventory management, menu design, and operational decisions.</p>

<br>

<h1>📊 Key Performance Indicators (KPIs)</h1>

<table>
<tr><th>KPI</th><th>Icon</th><th>Description</th></tr>
<tr><td>Total Revenue</td><td>💰</td><td>Total earnings from all pizza sales</td></tr>
<tr><td>Average Order Value (AOV)</td><td>🧾</td><td>Revenue per order</td></tr>
<tr><td>Total Pizzas Sold</td><td>🍕</td><td>Total quantity sold</td></tr>
<tr><td>Total Orders</td><td>📦</td><td>Unique orders placed</td></tr>
<tr><td>Avg. Pizzas per Order</td><td>➗</td><td>Quantity sold / total orders</td></tr>
</table>

<br>

<h1>🧠 SQL Analysis</h1>

<h2>🔧 KPI Queries</h2>

<pre><code>
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
</code></pre>

<br>

<h2>📆 Trend Analysis</h2>

<h3>🔸 Daily Orders</h3>
<pre><code>
SELECT DATENAME(dw, order_date) AS order_day,
       COUNT(DISTINCT order_id) AS total_order
FROM pizza_sales
GROUP BY DATENAME(dw, order_date);
</code></pre>

<h3>🔸 Monthly Orders</h3>
<pre><code>
SELECT DATENAME(month, order_date) AS month_day,
       COUNT(DISTINCT order_id) AS total_order
FROM pizza_sales
GROUP BY DATENAME(month, order_date)
ORDER BY total_order DESC;
</code></pre>

<br>

<h2>🧩 Category & Size Contribution</h2>

<pre><code>
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
</code></pre>

<br>

<h1>🏆 Best & Worst Sellers</h1>

<h3>🔝 Top 5 (Revenue / Quantity / Orders)</h3>
<pre><code>
SELECT TOP 5 pizza_name, SUM(total_price) AS total_revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY total_revenue DESC;
</code></pre>

<h3>🔻 Bottom 5 (Revenue / Quantity / Orders)</h3>
<pre><code>
SELECT TOP 5 pizza_name, SUM(total_price) AS total_revenue
FROM pizza_sales
GROUP BY pizza_name
ORDER BY total_revenue ASC;
</code></pre>

<br>

<h1>📊 Power BI Dashboard Overview</h1>

<ul>
  <li>🟦 Daily Sales Trend (Bar Chart)</li>
  <li>📉 Monthly Sales Trend (Line Chart)</li>
  <li>🥧 Category-wise Sales %</li>
  <li>🥧 Size-wise Sales %</li>
  <li>🔺 Best Sellers (Revenue, Quantity, Orders)</li>
  <li>🔻 Worst Sellers (Revenue, Quantity, Orders)</li>
  <li>🎯 Category Funnel Chart (Quantity Sold)</li>
</ul>

<br>

<h1>🛠 Tools & Technologies</h1>

<table>
<tr><th>Category</th><th>Tools</th></tr>
<tr><td>Database / Querying</td><td>SQL Server</td></tr>
<tr><td>Visualization</td><td>Power BI</td></tr>
<tr><td>Data Analysis</td><td>SQL Aggregations, Joins, Date Functions</td></tr>
<tr><td>File Formats</td><td>CSV, PBIX, RTF</td></tr>
<tr><td>Skills Demonstrated</td><td>KPI design, BI reporting, trend analysis</td></tr>
</table>

<br>

<h1>📌 Key Insights</h1>

<ul>
  <li>💰 High revenue driven by select best-selling pizzas</li>
  <li>🍕 Large size pizzas generate the highest revenue</li>
  <li>📆 Fridays and Saturdays have peak sales</li>
  <li>🏆 Supreme & Deluxe pizzas dominate revenue</li>
  <li>⚠️ Some categories consistently underperform</li>
  <li>🌞 Sales peak during summer months</li>
</ul>

<br>

<h1>🏁 Conclusion</h1>

<p>This project demonstrates your ability to perform:</p>

<ul>
  <li>✔ SQL-based business analysis</li>
  <li>✔ KPI development</li>
  <li>✔ Trend identification</li>
  <li>✔ Power BI dashboard creation</li>
  <li>✔ Data storytelling</li>
</ul>

<p>A strong example of <b>Business Intelligence & Analytics</b> applied to real-world restaurant sales.</p>

