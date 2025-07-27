 📊 Sales & Shipping Cost Analysis in Tableau

## 🧾 Overview

This Tableau project explores the relationships between sales, discounts, profit margins, and shipping costs using US Superstore data. By leveraging data storytelling and interactive dashboards, it identifies key patterns across product categories and regions, enabling data-driven business decisions.

---

## 🎯 Project Goals

- Investigate whether higher discounts actually drive profit or cause losses.
- Uncover which categories and states are consistently underperforming.
- Measure how shipping cost contributes to reduced profitability across states.
- Forecast future profit trends across different shipping modes.
- Support strategic planning through rich interactivity and insights.

---

## 📂 Dataset Summary

- **Primary Source**: US Superstore Dataset  
- **Metrics**: Sales, Profit, Discount, Quantity, Shipping Cost, Category, Region, Segment, Order Date, Ship Date  
- **Preprocessing**:  
  - Missing values in "Product Base Margin" were filled with the **median**.  
  - Outliers in profit were treated using the **Interquartile Range (IQR)** method.  
  - Date parsing and column normalization were handled in Tableau and Python (Pandas).

---

## ⚙️ Tableau Features & Techniques

### 🔧 Calculated Fields

- **Profit Ratio**:  
  ```tableau
  [Profit] / [Sales]
  ```
- **Shipping Cost per Order**:  
  ```tableau
  [Shipping Cost] / [Order ID]
  ```
- **Profit Margin**:  
  ```tableau
  ([Sales] - [Shipping Cost]) / [Sales]
  ```

### 📌 Level of Detail (LOD) Expressions

- **State-Level Avg Shipping Cost**:  
  ```tableau
  { FIXED [State] : AVG([Shipping Cost]) }
  ```
- **Category-Level Profit**:  
  ```tableau
  { FIXED [Category] : SUM([Profit]) }
  ```
- **Customer Order Count**:  
  ```tableau
  { FIXED [Customer ID] : COUNTD([Order ID]) }
  ```

These LOD expressions allow aggregations at specific dimensions, even when the visualizations operate at a lower or higher granularity.

---

## 📈 Key Visualizations

- **Stacked Bar Charts**: Compare sales from high vs. low discount orders across categories.
- **Scatter Plots**: Examine how discounts affect sales and profit at sub-category level.
- **Pareto Chart**: Visualize top sub-categories contributing to 80% of sales.
- **Trend Line with Forecast**: Predict profit and shipping cost evolution over time.
- **Interactive Map**: Show state-wise profit margins and shipping costs with color and size encoding.
- **Box Plot**: Distribution of profit margins across different regions.
- **Dynamic Parameters**:  
  - Toggle between Sales vs. Profit  
  - Select discount range  
  - Filter categories and regions

---

## 💡 Dashboard Interactivity

- **Action Filters**: Clicking on a region or sub-category filters other charts dynamically.
- **Highlight Actions**: Hovering highlights trends across charts.
- **Story Mode**: Walks the user through insights step-by-step.
- **Parameter Controls**: Allow users to adjust thresholds and see changes live.

---

## 📁 Files in this Repository

| File Name                                   | Description                                  |
|--------------------------------------------|----------------------------------------------|
| `Sales and Shipping Cost Analysis.twbx`     | Tableau workbook with full dashboards        |
| `Sales and Shipping Cost Analysis.pdf`      | Exported presentation version of the project |
| `README.md`                                 | Project documentation                        |

---

## 🔍 Insights & Takeaways

- Excessive discounting often **lowers profit**, especially in the Technology category.
- High shipping costs **correlate with negative profit** in certain states.
- Sub-categories like Tables and Bookcases are **consistently unprofitable**.
- Using **forecasting**, we anticipate further margin pressure if trends continue.

---

## 👩‍💻 Author

**Aysegul Dahi**  
[LinkedIn](https://linkedin.com/in/ayseguldahi)

---

## 📌 Tools

- Tableau  
- Python (Pandas, Seaborn for initial prep)  
- Excel (for dataset validation)
