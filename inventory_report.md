# Inventory Optimization — Detailed Report

**Project goal:** Produce an exploratory data analysis focused on inventory optimization decisions: SKU priorities (ABC), stockouts/unmet demand, reorder point performance, demand variability, and actionable recommendations.


## Key dataset facts

- Rows: 21,930
- Date range: 2023-01-01 to 2024-12-31
- SKUs: 10
- Stores: ['WH_Main', 'WH_East', 'WH_West']


## Top Findings (summary)

1. ABC classification: A SKUs (top contributors to sales): .

2. Total unmet demand across dataset: 65829 units — these are instances where demand exceeded available stock (stockouts / lost-sales). Priority should be given to SKUs with highest unmet units to reduce lost sales.

3. Reorder point violations (top items):

   - SKU_007: 875 days where on_hand < reorder_point

   - SKU_004: 872 days where on_hand < reorder_point

   - SKU_003: 856 days where on_hand < reorder_point

   - SKU_008: 845 days where on_hand < reorder_point

   - SKU_006: 804 days where on_hand < reorder_point



## Detailed analysis and charts

- Time-series of total daily sales shows clear seasonality and occasional spikes — plan safety stock around peak periods.

- Several SKUs show high coefficient of variation (CV) in demand — for those, consider higher safety stock or vendor-managed inventory.

- Lead times vary by SKU; items with long and variable lead times are high-risk for stockouts and should have higher reorder points.


## Recommendations (operational)

1. **ABC-focused policy:** Put A items on tighter review (review cycle daily or weekly), maintain more frequent replenishment, and consider vendor agreements for lead-time reductions. Move C items to less frequent review.

2. **Recalculate Reorder Points:** Use empirical lead time and demand variance per SKU to compute reorder points (ROP = demand during lead time + safety stock). Our simple simulated ROP still results in violations — recalculate using observed demand & lead-time distribution.

3. **Safety Stock for Variable Demand:** For SKUs with high CV, increase safety stock using higher service factor (z) or consider targeted promotions to smooth demand.

4. **Address Unmet Demand:** Investigate supply chain bottlenecks for SKUs with highest unmet units — possible remedies: expedited orders, safety stock, alternative suppliers, or substitution.

5. **Measure fill-rate & lost-sales:** Start tracking on a daily basis and set KPIs (e.g., 95% fill rate for A items).


## Appendices: Technical details

- All analysis performed using pandas and matplotlib; dataset generated synthetically to represent realistic inventory dynamics.

- Dataset file saved as: `/mnt/data/inventory_data.csv`

- Quick EDA visual summary saved as: `/mnt/data/inventory_eda_outputs.png`

