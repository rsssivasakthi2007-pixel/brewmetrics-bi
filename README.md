# BrewMetrics Coffee Co. — Sales Performance Dashboard

A version-controlled Power BI analytics solution for BrewMetrics Coffee Co. that analyzes sales performance across products, cities, categories, and time.

## Data Model

The project uses a star schema consisting of one fact table and three dimension tables.

### Fact Table

**Fact_Sales**
- sale_id
- date
- city
- store_format
- category
- item
- quantity
- unit_price
- sales_amount

### Dimension Tables

**Dim_Date**
- date
- Year
- Month Name
- Month Number
- Day

**Dim_City**
- city

**Dim_Product**
- category
- item

### Relationships

- Dim_Date[date] → Fact_Sales[date]
- Dim_City[city] → Fact_Sales[city]
- Dim_Product[item] → Fact_Sales[item]

The dimension tables are connected to the Fact_Sales table to support filtering and analysis.

## Dashboard Insights

1. Cold Brew sales show a seasonal pattern across the April–June period, with the dashboard providing a month-wise view of Cold Brew sales.

2. City-level sales performance varies across locations, allowing BrewMetrics Coffee Co. to compare sales contributions between cities.

3. Sales also vary across product categories, helping identify categories with higher contributions to overall sales.

## Dashboard Features

- Cold Brew seasonal sales trend
- City-level sales performance comparison
- Category-wise sales analysis
- Interactive city slicer
- Date drill-down from Year → Month → Day

## DAX Measures

- Total Sales
- MoM Sales Growth %
- Running Total Sales
- Item Rank
- Average Transaction Value

## Tools Used

- Power BI
- Power Query
- DAX
- GitHub
- GitHub Copilot
- Visual Studio Code