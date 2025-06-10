# Sales-Insights-Data-Analysis-Project

# 📊 Sales Insights Dashboard

### Dashboard File: `Sales Insights Project.pbix`

---

## 🎯 Problem Statement

The **Sales Insights Dashboard** is designed to help businesses gain actionable insights from their sales data. It enables stakeholders to monitor performance across regions, customers, and product categories, track revenue trends, and make data-informed decisions.

By analyzing this dashboard, the following business questions can be addressed:

- Which regions generate the highest revenue and sales volume?
- Which customers and products contribute most to the business?
- What are the seasonal patterns in revenue?
- Are there any data inconsistencies (e.g., missing product mappings)?
- How can we optimize our strategy based on performance trends?

---

## 🛠️ Steps Followed

### ✅ 1. Data Connection – MySQL Integration
- Connected **Power BI** to a **MySQL** database using the built-in MySQL connector.
- Provided connection string, server address, and login credentials.
- Imported required tables like `transactions`, `markets`, `products`, and `customers`.
- Chose **Import mode** for static data load and **DirectQuery** for scheduled refreshes when needed.

---

### ✅ 2. Data Transformation (Power Query Editor)
Cleaned and transformed raw MySQL data using Power Query steps:

- **Filtered Rows**: Removed irrelevant or incomplete entries.
- **Added Conditional Column**: Created a custom column for categorizing or flagging data.
- **Renamed Columns**: Cleaned and standardized column names for clarity.

---

### ✅ 3. Data Modeling
- Established relationships among tables: `transactions`, `products`, `customers`, `markets`, and a **date table**.
- Created a **calendar table** to support drill-down by Year, Quarter, and Month.
- Ensured correct data types (e.g., revenue as decimal, dates as datetime).

---

### ✅ 4. DAX Measures and Calculated Columns
Defined the following DAX measures:

- **Total Revenue**: `SUM([revenue])`
- **Total Sales Quantity**: `SUM([sales_qty])`
- **Profit Margin** (if available): `DIVIDE([Profit], [Revenue])`
- **Year**: `YEAR([order_date])`
- **Month Name**: `FORMAT([order_date], "MMMM")`

---

### ✅ 5. Visual Design
Created a one-page interactive dashboard using Power BI visuals:

- **Card Visuals**:
  - 📈 Total Revenue: `984.87M`
  - 📦 Total Sales Quantity: `2.43M`

- **Bar Charts**:
  - Revenue by `markets_name`
  - Sales Quantity by `markets_name`
  - Revenue by `customer_name`
  - Revenue by `product_code`

- **Line Chart**:
  - Revenue Trend over time with drill-down to month level

- **Slicers**:
  - Years: 2017, 2018, 2019, 2020
  - Order Dates for custom filtering



---

## 📈 Insights

### 🔹 Revenue and Sales Overview
- **Total Revenue**: `984.87M`
- **Total Sales Quantity**: `2.43M`

### 🔹 Market Performance
- **Delhi NCR** is the highest performing market:
  - Revenue: `520M`
  - Quantity: `1M`
- Mumbai and Ahmedabad are secondary contributors with `150M` and `132M` respectively.

### 🔹 Product-Level Insights
- Product codes `Prod040`, `Prod159`, and `Prod065` contribute moderately.
- A large chunk of revenue (`469M`) is under a **blank product code**, indicating missing product mapping – a critical data quality issue.

### 🔹 Customer-Level Revenue
- Top customer: `Electrical...` contributes `413M` in revenue.
- Other significant customers include:
  - Excel Store: `49M`
  - Premium...: `45M`
  - Nixon: `44M`

### 🔹 Time-Based Analysis
- Highest revenue spike: **Q1 2020**, especially on **March 1st** with ~`26M`.
- Revenue declined sharply afterward, possibly due to seasonal or economic factors.

---


