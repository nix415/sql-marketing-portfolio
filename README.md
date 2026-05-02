# SQL Marketing Analytics Portfolio

Five self-contained **SQLite** analyses that mirror how marketing and growth teams answer questions with data: where demand concentrates, how segments move through a journey, who sticks around, what drives revenue mix, and how to prioritize customers for campaigns.

The work is built on a **customer segmentation** dataset (demographics, purchase behavior, and engagement scores). Each `.sql` file is documented with comments, executable queries, and a short **business takeaway** section so the intent reads clearly alongside the code.

---

## What this demonstrates

- Translating **marketing questions** into measurable SQL (acquisition mix, funnels, cohorts, ROI-style views, RFM).
- **CTEs**, conditional aggregation, **window functions** (`NTILE`), and multi-step logic readable by stakeholders.
- Working within **real-world constraints**: when a dataset does not include web logs or ad IDs, using **documented proxies** so the same analytical frameworks still apply.

---

## Tech stack

| Tool | Role |
|------|------|
| **SQLite** | Query engine |
| **DB Browser for SQLite** | Import CSV, run scripts |
| **GitHub** | Version control and portfolio presentation |

The repo also includes a small **static landing page** (`index.html`, `style.css`) you can publish with **GitHub Pages** if you want a visual entry point in addition to the SQL files.

---

## Analyses at a glance

| # | File | Business question | SQL techniques |
|---|------|-------------------|----------------|
| 1 | [`01_traffic_acquisition_analysis.sql`](01_traffic_acquisition_analysis.sql) | Where is “demand” concentrated if we treat category preference like a channel mix? | CTEs, `CROSS JOIN`, shares and `% of total`, `CASE` |
| 2 | [`02_funnel_conversion_analysis.sql`](02_funnel_conversion_analysis.sql) | How do defined stages compare, and where is the largest drop-off? | `SUM(CASE …)` funnel math, stage-to-stage rates |
| 3 | [`03_cohort_retention_analysis.sql`](03_cohort_retention_analysis.sql) | How do engagement and purchase metrics differ by **membership tenure** (cohort proxy)? | Tenure-based cohorts, cohort metrics, retention-style tables |
| 4 | [`04_revenue_campaign_roi.sql`](04_revenue_campaign_roi.sql) | Where do **revenue and AOV** concentrate by category and segment for budget allocation? | Channel-style rollups, `NTILE` / quartiles, revenue share, efficiency ratios |
| 5 | [`05_rfm_segmentation.sql`](05_rfm_segmentation.sql) | How do we segment customers for CRM or campaign targeting using RFM-style scoring? | `NTILE(3)`, composite scores, tiered `CASE` |

Open any numbered file in order; numbering matches a typical **acquisition → conversion → retention → value → segmentation** narrative.

---

## Dataset

**Customer Segmentation Data for Marketing Analysis** — synthetic **1,000-row** customer table (suitable for portfolio demos and interview walkthroughs).

| Column | Description |
|--------|-------------|
| `id` | Customer identifier |
| `age` | Age |
| `gender` | Gender |
| `income` | Annual income |
| `spending_score` | Engagement / spend propensity (0–100) |
| `membership_years` | Tenure since signup |
| `purchase_frequency` | Purchase count |
| `preferred_category` | Favorite product category |
| `last_purchase_amount` | Most recent order value |

---

## How to run the queries

1. Install [DB Browser for SQLite](https://sqlitebrowser.org/) (or any SQLite client you prefer).
2. Create a database and import your CSV as a single table named **`customers`** with the columns above.
3. Open any `0X_*.sql` file and execute the script from top to bottom.
4. Read the header comments for goals and the bottom sections for **interpretation** and next-step prompts.

---

## Note on field mapping (important for reviewers)

This dataset does not include raw **web analytics** fields (UTM parameters, session timestamps, impression logs). The analyses therefore use **explicit proxies** so the *shape* of the analysis matches marketing practice:

| Real-world concept | Proxy in this dataset |
|--------------------|------------------------|
| Acquisition / traffic source | `preferred_category` |
| Cohort / time dimension | `membership_years` (and similar groupings) |
| Funnel stages | Thresholds on `spending_score` and related fields |
| Campaign or offer tiers | Income quartiles / bands |

That mapping is **called out in the SQL comments** so nothing is presented as fake clickstream data. The goal is to show you can **adapt standard marketing analytics patterns** to the columns you actually have — a common requirement in startup and mid-market analytics roles.

---

## Repository layout

```
01_traffic_acquisition_analysis.sql
02_funnel_conversion_analysis.sql
03_cohort_retention_analysis.sql
04_revenue_campaign_roi.sql
05_rfm_segmentation.sql
index.html              # Optional GitHub Pages front door
style.css
README.md
```

---

## Next steps (optional)

- Point the hero **Tableau** button in `index.html` to a real **Tableau Public** URL when you have one.
- Enable **GitHub Pages** on this repo if you want recruiters to land on the HTML overview before diving into SQL.

---

**Maintainer:** [@nix415](https://github.com/nix415)
