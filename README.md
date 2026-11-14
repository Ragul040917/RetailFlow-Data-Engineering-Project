<<<<<<< HEAD
# RetailFlow – End-to-End Data Engineering Project

## Project Overview

RetailFlow is an end-to-end retail data engineering project built using Databricks, PySpark, Delta Lake, and SQL.

The project demonstrates how raw retail data can be ingested, cleaned, transformed, validated, and converted into meaningful business insights using the Medallion Architecture.

The final output is an interactive sales analytics dashboard that helps analyze daily revenue, product performance, store performance, and monthly sales trends.

## Project Objectives

- Build an end-to-end data engineering workflow.
- Implement Medallion Architecture (Bronze, Silver, and Gold).
- Perform data cleaning and transformation using PySpark.
- Store processed datasets as Delta tables.
- Implement automated data quality validation checks.
- Generate business-level analytical tables.
- Build a sales analytics dashboard using Databricks SQL.

## Technologies Used

| Technology | Purpose |
|---|---|
| Databricks | Data engineering platform |
| PySpark | Data processing and transformation |
| Python | Data generation and validation logic |
| Delta Lake | Reliable data storage |
| SQL | Analytical queries |
| Medallion Architecture | Organizing data processing layers |
| Databricks SQL | Dashboard and visualization |

## Project Architecture

```text
                Raw Retail CSV Files
                         |
                         v
                 BRONZE LAYER
                Raw Data Ingestion
                         |
                         v
                 SILVER LAYER
             Data Cleaning and Quality
                         |
                         v
                  GOLD LAYER
               Business Aggregations
                         |
                         v
             Automated Data Validation
                         |
                         v
              Databricks SQL Dashboard
                         |
                         v
                  Business Insights
```

## Dataset Description

The project uses four retail datasets:

| Dataset | Description |
|---|---|
| orders.csv | Customer order information |
| order_items.csv | Individual items associated with orders |
| products.csv | Product details and pricing |
| stores.csv | Store information and locations |

The datasets contain sample data, including duplicates, missing values, and invalid quantities to demonstrate data cleaning and validation.

## Medallion Architecture Implementation

### 1. Bronze Layer – Data Ingestion

Notebook: `00_Generate_Retail_Data.py` and `01_Bronze_Ingestion.py`

- Generated sample retail datasets.
- Ingested raw CSV files into Databricks.
- Added ingestion timestamps.
- Stored raw datasets as Delta tables.

Bronze tables:

- bronze_orders
- bronze_order_items
- bronze_products
- bronze_stores

### 2. Silver Layer – Data Transformation

Notebook: `02_Silver_Transformation.py`

Performed data cleaning and transformation operations:

- Removed duplicate records.
- Handled missing customer IDs.
- Removed invalid order quantities.
- Replaced missing product categories with Unknown.
- Converted columns into appropriate data types.
- Trimmed unnecessary whitespace.
- Validated cleaned datasets.

Silver tables:

- silver_orders
- silver_order_items
- silver_products
- silver_stores

### 3. Gold Layer – Business Analytics

Notebook: `03_Gold_Analytics.py`

Joined the cleaned datasets and calculated business metrics such as revenue, order counts, and quantities sold.

Created four analytical tables:

- gold_daily_sales
- gold_product_performance
- gold_store_performance
- gold_monthly_sales

Revenue calculation:

```python
revenue = quantity * price
```

## Data Quality Framework

Notebook: `04_Data_Quality_Checks.py`

Implemented a reusable PySpark validation function to automate data quality checks.

The framework includes 11 validation checks covering:

- Duplicate order IDs.
- Missing customer IDs.
- Duplicate order item IDs.
- Invalid quantities.
- Missing product categories.
- Invalid product prices.
- Duplicate store IDs.
- Missing store details.
- Negative daily revenue.
- Negative product revenue.
- Negative store revenue.

The validation results are consolidated into a Spark DataFrame with:

- Check name
- Failed record count
- PASS / FAIL status

**Result:** All 11 validation checks passed with zero failed records in the completed project run.

## Dashboard and Business Insights

Created an interactive sales analytics dashboard using Databricks SQL.

The dashboard includes four visualizations:

1. Daily Revenue Trends – Analyzes daily sales fluctuations.
2. Top 10 Performing Products – Identifies products generating the highest revenue.
3. Store-wise Revenue Analysis – Compares revenue across retail stores.
4. Monthly Sales Performance – Analyzes monthly business performance.

## Repository Structure

```text
RetailFlow-Data-Engineering-Project/
│
├── notebooks/
│   ├── 00_Generate_Retail_Data.py
│   ├── 01_Bronze_Ingestion.py
│   ├── 02_Silver_Transformation.py
│   ├── 03_Gold_Analytics.py
│   └── 04_Data_Quality_Checks.py
│
├── screenshots/
│
├── README.md
└── .gitignore
```

## How to Run the Project

1. Create or access a Databricks workspace.
2. Import the project notebooks.
3. Configure the catalog, schema, and volume.
4. Generate the retail CSV datasets.
5. Execute the Bronze ingestion notebook.
6. Execute the Silver transformation notebook.
7. Execute the Gold analytics notebook.
8. Run the data quality validation notebook.
9. Use the Gold tables to create SQL queries and visualizations.
10. Build the final Databricks SQL dashboard.

## Key Learning Outcomes

- Understanding end-to-end data engineering workflows.
- Working with PySpark DataFrames.
- Implementing Medallion Architecture.
- Performing data cleaning and transformation.
- Working with Delta tables.
- Writing analytical SQL queries.
- Building reusable data quality validation logic.
- Creating business intelligence dashboards.

## Author

**Ragul Pushparaj**

GitHub: [Ragul040917](https://github.com/Ragul040917)

Project: RetailFlow – End-to-End Data Engineering Project
=======
# RetailFlow-Data-Engineering-Project.
End-to-end retail data engineering project using Databricks, PySpark, Delta Lake, Medallion Architecture and SQL Analytics.
>>>>>>> cbf67b1c0e3d1090bfc92c7ca3e49ecb9172e3d7
