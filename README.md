# 📈 Sales and Shipping Cost Analysis in Tableau

## 🧾 Project Overview

This Tableau project analyzes sales performance and shipping costs using a global superstore dataset. It focuses on uncovering regional patterns, profit dynamics, and delivery efficiency through advanced calculations and interactive dashboards. The project is enhanced with powerful Tableau features such as:

- Level of Detail (LOD) expressions  
- Nested logical statements  
- Dynamic KPIs and user-controlled filters  
- Customized profit categorization  
- Advanced date manipulation

The goal is to present a visually intuitive and analytically rich dashboard that helps executives and analysts optimize sales strategies and logistics.

---

## 📂 File Structure

```
📁 sales_shipping_cost_analysis_in_tableau/
├── 📄 Sales & Shipping Cost Analysis in Tableau.twbx        # Tableau Workbook File
├── 📄 Sales and Shipping Cost Analysis in Tableau.pdf         # Dashboard Report Summary (PDF)
├── 📄 README.md                         # Project documentation (this file)
```

---

## 🎯 Key Features

### 📌 Sales vs. Shipping Cost Dashboard
- **Sales-to-Shipping Ratio by Region**
- **Monthly Sales Trends**
- **Top-Selling Categories and Sub-Categories**
- **Shipping Cost Overruns**
- **Dynamic Profit Indicator (colored by region)**

### 🧠 Insightful Questions Addressed
- Which regions suffer from high shipping costs relative to revenue?
- What are the most and least profitable product segments?
- Which months yield higher shipping cost per unit sold?

---

## 📊 Advanced Calculations

### 🔹 Profit Categorization (Custom Calculated Field)
```tableau
IF [Profit] > 0 THEN "Profitable"
ELSEIF [Profit] = 0 THEN "Break-even"
ELSE "Loss"
END
```

### 🔹 Shipping Cost Per Sale
```tableau
[Shipping Cost] / [Sales]
```

### 🔹 Conditional Formatting for KPIs
```tableau
IF [Profit Ratio] > 0.25 THEN "High Margin"
ELSEIF [Profit Ratio] > 0.10 THEN "Moderate Margin"
ELSE "Low Margin"
END
```

---

## 🔍 Level of Detail (LOD) Calculations

### 🔸 Fixed LOD – Average Shipping Cost per Region
```tableau
{ FIXED [Region] : AVG([Shipping Cost]) }
```

### 🔸 Include LOD – Profit per Category by State
```tableau
{ INCLUDE [State] : SUM([Profit]) }
```

### 🔸 Exclude LOD – Total Sales ignoring Segment
```tableau
{ EXCLUDE [Segment] : SUM([Sales]) }
```

These LODs enable deep-dive exploration of data independent of the dashboard filters, providing flexible aggregation.

---

## 📌 Filters & Interactivity
- Multi-select drop-downs for **Region**, **Category**, and **Year**
- **Date range slider** for monthly trend analysis
- Hover tooltips with dynamic metrics: *Sales, Profit, Quantity, Profit Ratio*
- **Dashboard action filters** to enable drill-down between charts

---

## 🧠 Analytical Takeaways

- The **West** region has the highest average shipping cost per order.
- **Technology** in the **Central** region consistently outperforms other segments.
- There is a spike in **shipping cost inefficiencies** during Q3 of each year.
- **High shipping costs** are often associated with **low-profit sub-categories** like *Tables*.

---

## 🚀 How to Open the Project

1. Open Tableau Desktop.
2. Load the file: `Sales & Shipping Cost Analysis in Tableau.twbx`
3. Explore the dashboard and adjust filters for deeper insights.

---

## 👩‍🎓 Author

**Aysegul Dahi**  
