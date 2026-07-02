# Financial Statement Analysis Dashboard (Power BI)

A 5-page interactive Power BI dashboard that analyzes multi-company financial performance
across the income statement, balance sheet, and cash flow statement — built to surface
revenue trends, profitability, balance sheet health, and cash flow patterns for
comparative, stakeholder-level reporting.

## Files in this project

| File | Description |
|---|---|
| `project.pbix` | The Power BI data model + report (open in Power BI Desktop). |
| `financial_statements_sample.csv` | Sample data matching the dashboard's real schema (see note below). |
| `README.md` | This file. |

> **Note on the sample CSV:** The `.pbix` data model stores its rows in a compressed,
> proprietary format that can't be exported without Power BI Desktop / an OLAP tool.
> `financial_statements_sample.csv` therefore contains **illustrative sample data**
> shaped exactly like the dashboard's real schema (same tables/columns), so you can test
> queries, load it into other tools, or use it as a template — it is **not** the original
> dataset behind the published dashboard.

## Dashboard Structure (5 pages)

1. **Total Revenue — Annually & Quarterly / Company-Level Financial Insights**
   Revenue trend by company, annual vs. quarterly comparison.
2. **Income Statement Focus / Company with Loss**
   Net income and loss-making companies, income statement drill-down.
3. **Cash Flow Analysis**
   Operating, investing, and financing cash flows; free cash flow (FCF) status by company.
4. **Balance-Sheet Evaluation / Declining Assets Base**
   Total assets, liabilities, and companies with a shrinking asset base over time.
5. **Consolidated Report — Comparative & KPI Analysis / Consistent Growth Analysis**
   Cross-company KPI comparison and consistent-growth identification.

Visual types used across the report include scatter, waterfall, funnel, treemap, ribbon,
combo charts, KPI cards, and pivot tables (25+ visuals total).

## Data Schema

The report pulls from four underlying tables (all keyed by `stock`, the company ticker):

### `incomeStatementHistory_annually`
| Column | Description |
|---|---|
| stock | Company ticker |
| endDate | Fiscal year end date |
| totalRevenue | Total revenue |
| costOfRevenue | Cost of revenue (COGS) |
| grossProfit | Gross profit |
| operatingIncome | Operating income |
| totalOperatingExpenses | Total operating expenses |
| netIncome | Net income |

### `incomeStatementHistory_quarterly`
| Column | Description |
|---|---|
| stock | Company ticker |
| totalRevenue | Quarterly revenue |
| netIncome | Quarterly net income |

### `balanceSheetHistory_annually`
| Column | Description |
|---|---|
| stock | Company ticker |
| endDate | Fiscal year end date |
| totalAssets | Total assets |
| totalCurrentAssets | Total current assets |
| totalLiab | Total liabilities |
| totalCurrentLiabilities | Total current liabilities |
| cash | Cash and equivalents |
| retainedEarnings | Retained earnings |

### `cashflowStatement_annually`
| Column | Description |
|---|---|
| stock | Company ticker |
| capitalExpenditures | CAPEX |
| totalCashFromOperatingActivities | Operating cash flow |
| totalCashFromFinancingActivities | Financing cash flow |
| totalCashflowsFromInvestingActivities | Investing cash flow |
| FCF Status | Free cash flow status (Positive / Negative) |

## How to Use

1. Open `project.pbix` in Power BI Desktop to explore the live report.
2. Use `financial_statements_sample.csv` as a schema-accurate starting point if you want
   to rebuild the data model with your own source data (e.g., via a financial data API),
   or to test transformations before loading into Power Query.
3. Replace the sample data with your real source (e.g., company 10-K/10-Q filings or a
   financial data provider) and refresh the model to reproduce the dashboard with live data.

## Tech Stack

Power BI Desktop · Power Query (ETL) · DAX-based measures · Multi-page interactive reporting
