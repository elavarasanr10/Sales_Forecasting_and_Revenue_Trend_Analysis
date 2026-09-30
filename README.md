# Sales Forecasting & Revenue Trend Analysis

## Objective
Analyze 24 months of sales data for a fictional FMCG company (BrightCart Consumer Goods) to measure forecast accuracy, identify revenue trends, and produce a 6-month statistical forecast with scenarios, supporting decisions on marketing allocation, regional targets, and inventory planning.

## Business Problem
Actual revenue regularly differs from the company's forecast, but no one had measured how much, where, or why. This project quantifies the gap and identifies its root causes. See `01_Business_Problem_Statement.docx` for the full stakeholder and scope breakdown.

## Dataset
100 order-level records (Jan 2024 – Dec 2025) across 3 regions, 5 product categories, and 5 sales representatives, with 25 columns including revenue, cost, profit, marketing spend, forecasted revenue, and sales targets. Fictional data, built to reflect realistic FMCG patterns (seasonality, regional growth divergence).

File: `sales_forecasting_processed.xlsx`

## Forecasting Framework
Backtested three approaches by training on 2024 and testing against actual 2025 results:

| Model | Accuracy | Bias |
|---|---|---|
| Company's existing forecast | 94.8% | −4.6% |
| Linear trend model | 69.3% | +19.4% |
| Seasonal decomposition model | 78.6% | −21.4% |

The existing forecast outperformed both statistical models, most likely because two years of history is too little to reliably estimate trend and seasonality on its own. Recommendation: keep the current process, correct its known biases with targeted adjustment factors, and revisit a statistical model once more history accumulates.

File: `forecasting_summary.xlsx` (Historical Data / Forecast Model / Metrics & Regional tabs)

## Analysis Performed
- Revenue trend and YoY growth analysis
- Regional performance and variance analysis (South Asia, Middle East, Southeast Asia)
- Product category and profitability analysis
- Seasonal demand pattern analysis (seasonal indices by calendar month)
- Forecast accuracy and bias analysis (full period and holdout backtest)
- 6-month forward forecast (Jan–Jun 2026) with best/base/worst case scenarios
- Root cause analysis of forecast gaps (five-whys, cause categorization) — see `06_Root_Cause_Analysis.docx`

## Dashboard
`dashboard.html` — interactive, filterable dashboard (year, region, category, season) with KPI cards, revenue trend vs. forecast, 6-month forecast with scenario range, regional and category breakdowns, model comparison, and a recommendations snapshot. Open directly in any browser, or host via GitHub Pages.

## Key Insights
- Total revenue across 24 months: ₹1,21,71,830 against a company forecast of ₹1,17,54,000 (+3.5%)
- Festive season (Oct–Dec) is systematically under-forecast, with actual revenue beating plan by 2–16% each of those months across both years
- Southeast Asia is the fastest-growing region (+43.6% YoY); Middle East is the slowest (+11.2% YoY) and the only region where the forecast overshoots actuals (−7.4% variance)
- Profit margins are consistent across regions (32–33%), so growth differences are demand-driven, not pricing-driven

## Recommendations
See `07_Recommendations_Memo.docx` for full detail, effort/risk/priority ratings, and the executive summary. In brief:
1. Track monthly forecast accuracy and bias by region and product
2. Apply festive-season and Middle-East-specific adjustment factors to the existing forecast
3. Commission a market-level review of Middle East demand
4. Hold off on replacing judgment-based forecasting with a purely statistical model until more history exists
5. Test reallocating a share of Middle East marketing spend to Southeast Asia

## Conclusion
This project's most useful output isn't a new forecasting model — it's a validated, honest answer to "should we trust our current forecast, and where does it break." The current process is more accurate than the alternatives tested here, and the highest-value next step is a monitoring habit, not new technology.

## Tools Used
Python (data processing, forecasting math, backtesting), Excel/Google Sheets (final tabular deliverables), HTML/JavaScript/Chart.js (dashboard), AI-assisted drafting and analysis throughout (Claude).

## Files in This Repository
| File | Description |
|---|---|
| `01_Business_Problem_Statement.docx` | Stakeholders, decisions, scope, success criteria |
| `02_Requirements_and_KPI_Dictionary.docx` | User stories, functional requirements, KPI definitions |
| `03_Current_State_Process.png` | Flowchart of the existing forecasting process |
| `04_Future_State_Process.png` | Flowchart of the recommended future process |
| `05_Data_Quality_Validation_Log.docx` | Data checks performed and results |
| `06_Root_Cause_Analysis.docx` | Five-whys analysis for the three key findings |
| `07_Recommendations_Memo.docx` | Prioritized recommendations + executive summary |
| `08_Resume_Bullets_and_Project_Descriptions.docx` | Resume-ready project descriptions |
| `09_LinkedIn_Content.docx` | Three-post LinkedIn content plan with captions and hashtags |
| `sales_forecasting_processed.xlsx` | Full 100-row dataset with all calculated fields |
| `forecasting_summary.xlsx` | Historical data, forecast model, metrics & regional breakdown |
| `dashboard.html` | Interactive dashboard |
| `README.md` | This file |
