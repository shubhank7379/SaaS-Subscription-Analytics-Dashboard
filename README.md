# SaaS Subscription Analytics & Dashboard

## Project Overview

This project simulates a real-world data analytics workflow for a subscription-based SaaS business. The goal was to build a complete analytics pipeline — from raw data generation to a business-ready interactive dashboard — that helps stakeholders answer critical business questions:

- How is Monthly Recurring Revenue (MRR) trending over time?
- Which customer segments are most valuable and which are at risk of churning?
- What is the retention rate of customers acquired in different months?
- How does churn vary across company sizes and subscription plans?

The project covers the full analytics stack: **SQL** for structured querying, **Python** for data processing and segmentation, and **Power BI** for interactive visualization — making it a complete end-to-end portfolio piece that mirrors how data analysts work in real SaaS companies.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python (Pandas, Matplotlib, Seaborn) | Data cleaning, EDA, cohort analysis, RFM segmentation |
| SQL (MYSQL) | Schema design, revenue queries, churn and retention analysis |
| Power BI + DAX | Interactive 2-page business dashboard |

---

## Dataset

A synthetic dataset was generated using `generate_dataset.py` simulating 1,000+ SaaS customers across multiple subscription plans (Basic, Pro, Enterprise), industries, company sizes, and countries. The dataset includes:

- **customers_clean.csv** — Customer profiles with signup date, industry, company size, country
- **subscriptions_clean.csv** — Subscription records with plan, monthly price, status, start and end dates
- **payments_clean.csv** — Payment transactions with amount, method, and status
- **usage_clean.csv** — Feature-level product usage data per customer
- **rfm_segments.csv** — RFM scores and segment labels computed in Python

---

## Project Structure

```
saas-analytics-portfolio/
├── data/
│   ├── raw/
│   └── cleaned/
│       ├── customers_clean.csv
│       ├── subscriptions_clean.csv
│       ├── payments_clean.csv
│       ├── usage_clean.csv
│       └── rfm_segments.csv
├── sql/
│   ├── 01_schema_setup.sql
│   ├── 02_data_exploration.sql
│   ├── 03_mrr_analysis.sql
│   ├── 04_cohort_retention.sql
│   └── 05_churn_analysis.sql
├── python/
│   ├── 01_data_cleaning.py
│   ├── 02_eda.ipynb
│   ├── 03_cohort_analysis.ipynb
│   └── 04_rfm_segmentation.ipynb
├── images/
├── generate_dataset.py
└── README.md
```

---

## Phase 1 — SQL Analysis

Designed a normalized relational schema and wrote analytical queries to answer business questions directly from the database.

- **Schema setup** — Created 4 relational tables with primary and foreign key constraints
- **Data exploration** — Revenue breakdown by plan, country, and company size
- **MRR analysis** — Calculated Monthly Recurring Revenue and tracked growth over time
- **Cohort retention** — Measured what percentage of customers from each signup cohort remained active in subsequent months
- **Churn analysis** — Identified churn rate by plan type and company size to find the highest-risk segments

---

## Phase 2 — Python Analysis

### Data Cleaning
- Handled null values in `end_date` column (72% nulls — valid for active subscriptions)
- Fixed data type issues in `amount` column caused by header row misidentification
- Converted `cohort_month` and `payment_month` from full datetime to `YYYY-MM` text format for proper monthly grouping

### Exploratory Data Analysis
Generated 10+ visualizations including MRR trend, plan distribution, churn by company size, signup trend, and revenue by country.

### Cohort Retention Analysis
Tracked the percentage of customers acquired each month who remained active in months 1, 2, 3, and beyond. Found that months 2–4 represent the highest churn risk window.

### RFM Segmentation
Scored customers on Recency, Frequency, and Monetary value to classify them into actionable segments:

| Segment | Description |
|---------|------------|
| Champions | Bought recently, buy often, high spenders |
| Loyal | Regular buyers with good monetary value |
| Promising | Recent customers with growth potential |
| At Risk | Previously active but showing disengagement |
| Lost | Long inactive, low engagement |

---

## Phase 3 — Power BI Dashboard

Built a 2-page interactive dashboard with cross-page slicers, drill-through, conditional formatting, and DAX measures.

### Page 1 — Executive Overview
Designed for business leaders to monitor top-level performance at a glance.

- **KPI Cards** — MRR, Active Customers, ARPU, Churn Rate with color-coded values
- **MRR Trend** — Line chart showing monthly revenue movement
- **Revenue by Plan** — Donut chart breaking down revenue across Basic, Pro, Enterprise
- **Churn by Company Size** — Column chart comparing churn rates across Small, Medium, Enterprise customers
- **Monthly Signups** — Bar chart tracking new customer acquisition by month

### Page 2 — Customer Analytics
Designed for deeper customer behavior analysis.

- **Cohort Retention Heatmap** — Matrix visual with green-to-red conditional formatting showing retention drop-off by cohort
- **RFM Segment Distribution** — Bar chart showing count of customers per segment
- **At-Risk Customer Table** — Drill-through table listing customers by segment, plan, and revenue
- **CLV by Company Size** — Column chart comparing average customer lifetime value across company sizes

### DAX Measures Created
- `MRR` — Sum of monthly subscription prices
- `Active_Customers` — Distinct count of customers with active status
- `ARPU` — MRR divided by Active Customers
- `Churn_Rate` — Ratio of cancelled to total subscriptions
- `Champions`, `At_Risk` — Segment-specific customer counts
- `Avg_CLV` — Average monetary value from RFM data

---

## Key Business Insights

- Small companies churn at **3.5x higher rate** than enterprise customers — retention efforts should prioritize enterprise accounts
- The critical retention window is **months 2–4** — highest customer drop-off happens here, suggesting a need for stronger onboarding
- Enterprise plan customers generate significantly higher CLV despite being fewer in number
- Champions and Loyal segments together drive the majority of total revenue

---

## Dashboard Preview

<p align="center">
  <img src="saas dasboard.png" width="500" alt="Dashboard Screenshot">
</p>


---
## Connect

**LinkedIn:** your-  www.linkedin.com/in/shubhank7379
**Email:** your-shubhankarsrivastava1122@gmail.com
