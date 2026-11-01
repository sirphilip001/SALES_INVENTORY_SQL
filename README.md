# Sales and Inventory SQL Analysis

A PostgreSQL learning project for exploring customer, product, sales, and inventory data. The repository pairs a relational schema and sample dataset with 50 SQL exercises covering retrieval, aggregation, filtering, and table joins.

## Project overview

The script creates a schema named `assignment` and four related tables:

| Table | Description |
| --- | --- |
| `customers` | Customer contact details, registration dates, and membership tiers |
| `products` | Product names, categories, prices, suppliers, and stock quantities |
| `sales` | Sales records linked to customers and products, including quantities, dates, and sale amounts |
| `inventory` | Stock quantities linked to products |

The sample dataset contains 50 customers, 15 products, 15 sales, and 15 inventory records. Foreign keys connect sales to customers and products, and inventory records to products.

## What the project demonstrates

- Creating a schema and relational tables with primary and foreign keys
- Loading sample records into related tables
- Filtering and sorting records
- Aggregating data with `COUNT`, `SUM`, `AVG`, `MIN`, and `MAX`
- Grouping results and filtering groups with `HAVING`
- Joining customer, product, sales, and inventory data
- Using self-joins, subqueries, `UNION`, date functions, intervals, and pattern matching

## Repository contents

```text
.
├── README.md
└── sales_inventory.sql
```

## Requirements

- PostgreSQL
- `psql` or a PostgreSQL-compatible client such as pgAdmin or DBeaver

## Run the project

The script creates the `assignment` schema inside the database you connect to. Use a fresh practice database because the script creates fixed schema and table names and is not designed to run repeatedly in the same database.

```bash
createdb sales_inventory_db
psql -d sales_inventory_db -f sales_inventory.sql
```

Alternatively, connect to an empty practice database in `psql` and run:

```text
\i /path/to/sales_inventory.sql
```

You can also open `sales_inventory.sql` in pgAdmin, DBeaver, or another PostgreSQL client, connect to a practice database, and execute the script.

## Data model notes

- `sales.customer_id` references `customers.customer_id`.
- `sales.product_id` and `inventory.product_id` reference `products.product_id`.
- Product stock is stored in both `products` and `inventory`; the script does not keep those values synchronized automatically.
- `sales.total_amount` is loaded as sample data rather than calculated by a database rule.

## Scope

This is a SQL practice project with sample records, not a production sales system. The numbered queries are useful for learning and exploration; check their filters and aggregation logic before using results as business metrics.

## Suggested GitHub repository name

`sales-inventory-postgresql`

