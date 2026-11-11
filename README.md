# PostgreSQL Sales and Inventory Database

A PostgreSQL database design and SQL query project for customer, product, sales, and inventory records. It demonstrates relational schema design, sample data loading, and SQL queries for retrieving, joining, summarizing, and reviewing inventory data.

## Project overview

The SQL script creates an assignment schema with four related tables:

| Table | Description |
| --- | --- |
| customers | Customer contact details, registration dates, and membership tiers |
| products | Product names, categories, prices, suppliers, and stock quantities |
| sales | Sales records linked to customers and products, including quantities, dates, and amounts |
| inventory | Stock quantities linked to products |

The sample dataset contains 50 customers, 15 products, 15 sales, and 15 inventory records. Primary and foreign keys define the relationships between the tables.

## Database design and SQL work

The project demonstrates:

- Creating a PostgreSQL schema and related tables with primary and foreign keys
- Loading sample records into relational tables
- Querying inventory levels, including low-stock products
- Joining customer, product, sales, and inventory records
- Filtering, sorting, grouping, and aggregating results with COUNT, SUM, AVG, MIN, MAX, and HAVING
- Using subqueries, self-joins, UNION, date functions, intervals, and pattern matching

## Relevance to ICT support

The database design and inventory queries show skills that transfer to maintaining structured records and supporting database-backed applications. The inventory model is relevant to equipment-register work, while the queries can retrieve stock and transaction information for reporting.

## Project scope

This project uses sample records to demonstrate database design and SQL query work. It is not a live inventory application. Product stock is stored in both the products and inventory tables, and the script does not automatically synchronize those values. It also does not implement user access controls, backups, or restore procedures.

## Repository contents

- README.md: project overview and setup instructions
- sales_inventory.sql: schema, sample records, and SQL queries

## Requirements

- PostgreSQL
- psql or a PostgreSQL-compatible client such as pgAdmin or DBeaver

## Run the project

Use an empty database because the script creates fixed schema and table names and is not designed to run repeatedly in the same database.

    createdb sales_inventory_db
    psql -d sales_inventory_db -f sales_inventory.sql

Alternatively, connect to an empty database in psql and run:

    \i /path/to/sales_inventory.sql

You can also open sales_inventory.sql in pgAdmin, DBeaver, or another PostgreSQL client, connect to an empty database, and execute the script.

## Data model notes

- sales.customer_id references customers.customer_id.
- sales.product_id and inventory.product_id reference products.product_id.
- Product stock is stored in both products and inventory; the script does not keep those values synchronized automatically.
- sales.total_amount is sample data rather than a value calculated by a database rule.
