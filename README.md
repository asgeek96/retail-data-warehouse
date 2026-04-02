# 📊 Sales Analytics Dashboard (Power BI)

## 🚀 Overview

This project presents an **interactive Sales Analytics Dashboard** built using Power BI to analyze sales performance, profitability, and product trends from retail data.

The dashboard enables stakeholders to quickly understand key business metrics and make data-driven decisions.

---

## 🎯 Business Problem

Retail businesses often struggle with:

* Understanding sales trends over time
* Identifying profitable products
* Analyzing regional performance

👉 This dashboard solves these challenges by providing **interactive and visual insights**.

---

## ⚙️ Tech Stack

* Power BI
* DAX (Data Analysis Expressions)
* Excel (Data Source)

---

## 📊 Dashboard Features

### 📌 Executive Overview

* Total Sales → $12.6M

* Total Profit → $1.47M

* Profit Margin → 11.6%

* YoY Growth → 51.5%

* Total Orders → 25K

* Sales Trend (Yearly)

* Profit Trend (Yearly)

---

### 📌 Detailed Analysis

* Sales by Region
* Top 10 Products
* Sales vs Profit (Scatter Analysis)
* Interactive slicers (Year, Region, Category)

---

## 📈 Key Insights

* Central region contributes highest sales
* Certain products generate high revenue but low profit
* Strong YoY growth indicates business expansion

---

## 🧠 DAX Measures

```DAX
Total Sales = SUM(Fact_Orders[Sales])
Total Profit = SUM(Fact_Orders[Profit])
Total Orders = DISTINCTCOUNT(Fact_Orders[OrderID])

Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DateTable[Date]))
Sales YoY % = DIVIDE([Total Sales] - [Sales LY], [Sales LY])

Profit Margin = DIVIDE([Total Profit], [Total Sales])
```

---

## 📸 Dashboard Preview

### Executive Dashboard

<img width="1001" height="568" alt="image" src="https://github.com/user-attachments/assets/3d4e281c-f1f3-4009-9f38-6a6e45adc9d9" />

### Detailed Analysis

<img width="998" height="567" alt="image" src="https://github.com/user-attachments/assets/e73a1d39-3b27-4510-a169-7f2fb50ee237" />

---

## 📁 Project Structure

```bash
Sales-Analytics-PowerBI/
│
├── dashboard/     # Power BI files & screenshots
├── data/          # Source dataset
├── docs/          # Relationships & measures
│
└── README.md
```

---

## 🚀 How to Use

1. Clone this repository
2. Open `.pbix` file in Power BI Desktop
3. Explore dashboard with slicers

---

## 💡 Learnings

* Data modeling using relationships
* Writing DAX measures
* Building interactive dashboards
* Business storytelling with data

---

## 🎯 Key Highlights

* Multi-page dashboard
* Advanced visualization (Scatter Plot)
* Real-world business use case
* Clean UI/UX design

---
