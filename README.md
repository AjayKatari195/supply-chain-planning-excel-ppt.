# Supply Chain Planning: Demand Forecasting and Inventory Optimization

A simple end-to-end supply chain planning project built **only with Microsoft Excel and PowerPoint**.

A fictional electronics-accessories distributor sells 10 SKUs with different demand patterns, costs and supplier lead times. The project answers four planning questions: how much will we sell, how much buffer stock do we need, when should we reorder, and how much should we order?

## Files

| File | What it is |
|---|---|
| `Supply_Chain_Planning_Model.xlsx` | Formula-driven Excel model with a dashboard (631 live formulas) |
| `Supply_Chain_Planning_Presentation.pptx` | 8-slide deck presenting the method, results and recommendations |

## Excel workbook structure

| Sheet | Purpose |
|---|---|
| Dashboard | KPIs and four charts (demand vs forecast, stock vs reorder point, Pareto of value, safety stock) |
| Assumptions | Service level, ordering cost, holding cost rate. Change these and everything recalculates |
| SKU_Master | Unit cost, lead time, lead-time variability, current stock |
| Demand_History | 24 months of monthly demand per SKU (Oct-2024 to Sep-2026) |
| Forecast | 3-month moving-average forecast, MAPE and RMSE per SKU, next-month forecast |
| Inventory_Policy | Safety stock, reorder point, EOQ, reorder alert and suggested order quantity |
| ABC_Analysis | Pareto ranking and A/B/C classification |

Colour code: blue = input, black = formula, green = link to another sheet, yellow fill = key assumption.

## Methods

- **Forecast**: average of the previous 3 months. Accuracy measured with MAPE and RMSE.
- **Safety stock** = Z x SQRT(LeadTime x sigma_daily^2 + DailyDemand^2 x sigma_leadtime^2), with Z from the service level (95%).
- **Reorder point (ROP)** = DailyDemand x LeadTime + SafetyStock.
- **EOQ** = SQRT(2 x AnnualDemand x OrderingCost / (HoldingRate x UnitCost)).
- **Order policy**: when stock <= ROP, order up to ROP + EOQ.
- **ABC**: A = first 80% of annual value, B = next 15%, C = last 5%.

## Key results

- 86,643 units and about $966K of annual consumption value.
- Average forecast error (MAPE) of about 19%.
- 6 of 10 SKUs are at or below their reorder point and need a purchase order.
- 5 A-class SKUs account for about 83% of annual value.

## Skills demonstrated

Demand forecasting, inventory policy design, safety stock and EOQ modelling, ABC analysis, Excel formulas and charts, dashboard design, and presenting findings in PowerPoint.

## Data disclaimer

All data is **synthetic**. It was generated for this learning project using trend, seasonality and random noise. It is not real company data. Assumptions (ordering cost of $75 per order and a 20% annual holding cost) are illustrative.

## How to use

1. Open `Supply_Chain_Planning_Model.xlsx` and start on the Dashboard.
2. Change the yellow cells on the Assumptions sheet to see the policy update.
3. Open the PowerPoint to see the findings summarised.
