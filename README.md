# Retail-Sales-Data-Warehousing-Project


# Data Warehouse and Analytical Queries Setup

This project consists of three SQL scripts to set up a data warehouse schema, transform data, and define analytical queries. Each script is briefly explained below:

## 1. `oltp_schema.sql`
Defines the Online Transaction Processing (OLTP) schema, setting up tables to store raw transactional data. This schema includes:
- **shops_data**: Information about each shop, including location and type.
- **item_categories_data**: Stores item category names.
- **items_data**: Holds item details and links to categories.
- **sales_transactions**: Records each transaction, including date, shop, item, and sales data.

## 2. `dimensional_model.sql`
Defines the dimensional model schema used for data warehousing. This script:
- Drops existing tables (if any) and recreates **dimension tables** (shops, items, date) and a **fact table** (`sales_fact`).
- Populates these tables with data from the OLTP schema.
- **Dimension Tables**:
  - `shops_dim`: Detailed shop information.
  - `item_dim`: Item and category data.
  - `date_dim`: Date attributes for time-based analysis.
- **Fact Table**:
  - `sales_fact`: Aggregated sales data, referencing dimensions for analytical queries.

## 3. `creating_view_analytical_queries.sql`
Defines several analytical views to support business insights and trend analysis:
- **v_monthly_sales_units**: Monthly total sales and units sold.
- **v_day_of_week_sales**: Day-of-week sales and units analysis.
- **v_cumulative_sales**: Monthly cumulative sales.
- **v_top_10_shops_sales**: Top shops by total sales with quartile rankings.
- **v_correlation_price_units**: Correlation between item price and units sold.
- **v_rolling_3_month_sales**: Rolling 3-month sales by shop.
- **v_quarterly_sales_growth**: Quarterly sales and growth percentage.
- **v_year_over_year_growth**: Year-over-year monthly growth.
- **v_monthly_sales_by_category**: Monthly sales by item category.
- **v_top_5_items_per_shop**: Top 5 items by units sold for each shop.

This setup enables efficient data analysis and insights into sales trends, customer behavior, and product performance.

## Usage
Run each SQL script in sequence to build the database schema and views:
1. Execute `oltp_schema.sql` to create and populate raw tables.
2. Run `dimensional_model.sql` to set up the dimensional model and fact table.
3. Execute `creating_view_analytical_queries.sql` to create views for analytical reporting.

## Requirements
Requires an SQL-compatible database like Oracle or PostgreSQL. Ensure necessary permissions for table creation and data manipulation.
