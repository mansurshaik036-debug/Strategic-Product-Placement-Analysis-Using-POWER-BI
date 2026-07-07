# Slicer Configuration Guide

## Slicer 1: Product Position
- **Type**: Dropdown
- **Field**: Product Position
- **Values**: End-cap, Aisle, Front of Store
- **Default**: All
- **Sort**: By value (descending)
- **Style**: Filled, dark theme

## Slicer 2: Promotion
- **Type**: Toggle buttons
- **Field**: Promotion
- **Values**: Yes, No
- **Default**: All
- **Style**: Pill buttons, green for Yes, gray for No

## Slicer 3: Foot Traffic
- **Type**: Dropdown
- **Field**: Foot Traffic
- **Values**: High, Medium, Low
- **Default**: All
- **Sort**: Custom (High -> Medium -> Low)

## Slicer 4: Consumer Demographics
- **Type**: Dropdown
- **Field**: Consumer Demographics
- **Values**: College Students, Working Professionals, Families, Seniors, Teenagers
- **Default**: All
- **Sort**: By sales (descending)

## Slicer 5: Product Category
- **Type**: Multi-select dropdown
- **Field**: Product Category
- **Values**: Clothing, Food, Electronics
- **Default**: All
- **Style**: Color-coded chips (Teal, Blue, Purple)

## Slicer 6: Seasonal
- **Type**: Toggle buttons
- **Field**: Seasonal
- **Values**: Yes, No
- **Default**: All

## Slicer 7: Price Position
- **Type**: Dropdown
- **Field**: Price Position (calculated)
- **Values**: Premium, Discount
- **Default**: All

## Cross-Filtering Setup
1. Select all slicers
2. Format -> Edit interactions
3. Set all visuals to "Filter" (not highlight)
4. Ensure slicers affect all pages via sync slicers

## Sync Slicers Across Pages
1. View -> Sync slicers
2. Select each slicer
3. Check all pages where it should apply
4. Enable "Visible" on pages where it should show
