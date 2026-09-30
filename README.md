# SaaS Subscription Analytics & Dashboard

An end-to-end data analytics portfolio project analyzing subscription-based SaaS business metrics including revenue trends, customer retention, and churn behavior.

---

## Tech Stack

- **Python** — Data cleaning, EDA, cohort analysis, RFM segmentation
- **SQL** — Schema design, MRR calculation, churn and retention queries
- **Power BI** — Interactive 2-page business dashboard

---

## Project Structure

```
saas-analytics-portfolio/
├── data/
│   ├── raw/                        # Raw generated dataset
│   └── cleaned/                    # Cleaned CSV files
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
├── images/                         # All exported visualizations
├── generate_dataset.py             # Synthetic dataset generator
└── README.md
```

---

## What This Project Covers

### Phase 1 — SQL Analysis
- Designed a normalized relational schema with 4 tables
- Wrote queries for MRR calculation, cohort retention, and churn analysis
- Explored revenue breakdown by plan, country, and company size

### Phase 2 — Python Analysis
- Cleaned and processed raw data using **Pandas** — handled nulls, type conversions, and date formatting
- Performed EDA with **Matplotlib** and **Seaborn** generating 10+ visualizations
- Built **cohort retention analysis** to track customer retention month over month
- Implemented **RFM segmentation** to classify customers into Champions, Loyal, Promising, At-Risk, and Lost segments

### Phase 3 — Power BI Dashboard
Built a 2-page interactive dashboard with slicers, drill-through, and conditional formatting.

**Page 1 — Executive Overview**
- KPI cards: MRR, Active Customers, ARPU, Churn Rate
- MRR trend line chart by month
- Revenue by plan donut chart
- Churn rate by company size
- Monthly customer signups

**Page 2 — Customer Analytics**
- Cohort retention heatmap (Matrix with conditional formatting)
- RFM segment distribution bar chart
- At-risk customer detail table
- CLV by company size

---

## Key Insights

- Small companies churn at **3.5x higher rate** than enterprise customers
- Month 2–4 is the critical retention window — highest customer drop-off occurs here
- Enterprise plan contributes disproportionately higher CLV despite lower customer count
- Champions and Loyal segments together account for over 50% of total revenue

---

## Dashboard Preview

> *(Add screenshot of your Power BI dashboard here)*

---

## How to Run

**Generate Dataset:**
```bash
python generate_dataset.py
```

**Run Python Analysis:**
```bash
pip install pandas numpy matplotlib seaborn jupyter openpyxl
jupyter notebook python/02_eda.ipynb
```

**SQL Setup:**
- Run `sql/01_schema_setup.sql` first to create tables
- Then run remaining SQL files in order

**Power BI:**
- Open the `.pbix` file in Power BI Desktop
- Data is loaded from `data/cleaned/` folder

---

## Connect

**LinkedIn:** your-linkedin-url  
**Email:** your-email@gmail.com
