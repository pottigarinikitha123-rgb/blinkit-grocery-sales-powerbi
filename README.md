# Blinkit Grocery Sales Analysis | Power BI

An interactive Power BI report that analyzes **8,523 Blinkit grocery sales records** to find which products, outlet types, and locations drive revenue.

![Sales Overview Dashboard](images/03_dashboard_sales_overview.png)

## Business Problem

Blinkit is an Indian quick-commerce grocery app. Retail teams need to know where revenue comes from so they can decide what to stock, where to expand, and which outlets need attention. This project answers four questions:

1. How much revenue does the business generate, and what is the average sale and rating?
2. Which product categories and fat-content groups sell the most?
3. How do outlet size, location tier, and outlet type affect sales?
4. How does sales performance vary by outlet establishment year and by customer rating?

## Key Results at a Glance

| Metric | Value |
|---|---|
| Total Sales | **$1.20M** |
| Average Sale | **$141** |
| Number of Items | **8,523** |
| Average Rating | **3.9** |

## Dashboards

### 1. Sales Overview
KPI cards for Total Sales, Average Sales, Number of Items, and Average Rating; a metric switcher (field-parameter style slicer); a fat-content donut chart; and slicers for Outlet Location Type, Outlet Size, and Item Type.

### 2. Product and Outlet Trends
![Product and Outlet Trends](images/04_dashboard_product_outlet_trends.png)

Sales by fat content within each location tier, item count by fat content, sales by outlet establishment year, and a ranked bar chart of sales by item type.

### 3. Outlet Performance
![Outlet Performance](images/05_dashboard_outlet_performance.png)

Sales by outlet size, a funnel of sales by location tier, total sales by rating, and a conditionally formatted matrix comparing outlet types on Total Sales, Avg Rating, Avg Sales, Number of Items, and Item Visibility.

## Key Insights

- **Low-fat products drive about 65% of revenue** ($776K vs. $425K for regular), in line with low-fat items making up 64.7% of the catalog.
- **Fruits & Vegetables ($178K) and Snack Foods ($175K)** are the top categories, followed by Household ($136K) and Frozen Foods ($119K). Seafood, Breakfast, and Starchy Foods sell the least.
- **Tier 3 locations bring in the most revenue** ($472K, about 39%), ahead of Tier 2 ($393K) and Tier 1 ($336K).
- **Supermarket Type1 accounts for about 65% of sales** ($788K). Its average sale ($141) is almost the same as every other outlet type ($140 to $142), so its lead comes from **carrying more items (5,577), not from bigger individual sales**.
- **Medium-size outlets lead on revenue** ($508K), followed by Small ($445K) and High ($249K).
- **Outlets established in 2018 stand out** at $205K, while most other years hold steady at about $130K.
- **Sales concentrate around a rating of 4**, which matches the overall average rating of 3.9.

## Recommendations

- Keep low-fat products, Fruits & Vegetables, and Snack Foods well stocked, as they make up the core of revenue.
- Study what makes Tier 3 outlets successful and test those practices in Tier 1 and Tier 2 locations.
- Because average sale per item is flat across outlet types, grow revenue by expanding product range in smaller formats rather than relying on price.
- Review low-selling categories (Seafood, Breakfast, Starchy Foods) for repositioning or reduced shelf space.

## Methodology

**Data cleaning (Power Query)**
- Filled missing `Item Weight` values
- Standardized inconsistent `Item Fat Content` labels (for example, "LF", "low fat", and "Low Fat" into one value)
- Removed duplicate rows and set correct data types
- Kept every step in Applied Steps so the workflow can be repeated

![Power Query Cleaning](images/01_power_query_cleaning.png)

**Data modeling**
- Main fact table: `BlinkIT Grocery Data`
- Supporting table `METRIX` drives the metric-switcher slicer
- DAX measures: `Total Sales`, `Avg Sales`, `No of Items`, `Avg Rating`

![Data Model](images/02_data_model.png)

## Dataset

8,523 rows covering:
- **Product info:** Item Identifier, Item Type, Item Fat Content, Item Weight, Item Visibility
- **Outlet info:** Outlet Identifier, Outlet Type, Outlet Size, Outlet Location Type, Outlet Establishment Year
- **Performance:** Sales, Rating

Source: [Blinkit grocery dataset (Google Drive)](https://drive.google.com/drive/folders/1mKh61zKVBnPJN0A5lc77osGNkmNa-loI)

## Tools and Skills

Power BI Desktop · Power Query · DAX · Data Modeling · KPI Design · Conditional Formatting · Data Storytelling

## Repository Structure

```
├── powerbi/
│   └── blinkit_grocery_sales.pbix     # Power BI report file
├── report/
│   └── BlinkIT_Project_Report.pdf     # Full written project report
├── images/                            # Dashboard and model screenshots
└── README.md
```

## How to Open

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows).
2. Download `powerbi/blinkit_grocery_sales.pbix`.
3. Open it in Power BI Desktop and use the slicers to filter by location, outlet size, and item type.

## Team

Group project for **ISM 6404: Introduction to Business Analytics and Big Data**, Florida Atlantic University (April 2025)

- Nikhitha Pottigari
- Punith Kumar Vaddepally
- Sushank Yamzala
