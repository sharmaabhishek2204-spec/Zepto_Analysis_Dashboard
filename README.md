# Zepto Inventory & Pricing Analysis | PostgreSQL

## Project Overview

This project uses **PostgreSQL** to explore and analyze Zepto product-level data, focusing on pricing, discounts, stock availability, product value, and inventory weight.

The objective is to use SQL to answer practical business questions and turn raw product data into structured analysis that can support pricing and inventory-related decisions.

> **Note:** This project analyzes product and inventory data. It does not contain transaction-level sales, customer, or cost data; therefore, it cannot establish actual sales revenue, profit, customer demand, or lost sales.

## Business Problems Addressed

The project answers the following eight business questions:

| # | Business Question | Business Purpose |
|---|---|---|
| 1 | **Find the top 10 best-value products based on discount percentage.** | Identify products offering the highest percentage discounts and compare promotional value. |
| 2 | **What are the products with high MRP but out of stock?** | Highlight higher-priced products that are unavailable, helping identify potential availability concerns. |
| 3 | **Calculate estimated revenue for each category.** | Compare categories using selling price and available quantity as an inventory-value proxy. |
| 4 | **Find products where MRP is greater than ₹500 and discount is less than 10%.** | Identify relatively expensive products with limited discounts. |
| 5 | **Identify the top 5 categories offering the highest average discount percentage.** | Compare discount intensity across categories and identify categories with stronger promotional pricing. |
| 6 | **Find the price per gram for products above 100g and sort by best value.** | Compare unit pricing across eligible products to identify lower price-per-gram options. |
| 7 | **Group products into Low, Medium, and Bulk weight categories.** | Segment products based on weight for easier product-level analysis. |
| 8 | **Calculate total inventory weight per category.** | Compare the weight represented by available inventory across product categories. |

### Important Metric Clarification

Question 3 is labelled “estimated revenue” in the original analysis question. However, the calculation:

`discountedSellingPrice × availableQuantity`

represents **estimated inventory value at the discounted selling price**, not actual revenue. Actual revenue requires sales or transaction data.

## Project Workflow

1. **Table creation:** Defined the `zepto` table and its product-level fields.
2. **Data exploration:** Checked row count, previewed records, examined categories, stock status, and repeated product names.
3. **Data quality checks:** Checked for NULL values and zero-price records.
4. **Data cleaning:** Removed zero-MRP records and converted prices from paise to rupees where applicable.
5. **SQL analysis:** Wrote SQL queries to answer the eight business questions.
6. **Excel reporting:** Imported the dataset into Microsoft Excel for further analysis and dashboard presentation.

## SQL Concepts Used

- `SELECT`, `WHERE`, `ORDER BY`, and `LIMIT`
- `DISTINCT`
- `GROUP BY` and `HAVING`
- Aggregate functions: `COUNT()`, `SUM()`, and `AVG()`
- `ROUND()`
- `CASE WHEN`
- Data cleaning using `DELETE` and `UPDATE`
- Boolean filtering
- NULL-value checks

## Dataset Fields

| Column | Description |
|---|---|
| `sku_id` | Unique SKU identifier |
| `category` | Product category |
| `name` | Product name |
| `mrp` | Maximum Retail Price |
| `discountPercent` | Discount percentage |
| `availableQuantity` | Available inventory quantity |
| `discountedSellingPrice` | Selling price after discount |
| `weightInGms` | Product weight in grams |
| `outOfStock` | Stock availability indicator |
| `quantity` | Product quantity field in the dataset |

## Tools Used

- **PostgreSQL** — Data exploration, cleaning, and SQL analysis
- **Microsoft Excel** — Dataset import, PivotTables, PivotCharts, and dashboard reporting
- **GitHub** — Project documentation and portfolio presentation

## Key Learning Outcomes

- Practiced writing SQL queries to answer structured business questions.
- Explored product pricing, discount, and inventory patterns.
- Used aggregation and conditional logic for category-level analysis.
- Applied data quality checks before analysis.
- Connected SQL analysis with Excel-based reporting.
- Learned to distinguish inventory metrics from sales and revenue metrics.

## Limitations

- The dataset is product-level and does not include transaction history.
- Actual sales revenue, profit margins, customer behavior, and demand cannot be calculated from the available fields.
- Out-of-stock products do not automatically imply lost sales.
- Price-per-gram comparisons may not be meaningful across products with different formats or use cases.
- Findings describe patterns in the available dataset and should not be interpreted as verified internal Zepto business performance.

## Conclusion

This project demonstrates a practical SQL workflow—from data exploration and cleaning to answering business questions about pricing, discounts, and inventory. The analysis is further presented through Excel reporting to make the results easier to interpret.
