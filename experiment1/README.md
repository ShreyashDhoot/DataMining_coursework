# Experiment 1: OLAP Operations on Warehouse Data

## Overview
This experiment demonstrates core OLAP operations using a small warehouse-style dataset in a Jupyter notebook.

Notebook used:
- warehouse.ipynb

The workflow creates three CSV files, combines them into a fact table, and performs the following operations:
- Roll-up
- Roll-down (Drill-down)
- Slice
- Dice
- Pivot

## Objective
Build a simple data warehouse view from sales data and apply OLAP operations for multidimensional analysis.

## Files in This Experiment
- Customers.csv: Customer dimension data
- Products.csv: Product dimension data
- Sales.csv: Transaction (fact-like) source data
- warehouse.ipynb: Full implementation and outputs

## Dataset Structure
### Customers.csv
- customer_id
- customer_name
- city
- state

### Products.csv
- product_id
- product_name
- category
- price

### Sales.csv
- sale_id
- customer_id
- product_id
- sale_date
- quantity

## Steps Performed in Notebook
1. Create source CSV files for customers, products, and sales.
2. Read all CSV files using pandas.
3. Clean and prepare fields:
- quantity is converted to numeric safely (invalid/mixed values handled)
- sale_date is parsed to datetime
4. Merge sales with customer and product data to build a joined fact table.
5. Compute revenue as:

Revenue = quantity x price

6. Apply OLAP operations:
- Roll-up: Aggregate revenue from city level to state level
- Roll-down: Drill from state to city to customer
- Slice: Filter one dimension (for example, category = Electronics)
- Dice: Filter multiple dimensions together (state, category, quantity)
- Pivot: Create state x category revenue summary table

## OLAP Output Summary
- Joined fact table created successfully
- State-wise and city-wise revenue aggregation shown
- Drill-down view up to customer level shown
- Slice and dice filtered views shown
- Pivot table with grand total shown

## Tools and Libraries
- Python 3.x
- pandas
- Jupyter Notebook (VS Code or Jupyter environment)

## How to Run
1. Open warehouse.ipynb.
2. Run cells in order from top to bottom.
3. Verify CSV files are generated in the experiment folder.
4. Check displayed tables for each OLAP operation.

## Learning Outcomes
After completing this experiment, you can:
- Build a simple fact table from multiple CSV sources
- Prepare and clean data before aggregation
- Perform common OLAP operations with pandas
- Interpret summarized multidimensional data

## Note
The notebook includes handling for inconsistent quantity values in Sales.csv so aggregation does not fail.
