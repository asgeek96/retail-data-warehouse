# Case Study: Enterprise Sales Analytics Dashboard

**Tool:** Power BI Desktop  
**Dataset:** Retail sales data · 25,000 orders · Excel source  
**Analyst:** Anubhav Srivastava  

---

## The Business Problem

Retail businesses generate transactional data constantly — but without a structured view, that data doesn't translate into decisions. Sales managers typically face three recurring questions they can't answer quickly:

- Are we growing, and by how much compared to last year?
- Which products are driving profit — not just revenue?
- Which regions are performing, and which are masking underperformance behind high sales volume?

Answering these from raw Excel data means manual pivot tables, inconsistent calculations, and no interactivity. This dashboard was built to replace that process with a single, always-current source of truth across two focused report pages.

---

## Approach

### Data Modelling

The source data came in as a flat Excel file. Before any measures were written, a proper data model was established:

- A **DateTable** was created to enable time intelligence functions — without a dedicated date table, DAX functions like `SAMEPERIODLASTYEAR` will not work correctly
- Relationships were defined between the fact table (`Fact_Orders`) and the date dimension
- The model was kept clean and flat — no unnecessary complexity for a single-source dataset

This step is often skipped by analysts who jump straight to visuals. Getting it right here is what makes the YoY measures reliable.

### DAX Measures

Six core measures power the entire dashboard:

```dax
Total Sales = SUM(Fact_Orders[Sales])

Total Profit = SUM(Fact_Orders[Profit])

Total Orders = DISTINCTCOUNT(Fact_Orders[OrderID])

Sales LY = CALCULATE([Total Sales], SAMEPERIODLASTYEAR(DateTable[Date]))

Sales YoY % = DIVIDE([Total Sales] - [Sales LY], [Sales LY])

Profit Margin = DIVIDE([Total Profit], [Total Sales])
```

A few deliberate choices here:

- `DISTINCTCOUNT` on `OrderID` rather than `COUNTROWS` — ensures orders with multiple line items aren't double-counted
- `DIVIDE` used throughout instead of `/` — handles zero-denominator cases gracefully without throwing errors
- `SAMEPERIODLASTYEAR` requires the DateTable relationship to be active — this is why the data modelling step above is non-negotiable

### Report Structure

Two pages, each answering a distinct stakeholder question:

| Page | Question Answered |
|---|---|
| Executive Overview | How is the business performing overall, and are we growing? |
| Detailed Analysis | Where specifically is performance strong or weak — by region, product, and category? |

---

## Key Findings

### 1. The business grew 51.5% YoY — but margin tells a different story

Total sales hit **$12.6M** with a **51.5% year-on-year growth rate** — strong headline numbers. But profit margin sits at **11.6%**, with total profit at **$1.47M**.

The gap between revenue growth and margin tells a more nuanced story: volume is growing, but not all of that growth is equally profitable.

**Business implication:** Growth rate alone is not a sufficient success metric. Margin by product and region needs to be tracked alongside revenue to ensure expansion is sustainable.

---

### 2. High-revenue products are not always high-profit products

The scatter plot analysis (Sales vs Profit) surfaces a pattern common in retail: several products sitting in the top 10 by revenue are generating below-average profit margins.

This means the business may be prioritising and promoting the wrong products — optimising for revenue while quietly subsidising low-margin lines.

**Business implication:** Procurement, pricing, and promotional strategy should be driven by margin, not just sales volume. The scatter plot view makes this trade-off visible in seconds — something a standard sales report cannot do.

---

### 3. Central region leads sales — but regional comparison needs margin context

The Central region contributes the highest sales volume across all regions. However, without margin data broken down by region, high sales could still mask operational inefficiencies or discount-heavy selling.

**Business implication:** Regional targets should include a margin floor, not just a revenue target. A region hitting its sales number while running below-average margins is a problem that aggregate reporting won't catch.

---

## Analytical Decisions Worth Noting

| Decision | Rationale |
|---|---|
| Built a dedicated DateTable | Required for `SAMEPERIODLASTYEAR` to work correctly — without it, time intelligence measures silently return wrong results |
| Used `DISTINCTCOUNT` for order count | Prevents double-counting on multi-line orders — `COUNTROWS` would overstate volume |
| Used `DIVIDE` for all ratio measures | Prevents division-by-zero errors when slicers filter to segments with no data |
| Scatter plot for Sales vs Profit | The only visual type that shows the relationship between two continuous measures simultaneously — directly answers the "high revenue, low profit" question |
| Two-page structure | Separates executive summary (KPIs, trends) from analytical detail — different audiences, different needs |

---

## Skills Demonstrated

- **Data modelling** — DateTable creation, relationship definition, fact/dimension separation
- **Time intelligence DAX** — `SAMEPERIODLASTYEAR`, YoY % calculation with proper date context
- **Ratio measures** — Profit Margin and YoY % using `DIVIDE` for production-safe calculations
- **Multi-page report design** — structured around stakeholder questions
- **Scatter plot analysis** — surfacing the Sales vs Profit trade-off visually
- **Interactive slicers** — Year, Region, Category filtering across both pages

---

## Repository Contents

| File | Description |
|---|---|
| `dashboard/` | Power BI `.pbix` file and screenshots |
| `data/` | Source Excel dataset |
| `docs/` | Relationships diagram and measure reference |
| `README.md` | Project overview |
| `case-study.md` | This file — business narrative and analytical deep dive |

---

*Built by Anubhav Srivastava · [GitHub](https://github.com/asgeek96) · [LinkedIn](https://linkedin.com/in/asgeek)*
