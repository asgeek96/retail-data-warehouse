# 🏬 Retail Data Warehouse & Executive Dashboard

## 🚀 Overview

Built an end-to-end retail analytics solution simulating a real-world enterprise data warehouse using SQL Server, SSIS, and Power BI. The solution enables business users to track sales performance, profitability, and customer trends through an interactive executive dashboard.

---

## 🎯 Business Problem

Retail organizations often struggle with:

* Disconnected data across multiple sources
* Lack of centralized reporting
* Difficulty in tracking key business KPIs

👉 This project solves these challenges by creating a **centralized data warehouse and interactive BI dashboard** for real-time decision-making.

---

## 🏗️ Architecture

```
Source (CSV Files) → Staging → Data Warehouse → Power BI Dashboard
```

* **Staging Layer**: Raw data ingestion
* **Data Warehouse**: Cleaned & structured star schema
* **Power BI**: Business insights & visualization

---

## 🗄️ Data Model

Designed using **Star Schema** for optimal performance:

* **Fact Table**: `Fact_Orders`
* **Dimension Tables**:

  * `Dim_Customers`
  * `Dim_Products`
  * `Dim_Geography`
  * `DateTable`

---

## ⚙️ Tech Stack

* **SQL Server** → Data warehouse storage
* **SSIS** → ETL pipeline automation
* **Power BI** → Dashboard & reporting
* **DAX** → KPI calculations

---

## 🔄 ETL Pipeline

1. Extract data from CSV files
2. Load into staging tables
3. Transform & clean data
4. Load into fact & dimension tables
5. Validate data using record count checks
6. Schedule ETL via SSIS

---

## 📊 Dashboard Features

### 📌 Executive Overview

* KPI Cards (Sales, Profit, Orders, Margin, YoY Growth)
* Sales Trend (Yearly)
* Profit Trend (Yearly)

### 📌 Detailed Analysis

* Sales by Region
* Top 10 Products
* Sales vs Profit (Scatter Analysis)
* Interactive slicers (Year, Region, Category)

---

## 📈 Key KPIs

* **Total Sales** → $12.6M
* **Total Profit** → $1.47M
* **Profit Margin** → 11.6%
* **YoY Growth** → 51.5%
* **Total Orders** → 25K

---

## 💡 Business Insights

* Identified high-performing regions (e.g., Central region leading sales)
* Detected products with high sales but low profitability
* Enabled filtering by region, category, and year for granular analysis

---

## 🧠 Learnings

* Data warehouse design using **Star Schema**
* Building scalable **ETL pipelines with SSIS**
* Writing optimized SQL queries
* Designing **business-focused dashboards in Power BI**
* Using DAX for KPI and time intelligence

---

## 🎯 Key Highlights

* Multi-page interactive dashboard
* Advanced visualization (Scatter Plot for Sales vs Profit)
* Real-world business use case simulation
* Clean and professional UI/UX design

---

## 📸 Dashboard Preview

<img width="1001" height="568" alt="image" src="https://github.com/user-attachments/assets/3d4e281c-f1f3-4009-9f38-6a6e45adc9d9" />
<img width="998" height="567" alt="image" src="https://github.com/user-attachments/assets/e73a1d39-3b27-4510-a169-7f2fb50ee237" />


---

## 🚀 Future Improvements

* Add real-time data refresh
* Implement row-level security (RLS)
* Deploy dashboard to Power BI Service

---
