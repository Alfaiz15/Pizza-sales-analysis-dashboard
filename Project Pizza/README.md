# 🍕 Data-Driven Pizza Sales Performance Analysis

## 📌 Executive Summary

This project demonstrates **Data Analysis** capabilities with a focus on **Operations**, transforming one year of raw transaction data into **actionable insights**. Analysis was performed efficiently using **Microsoft Excel / Google Sheets**, resulting in a **dashboard** that guides management on **Revenue Optimization**, **Forecasting**, and **Inventory Efficiency**.

---

## 🎯 Business Objectives

This analysis aims to answer four key business questions:

1. **KPI Performance:** What are **Total Revenue**, **Total Orders**, and **Average Order Value (AOV)**?
2. **Market Trends:** What are the monthly revenue trends (*seasonality*) over the year?
3. **Product Prioritization:** What are the **Top 10 Selling Pizzas** by quantity?
4. **Pricing Strategy:** How does **Revenue** contribute by **Category** and **Pizza Size**?

---

## 🛠️ Tools & Data

* **Primary Tool:** Microsoft Excel / Google Sheets  
* **Data Source:** Daily Sales Transactions (`Data Pizza.xlsx` / `Raw Data Pizza Sales.csv`)

---

## ⚙️ Analysis Workflow (Excel/Sheets Focused)

### Phase 1: Data Cleansing & Feature Engineering

Created new variables (`features`) from raw data, essential before building Pivot Tables.

| New Column | Calculation | Key Excel Formula | Business Purpose |
| :--- | :--- | :--- | :--- |
| **Total Revenue** | Unit Price x Quantity | `= unit_price * quantity` | Core financial metric. |
| **Month Name** | Extract month from date | `=TEXT(order_date, "mmmm")` | Seasonal & Forecasting analysis. |
| **Day Name** | Extract day from date | `=TEXT(order_date, "dddd")` | Workload analysis & staff scheduling. |
| **Total Unique Orders** | Aggregate unique order IDs | `=COUNTA(UNIQUE(order_id_column))` | Measure transaction volume. |

---

### Phase 2: Pivot Table (The Engine Room)

Pivot Tables summarize data and answer key business questions:

1. **KPI Summary:** Calculate **Total Revenue**, **Total Orders**, and **AOV** (`Total Revenue / Total Orders`).  
2. **Revenue & Quantity:** Separate pivots for `Month Name` (for Line Chart) and `pizza_name` (Top 10 Filter).  
3. **Complex Segmentation:** Rows: `pizza_category`, Columns: `pizza_size`, Values: `SUM of Total Revenue` (analyzing contribution by size).

---

### Phase 3: Dashboard & Interactivity

Clear, concise visualization for effective insights communication.

| Visualization | Chart Type | Reinforced Insight |
| :--- | :--- | :--- |
| **Monthly Revenue Trend** | Line Chart | Highlights seasonality (**Peak July**, **Low September**) for planning. |
| **Quantity per Category** | Donut Chart | Inventory prioritization: **Classic (30%)**, **Supreme (24%)** dominate volume. |
| **Revenue by Size** | Stacked Bar Chart | Upselling strategy: **Large (L)** is the primary revenue driver. |
| **Interactivity** | Slicer | Connect `pizza_category` slicer to all charts for ad-hoc analysis. |

---

## 💡 Key Insights & Strategic Recommendations

Data analysis produced actionable insights to enhance efficiency and profit:

| Insight | Strategic Recommendation (Operations & Revenue) |
| :--- | :--- |
| **Seasonal Fluctuation** | **Forecasting & Marketing:** Allocate marketing budget to promote low-season months (**September**, **November**) to stabilize **Revenue Stream**. |
| **Product Dominance** | **Operations Efficiency:** Conduct *Time & Motion Study* for **The Classic Deluxe Pizza** (Top Seller) to reduce preparation time and mitigate bottlenecks. |
| **AOV Potential** | **Pricing Strategy:** Focus on **Upselling** to **Large (L)** sizes and create profitable bundling packages. |
| **Category Focus** | **Inventory Management:** Designate **Classic** and **Supreme** as Tier 1 categories. Increase buffer stock to prevent stock-outs during peak season. |
