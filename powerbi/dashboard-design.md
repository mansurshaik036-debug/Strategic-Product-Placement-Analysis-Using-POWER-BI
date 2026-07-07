# Dashboard Design Specification

## Page 1: Executive Overview

### KPI Cards (Top Row)
| Card | Measure | Format | Trend |
|------|---------|--------|-------|
| Total Sales | [Total Sales] | Rs.#,##0 | up +12.4% |
| Est. Profit | [Estimated Profit] | Rs.#,##0 | up +8.7% |
| Units Sold | [Total Quantity Sold] | #,##0 | up +5.2% |
| Avg Order Value | [Avg Order Value] | Rs.#,##0 | down -1.3% |
| Profit Margin | [Profit Margin] | 0.0% | up +0.4pp |
| Avg Unit Price | [Avg Unit Price] | Rs.#,##0 | up +2.1% |

### Visuals
1. **Category Bar Chart**: Product Category (X) vs Sales Amount (Y) -- Clustered bar, sorted descending
2. **Category Donut**: Product Category vs Sales Amount -- Show % of total
3. **Placement Funnel**: Product Position vs Sales Amount -- Funnel chart
4. **Promotion Comparison**: Promotion flag vs Sales -- Clustered bar
5. **Traffic Analysis**: Foot Traffic vs Sales -- Clustered bar
6. **Scatter Plot**: Sales Amount (X) vs Estimated Profit (Y), bubble size = Sales Volume, color = Product Category

### Slicers (Left Panel)
- Product Position (Dropdown)
- Promotion (Toggle buttons)
- Foot Traffic (Dropdown)
- Consumer Demographics (Dropdown)
- Product Category (Multi-select)
- Seasonal (Toggle)
- Price Position (Dropdown)

## Page 2: Placement Strategy

### Visuals
1. **Heatmap Matrix**: Rows = Product Position, Columns = Product Category, Values = Sales Amount
2. **Placement Efficiency Funnel**: Product Position vs Placement Efficiency
3. **Placement Insights**: Text box with 4 strategic recommendations

## Page 3: Product & Category

### Visuals
1. **Top 10 Products Table**: Product ID, Category, Sales, Profit, Margin %, Placement
   - Conditional formatting: Margin bar (green gradient)
   - Data bars on Sales column
2. **Price Position Line**: Price Spread vs Competitor trend
3. **Seasonal Impact**: Seasonal vs Non-Seasonal sales comparison
4. **Product Alerts**: Conditional formatting for 0% margin products

## Page 4: Customer & Demographics

### Visuals
1. **Demographics Funnel**: Consumer Demographics vs Sales Amount
2. **Demographics Heatmap**: Rows = Demographics, Columns = Category, Values = Sales
3. **Customer Strategy**: Text box with 4 demographic recommendations

## Page 5: Actionable Insights

### Visuals
1. **Insights Grid**: 10 cards with priority numbers, titles, and descriptions
2. **Implementation Table**: Visual type, fields, purpose
3. **DAX Reference**: Code block with key measures

## Color Palette

| Purpose | Color | Hex |
|---------|-------|-----|
| Primary (Clothing) | Teal | #0d9488 |
| Secondary (Food) | Sky Blue | #0ea5e9 |
| Tertiary (Electronics) | Purple | #8b5cf6 |
| Positive | Green | #34d399 |
| Negative | Red | #f87171 |
| Warning | Amber | #fbbf24 |
| Background | Dark Slate | #0f172a |
| Card | Slate | #1e293b |
| Border | Gray | #334155 |
| Text Primary | White | #f8fafc |
| Text Secondary | Light Gray | #94a3b8 |

## Typography
- Headers: Inter, 14-22px, weight 600
- Body: Inter, 12px, weight 400
- KPI Values: Inter, 24-28px, weight 600, tabular-nums
- Labels: Inter, 11px, weight 500, uppercase

## Interactions
- Cross-filtering: All slicers filter all visuals on page
- Drill-through: Click product in table -- Product Detail page
- Tooltips: Custom tooltip pages showing product details
- Bookmarks: Save filter states for executive presentations
