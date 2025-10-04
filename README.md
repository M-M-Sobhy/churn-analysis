# 🍕 Pizza Sales Report — Analytics Dashboard

A clean, interactive **Pizza Sales** analytics dashboard that surfaces best/worst sellers, KPIs, and trends for a full year (Jan–Dec 2015). This repo contains the source files and reproducible steps to rebuild the dashboard from scratch.

> **Tech stack:** Power BI (or Power BI Desktop), CSV dataset(s) and DAX measures.  
> **Use-cases:** retail sales analysis, product mix optimization, pricing/discount strategy, operations planning.

---

## 📸 Preview



<p align="center">
  <img src="Best-worst sellers.jpeg" alt="Overview Dashboard" width="800">
</p>

<p align="center">
  <img src="Best-worst sellers.jpeg" alt="Overview Dashboard" width="800">
</p>
---

## ✨ Key Features

- **Executive KPIs** at a glance:
  - **Avg Order Value** (AOV)
  - **Total Orders**
  - **Total Pizzas Sold**
  - **Sum of Total Revenue**
  - **Avg Pizzas per Order**
- **Top & Bottom 5** pizzas by:
  - **Total Orders**
  - **Quantity**
  - **Revenue**
- **Best/Worst Sellers** quick-read cards
- **Global slicers/filters:** **Date range** and **Pizza Category**
- **Responsive layout** optimized for widescreen monitors

---

## 🧠 KPIs & DAX (example measures)

Below are representative DAX measures you can drop into the model. Names may be adapted to your table/column schema.

```DAX
-- Base measures
Total Revenue = SUM ( Sales[Revenue] )
Total Orders  = DISTINCTCOUNT ( Sales[OrderID] )
Total Pizzas  = SUM ( Sales[Quantity] )

-- Derived KPIs
Avg Order Value = DIVIDE ( [Total Revenue], [Total Orders] )
Avg Pizzas per Order = DIVIDE ( [Total Pizzas], [Total Orders] )

-- Optional helpers (for Top/Bottom visuals)
Revenue by Pizza = [Total Revenue]          -- used in bar charts by Pizza[Name]
Orders by Pizza  = [Total Orders]
Qty by Pizza     = [Total Pizzas]
