# 🍕 Pizza Sales Analytics — SQL Business Intelligence Project

<p align="center">
  <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white"/>
  <img src="https://img.shields.io/badge/SQL-Data%20Analysis-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Domain-Food%20%26%20Beverage-red?style=for-the-badge"/>
</p>

---

## 📌 Project Overview

This end-to-end SQL analytics project dives into **a full year of pizza sales data** to surface actionable business intelligence for a pizza restaurant chain. Using MySQL, I transformed raw transactional records into strategic insights covering **revenue performance, customer ordering behaviour, peak demand windows, and product-level profitability**.

The project mirrors real-world BI workflows — from raw data ingestion and relational modelling to KPI calculation, cohort-level analysis, and executive-ready recommendations. It is designed to demonstrate the depth of SQL skills and business acumen that data analyst roles demand.

---

## 🚩 Business Problem

> *"We have sales data — but we don't know what's driving revenue, when demand spikes, or which products we should be promoting."*

The restaurant management needed answers to four critical questions:

1. **Which products drive the most revenue?** — to focus marketing investment
2. **When are peak sales periods?** — to optimise staffing and inventory
3. **How do customers order?** — to identify upsell and combo opportunities
4. **Which categories perform best?** — to guide menu strategy and pricing

---

## 🎯 Project Objectives

- Calculate and track core business KPIs (Revenue, Orders, AOV)
- Identify top-selling pizzas by both volume and revenue
- Analyse time-based trends — hourly, daily, and cumulative
- Perform category-level performance comparison
- Deliver data-backed business recommendations

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|------|---------|
| **MySQL** | Data storage, querying, and analysis |
| **SQL** | Aggregations, joins, window functions, subqueries |
| **Excel / CSV** | Raw dataset storage and initial inspection |
| **GitHub** | Version control and project documentation |

---

## 📂 Dataset Information

The dataset simulates one full year of pizza restaurant transactions and is structured across **four relational tables**:

| Table | Description | Key Columns |
|-------|-------------|-------------|
| `orders` | One record per customer order | `order_id`, `date`, `time` |
| `order_details` | Line items within each order | `order_detail_id`, `order_id`, `pizza_id`, `quantity` |
| `pizzas` | Pizza SKUs with size and price | `pizza_id`, `pizza_type_id`, `size`, `price` |
| `pizza_types` | Pizza names, categories, ingredients | `pizza_type_id`, `name`, `category`, `ingredients` |

**Dataset size:** 21,350 orders · 49,574 pizzas sold · 4 product categories

> 📥 Download: [pizza_sales.zip](pizza_sales.zip)

### Entity Relationship Diagram

```
orders ──< order_details >── pizzas ──< pizza_types
```

- `order_details` acts as a bridge between `orders` and `pizzas`
- `pizzas` links to `pizza_types` for category-level analysis

![ER Diagram](ER_Diagram.png)

---

## 🔄 Project Workflow

```
Data Collection → Data Import → Data Cleaning → Exploratory Analysis
      → KPI Calculation → Advanced Analysis → Insights → Recommendations
```

**1. Data Collection & Import**
- Downloaded four CSV files representing relational tables
- Imported into MySQL and verified primary/foreign key relationships

**2. Data Cleaning & Validation**
- Checked for null values and duplicate records
- Corrected data types (date, time, numeric price fields)
- Validated referential integrity across all joins

**3. Exploratory Data Analysis**
- Profiled each table (row counts, value distributions, date ranges)
- Mapped out table relationships and join paths

**4. KPI & Aggregation Analysis**
- Computed total revenue, order count, quantity sold, and AOV
- Grouped metrics by pizza, category, hour, and day

**5. Advanced SQL Analysis**
- Applied `RANK()` and `DENSE_RANK()` window functions for product rankings
- Used `SUM() OVER()` for cumulative revenue trending
- Leveraged multi-table `INNER JOINs` (3+ tables) for category-level rollups

**6. Insight Generation & Documentation**
- Translated query results into plain-language business findings
- Structured recommendations around revenue, operations, and menu strategy

---

## 📊 Dashboard / Analysis Snapshots

> *Add screenshots of your query results or any visualisations here.*

| Analysis | Preview |
|----------|---------|
| Revenue by Category | *(screenshot)* |
| Top 5 Pizzas by Revenue | *(screenshot)* |
| Orders by Hour of Day | *(screenshot)* |
| Cumulative Revenue Trend | *(screenshot)* |

---

## 📈 Key KPIs

<table>
  <tr>
    <th>📦 Total Orders</th>
    <th>💰 Total Revenue</th>
    <th>🍕 Pizzas Sold</th>
    <th>🧾 Avg Order Value</th>
    <th>📁 Categories</th>
  </tr>
  <tr>
    <td align="center"><b>21,350</b></td>
    <td align="center"><b>₹8,17,860</b></td>
    <td align="center"><b>49,574</b></td>
    <td align="center"><b>₹38.3</b></td>
    <td align="center"><b>4</b></td>
  </tr>
</table>

---

## 💡 Key Insights

### 🏆 Product Performance
- **Thai Chicken Pizza** is the single highest revenue generator at **~₹43,000**, outperforming all other SKUs
- The **top 3 revenue-generating pizzas are all chicken-based**, revealing a clear and consistent customer preference for chicken varieties
- Revenue is concentrated among a small number of high-performing products — a classic **Pareto distribution** — suggesting the long tail offers optimisation potential

### 📂 Category Performance
- The **Classic category leads all segments with ~₹2,20,000 in revenue**, making it the cornerstone of the menu
- Revenue is relatively balanced across the four categories, indicating a healthy product mix with no single point of failure
- Premium categories present an opportunity to improve margin through targeted promotion

### ⏰ Time-Based Demand Patterns
- **Peak hours are 12 PM – 2 PM (lunch rush) and 5 PM – 8 PM (dinner window)**, accounting for the highest concentration of daily orders
- The busiest single day recorded **115 orders — approximately 2× the daily average** — indicating significant demand volatility to plan around
- Early mornings and late nights consistently underperform, presenting an opportunity to test off-peak promotions

### 📉 Revenue Trend Analysis
- Cumulative revenue (calculated via `SUM() OVER()`) shows **steady business growth** across the year with periodic spikes
- **Highest single-day revenue exceeded ₹4,400**, highlighting the outsized impact of peak trading days on monthly totals
- Running totals reveal consistent compounding growth, validating the business model

---

## ✅ Business Recommendations

**1. Double Down on Chicken Pizzas**
The top 3 pizzas by revenue are chicken-based. Prioritise these in marketing campaigns, menu placement, and combo deals to maximise revenue per order.

**2. Staff and Stock for Peak Windows**
Lunch (12–2 PM) and dinner (5–8 PM) drive the bulk of daily revenue. Align staffing levels, prep schedules, and ingredient stock to these windows to reduce wait times and prevent stockouts.

**3. Revive Underperforming Products**
Introduce limited-time offers, price promotions, or combo bundles for low-performing SKUs to improve sell-through rates without removing them from the menu.

**4. Leverage Off-Peak Hours**
Early morning and late-night demand is low but represents untapped capacity. Consider time-based discounts or "happy hour" promotions to smooth demand and improve labour efficiency.

**5. Invest in the Classic Category**
With ~₹2,20,000 in revenue, Classic is the most trusted category. Protect its quality and availability while exploring premium variants to capture higher-margin upsells.

---

## 🧠 Skills Demonstrated

| Category | Skills Applied |
|----------|---------------|
| **SQL Querying** | `SELECT`, `WHERE`, `ORDER BY`, `LIMIT` |
| **Data Joining** | `INNER JOIN` across 3+ relational tables |
| **Aggregation** | `SUM()`, `COUNT()`, `AVG()`, `GROUP BY`, `HAVING` |
| **Window Functions** | `RANK()`, `DENSE_RANK()`, `SUM() OVER()` |
| **Subqueries** | Nested queries for filtered aggregations |
| **Business Analysis** | KPI definition, trend analysis, cohort thinking |
| **Communication** | Translating SQL output into business recommendations |

---

## 🗂️ Repository Structure

```
Pizza-Sales-Analysis-using-SQL/
│
├── SQL/
│   └── pizza_sales.sql          # All SQL queries (Basic → Advanced)
│
├── Dataset/
│   ├── orders.csv
│   ├── order_details.csv
│   ├── pizzas.csv
│   └── pizza_types.csv
│
├── Docs/
│   └── insights.md              # Detailed written insights
│
├── ER_Diagram.png               # Entity Relationship Diagram
└── README.md
```

---

## 🔍 Sample SQL Query

**Revenue contribution by category:**

```sql
-- Which category generated the highest revenue?
SELECT 
    pt.category,
    ROUND(SUM(od.quantity * p.price), 2) AS total_revenue
FROM pizza_types pt
JOIN pizzas p 
    ON pt.pizza_type_id = p.pizza_type_id
JOIN order_details od 
    ON od.pizza_id = p.pizza_id
GROUP BY pt.category
ORDER BY total_revenue DESC;
```

**Top pizzas per category using window functions:**

```sql
-- Rank pizzas by revenue within each category
SELECT 
    category,
    name,
    ROUND(SUM(od.quantity * p.price), 2) AS revenue,
    RANK() OVER (PARTITION BY category ORDER BY SUM(od.quantity * p.price) DESC) AS rnk
FROM pizza_types pt
JOIN pizzas p ON pt.pizza_type_id = p.pizza_type_id
JOIN order_details od ON od.pizza_id = p.pizza_id
GROUP BY category, name;
```

---

## 👤 Author

**Jijau Khandale**  
Aspiring Data Analyst | SQL · Excel · Python · Data Storytelling

<p>
  <a href="http://www.linkedin.com/in/jijau-khandale">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=for-the-badge&logo=linkedin"/>
  </a>
  <a href="https://github.com/Jk1201-web">
    <img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github"/>
  </a>
  <a href="https://www.kaggle.com/jijaumohankhandale">
    <img src="https://img.shields.io/badge/Kaggle-Profile-20BEFF?style=for-the-badge&logo=kaggle"/>
  </a>
</p>

---

> ⭐ *If this project added value to your learning or inspired your own work, consider giving it a star — it helps others discover it too!*
