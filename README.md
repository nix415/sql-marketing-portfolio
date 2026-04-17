# SQL Marketing Analytics Portfolio

Five SQL analyses built on the **Customer Segmentation Data for Marketing Analysis** dataset, designed to demonstrate skills relevant to growth marketing and marketing analysis roles.

<!-- TODO: Uncomment and update these links after deploying -->
<!-- **[Live Site](https://YOUR_GITHUB_USERNAME.github.io/sql-marketing-portfolio/)** · **[Tableau Dashboard](PASTE_YOUR_TABLEAU_PUBLIC_URL_HERE)** -->

## Dataset

| Column | Description |
|---|---|
| `id` | Unique customer identifier |
| `age` | Customer age |
| `gender` | Customer gender |
| `income` | Annual income |
| `spending_score` | Engagement/spending propensity (0-100) |
| `membership_years` | Years since signup |
| `purchase_frequency` | Number of purchases |
| `preferred_category` | Favorite product category |
| `last_purchase_amount` | Most recent order value |

**Tool:** SQLite via DB Browser for SQLite

## Analyses

| # | File | Analysis | Key SQL Concepts |
|---|---|---|---|
| 1 | `01_traffic_acquisition_analysis.sql` | Traffic & Acquisition | CTEs, CROSS JOIN, percentage calculations, CASE |
| 2 | `02_funnel_conversion_analysis.sql` | Funnel Conversion | Conditional aggregation, multi-stage SUM/CASE, drop-off rates |
| 3 | `03_cohort_retention_analysis.sql` | Cohort Retention | Cohort grouping, retention rate calculation, cross-tabs |
| 4 | `04_revenue_campaign_roi.sql` | Revenue & Campaign ROI | NTILE window function, revenue share, efficiency metrics |
| 5 | `05_rfm_segmentation.sql` | RFM Segmentation | NTILE(3), composite scoring, tiered CASE logic |

## How to Run

1. Open DB Browser for SQLite
2. Import your CSV as a table named `customers`
3. Open any `.sql` file and execute the queries
4. Each file is self-contained with comments and a business insight summary

## Note on Column Mapping

Since this dataset doesn't include traditional web analytics fields (UTM source, session events, timestamps), several analyses use creative proxies:

- **preferred_category** serves as the "acquisition channel"
- **membership_years** serves as the cohort/recency dimension
- **spending_score thresholds** model funnel stages
- **income quartiles** simulate campaign-tier targeting

This approach demonstrates the ability to apply marketing analytics frameworks to any dataset — a core skill for growth roles.
