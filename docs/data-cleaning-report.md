# Data Cleaning & EDA Report

## Dataset Structure
- **Records**: 1,000 observations + 1 header row
- **Source Columns**: 10
- **Derived Columns**: 6 (added in columns K:P)
- **Numeric Fields**: Product ID, Price, Competitor's Price, Sales Volume
- **Categorical Fields**: Product Position, Promotion, Foot Traffic, Consumer Demographics, Product Category, Seasonal

## Data Quality Checks

| Check | Result | Action |
|-------|--------|--------|
| Missing Values | 0 | None required |
| Exact Duplicate Rows | 0 | None required |
| Duplicate Product IDs | 11 | Retained -- may represent different placements of same SKU |
| Inconsistent Categories | 0 | None required |
| Outliers (IQR Method) | 2 | Retained -- extreme performance may indicate opportunities |

## Derived Fields

| Field | Formula | Purpose |
|-------|---------|---------|
| Sales Amount | Price x Sales Volume | Total revenue per observation |
| Price Spread vs Competitor | Price - Competitor Price | Pricing position indicator |
| Estimated Profit | (Price - Competitor Price) x Sales Volume | Proxy for profitability |
| Estimated Profit Margin | Estimated Profit / Sales Amount | Margin percentage |
| Price Position | IF Price > Competitor THEN "Premium" ELSE "Discount" | Strategic pricing bucket |
| Outlier Flag | IQR method on Sales Volume & Sales Amount | Statistical anomaly detection |

## Category Analysis

| Category | Sales (Rs.) | Share |
|----------|-------------|-------|
| Clothing | 17,305,909 | 34.6% |
| Food | 16,364,252 | 32.7% |
| Electronics | 16,337,370 | 32.7% |

## Placement Analysis

| Placement | Sales (Rs.) | Share |
|-----------|-------------|-------|
| End-cap | 17,421,854 | 34.8% |
| Aisle | 16,845,879 | 33.7% |
| Front of Store | 15,739,797 | 31.5% |

## Promotion Analysis

| Status | Sales (Rs.) | Share |
|--------|-------------|-------|
| Non-Promoted | 25,459,263 | 50.9% |
| Promoted | 24,548,267 | 49.1% |

## Foot Traffic Analysis

| Traffic Level | Sales (Rs.) | Share |
|---------------|-------------|-------|
| High | 16,840,186 | 33.7% |
| Medium | 14,320,000 | 28.6% |
| Low | 11,910,000 | 23.8% |

## Seasonal Analysis

| Seasonal | Sales (Rs.) | Share |
|----------|-------------|-------|
| Yes | 25,814,085 | 51.6% |
| No | 24,193,445 | 48.4% |

## Demographic Analysis

| Demographic | Sales (Rs.) | Share |
|-------------|-------------|-------|
| College Students | 12,860,660 | 25.7% |
| Working Professionals | 10,920,000 | 21.8% |
| Families | 9,250,000 | 18.5% |
| Seniors | 7,470,000 | 14.9% |
| Teenagers | 5,790,000 | 11.6% |
| Others | 4,120,000 | 8.2% |

## Top Products

| Product ID | Sales (Rs.) | Profit (Rs.) | Margin | Category |
|------------|-------------|--------------|--------|----------|
| 115581 | 241,836 | 17,677 | 7.3% | Clothing |
| 176976 | 198,420 | 0 | 0.0% | Electronics |

## Data Limitations
- **No Date Field**: Time-series, trend, growth, and seasonal calendar analysis unavailable
- **No Geographic Fields**: Region, state, city, and territory comparisons unavailable
- **No Customer ID**: Individual customer behavior and loyalty analysis unavailable
- **No Actual Cost**: True profit calculation unavailable -- estimated profit uses price spread as proxy
- **No Store ID**: Location-level profitability and store comparison unavailable

## Recommended Future Fields
- Date (order date)
- Region, State, City, Store ID, Country
- Customer ID, Customer Name, Customer Segment
- Actual Cost, True Profit, COGS
- Order ID, Transaction ID
- Channel (Online, In-store, Mobile)
