# Inventory Optimization EDA Project

**Objective:**  
Perform an **Exploratory Data Analysis (EDA)** to uncover key insights for **inventory optimization**, including stock level patterns, stockouts, ABC classification, reorder point performance, and demand variability.  

---

## Project Highlights
✔ **Dataset:** Synthetic but realistic 2-year inventory dataset for 10 SKUs across 3 warehouses (seasonality, lead times, reorder behavior).  
✔ **Tools Used:** Python (**pandas**, **matplotlib**).  
✔ **Techniques Applied:**  
- Data Cleaning & Preprocessing  
- **ABC Analysis** (classification into A/B/C SKUs)  
- Stockout & Unmet Demand Analysis  
- Lead Time Variability & Safety Stock Evaluation  
- Inventory Turnover Calculation  
- Reorder Point Performance Check  
✔ **Visualizations:**  
- Time Series of Daily Sales  
- Inventory Levels vs Sales Scatter  
- SKU-level Boxplots for Sales Distribution  
- Histogram of Lead Times  
- Stockout Bar Charts  

---

## Key Findings & Insights
- **A-class SKUs drive majority of sales** → tighter control needed.  
- **High unmet demand** for certain SKUs → revise safety stock and lead-time assumptions.  
- **Reorder point violations** frequent → recalculate ROP using empirical lead time and demand variance.  
- **Demand variability (CV) high** for some SKUs → adopt dynamic safety stock policies.  

---

## Recommendations
1. Prioritize A-class SKUs for frequent review and better supplier coordination.  
2. Increase safety stock for high CV items and those with long lead times.  
3. Monitor fill rate KPIs (target ≥95% for A items) to minimize stockouts.  

---

### Repository Structure
```
📂 inventory-optimization-eda
 ├── inventory_data.csv           # Dataset (synthetic, realistic)
 ├── inventory_report.md          # Detailed report with insights & recommendations
 ├── inventory_eda_outputs.png    # Visual summary of key plots
 ├── inventory_summary.md         # Technical analysis summary
 ├── README.md                    # Portfolio-ready summary
 └── eda_code.ipynb               # Jupyter notebook with code & outputs
```

---

