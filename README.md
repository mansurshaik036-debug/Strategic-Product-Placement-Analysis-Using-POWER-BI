# Strategic Product Placement Analysis — Power BI Dashboard

> **Executive-level business intelligence dashboard** built for a 1,000-observation product placement dataset. Designed for recruiters at Microsoft, Amazon, Swiggy, Zomato, Uber Eats, Deloitte, EY, PwC, and Accenture.

![Dashboard Preview](assets/dashboard-preview.png)

---

## Dashboard Preview
<img width="3503" height="2179" alt="dashboard-preview-hd" src="https://github.com/user-attachments/assets/82204472-2a99-4c48-87ec-ae4412c75e1b" />


The dashboard features a **clean, minimal dark executive theme** with 5 interactive pages:

| Page | Purpose | Key Visuals |
|------|---------|-------------|
| **Overview** | At-a-glance performance | 6 KPI cards, category bars, placement funnel, scatter plot |
| **Placement** | Location strategy | Heatmap matrix, efficiency funnel, recommendations |
| **Products** | SKU-level analysis | Top 10 table, price spread, seasonal impact, alerts |
| **Customers** | Demographic insights | Sales funnel, category heatmap, targeting strategy |
| **Actions** | Priority recommendations | 10 insight cards, visual mapping, DAX reference |

---

## Business Problem

Retail leaders need to answer:
- How is the business performing?
- Which product placements drive the most revenue?
- Which categories and demographics are most valuable?
- Where should we allocate inventory and marketing budget?

---

## Dataset Overview

| Attribute | Details |
|-----------|---------|
| Records | 1,000 product-placement observations |
| Source Fields | 10 (Product ID, Position, Price, Competitor Price, Promotion, Foot Traffic, Demographics, Category, Seasonal, Sales Volume) |
| Derived Fields | 6 (Sales Amount, Price Spread, Estimated Profit, Profit Margin, Price Position, Outlier Flag) |
| Total Sales | Rs.50,007,530 |
| Estimated Profit | Rs.4,343,015 |
| Profit Margin | 8.7% |

---

## Key Insights

| # | Insight | Impact |
|---|---------|--------|
| 1 | End-cap placements outperform by 6.4% | Rs.17.42M revenue |
| 2 | Clothing is the top category | Rs.17.31M sales |
| 3 | Electronics underperforms — needs review | Rs.16.34M (lowest) |
| 4 | Promotions show minimal sales lift | Rs.24.55M vs Rs.25.46M non-promoted |
| 5 | College students drive 25.7% of revenue | Rs.12.86M |
| 6 | Product 115581 is the top performer | Rs.241K sales, Rs.17.7K profit |
| 7 | Product 176976 has 0% margin at Rs.198K sales | Immediate repricing needed |

---

## Tech Stack

- **Power BI Desktop** — Data modeling, DAX, visual design
- **Power Query** — Data cleaning, derived columns, outlier flagging (IQR method)
- **DAX** — Custom measures for KPIs, rankings, and comparative analysis
- **UX Design** — Dark executive theme, color-coded severity, interactive drill-down

---

## DAX Measures (Sample)

```dax
Total Sales = SUM('Data'[Sales Amount])

Estimated Profit = SUM('Data'[Estimated Profit])

Profit Margin = DIVIDE([Estimated Profit], [Total Sales], 0)

Avg Order Value = AVERAGE('Data'[Sales Amount])

Price Spread = SUM('Data'[Price]) - SUM('Data'[Competitor Price])

Price Position = IF([Price Spread] > 0, "Premium", "Discount")

Top Product = TOPN(1, ALL('Data'), [Total Sales], DESC)
```

---

## File Structure

```
product-placement-powerbi/
├── README.md                          # This file
├── data/
│   └── Product_Positioning.csv        # Source dataset
├── powerbi/
│   ├── dashboard-design.md            # Visual spec & layout guide
│   ├── dax-measures.dax              # All reusable DAX measures
│   └── slicer-config.md              # Slicer and filter setup
├── assets/
│   └── dashboard-preview.png         # Screenshot of final dashboard
├── docs/
│   ├── business-insights.md          # 10 actionable insights
│   ├── data-cleaning-report.md       # EDA & cleaning documentation
│   └── executive-summary.md          # One-page summary for stakeholders
└── .gitignore
```

---

## How to Use

1. Open `Product_Positioning.csv` in Power BI Desktop
2. Import DAX measures from `powerbi/dax-measures.dax`
3. Build visuals per `powerbi/dashboard-design.md`
4. Configure slicers per `powerbi/slicer-config.md`
5. Publish to Power BI Service for sharing

---

## Author

**SHAIK.MANSUR**

Built for portfolio demonstration and recruiter evaluation.

---

*Report generated: 3 July 2026 | Dataset: 1,000 observations across 10 source fields*
