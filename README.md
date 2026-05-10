# ecommerce-database-oracle-sql
Oracle SQL e-commerce database — DDL schema, sample data, 15 analytics queries, and 4 PL/SQL stored procedures with real-world business logic.
#  E-Commerce Database — Oracle SQL

E-commerce database built in Oracle SQL with normalized schema, 15 analytics queries using JOINs, subqueries, and window functions, plus 4 PL/SQL stored procedures.

---

# File Structure

```
ecommerce-database-oracle-sql/
│
├── 01_schema.sql              # CREATE TABLE, sequences, indexes, constraints
├── 02_insert_data.sql         # Sample data — 50 customers, 20 products, 100+ orders
├── 03_queries.sql             # 15 analytics queries
├── 04_stored_procedures.sql   # 4 PL/SQL stored procedures
├── screenshots/               # Query output screenshots
├── .gitignore
└── LICENSE
```

---

# Database Schema (5 Tables)

```
customers ──< orders ──< order_items >── products
                │
             payments
```

| Table | Description | Rows |
|---|---|---|
| `customers` | Customer master data | 50 |
| `products` | Product catalog with stock | 20 |
| `orders` | Order headers | 120+ |
| `order_items` | Line items per order | 50+ |
| `payments` | Payment records | 43+ |

---

#  Skills Demonstrated

- DDL — CREATE TABLE, PRIMARY KEY, FOREIGN KEY, CHECK, UNIQUE constraints
- DML — INSERT, UPDATE with COMMIT and ROLLBACK
- Sequences for auto-increment IDs
- Indexes for query performance
- JOINs — INNER JOIN, LEFT JOIN, multi-table (5 tables)
- GROUP BY, HAVING, ORDER BY
- Subqueries and inline views
- Window Functions — RANK(), SUM() OVER, PARTITION BY
- Oracle-specific — TO_CHAR, NVL, ROWNUM, SYSDATE, RPAD
- PL/SQL — Stored procedures, CURSOR, FOR loop, EXCEPTION handling

---

#  15 Analytics Queries

| # | Query | Concepts |
|---|---|---|
| Q1 | Top 5 customers by spending | JOIN, GROUP BY, ROWNUM |
| Q2 | Monthly revenue trend | TO_CHAR, GROUP BY |
| Q3 | Best selling products | JOIN, GROUP BY, ROWNUM |
| Q4 | Revenue by category | JOIN, GROUP BY, HAVING |
| Q5 | Orders with no payment | LEFT JOIN, IS NULL |
| Q6 | City-wise customer count | GROUP BY, Window % |
| Q7 | Low stock alert | CASE WHEN, WHERE |
| Q8 | Avg order value by state | JOIN, AVG, GROUP BY |
| Q9 | Repeat customers | Subquery, HAVING |
| Q10 | Payment method breakdown | GROUP BY, Window % |
| Q11 | Rank customers by spending | RANK(), PARTITION BY |
| Q12 | Running total revenue | SUM() OVER, Window |
| Q13 | Order status summary | CASE, GROUP BY |
| Q14 | Full order details | 5-table JOIN |
| Q15 | Customers with no orders | LEFT JOIN, Anti Join |

---

# 4 PL/SQL Stored Procedures

| Procedure | Description |
|---|---|
| `place_new_order` | Places order, deducts stock, records payment with full validation |
| `low_stock_alert` | Prints products below stock threshold with CRITICAL / LOW STOCK label |
| `update_order_status` | Updates order status with transition validation |
| `customer_order_summary` | Prints full order history and total spending for any customer |

---

#  How to Run

**Requirements:** Oracle 10g or above, SQL*Plus or SQL Developer

```sql
-- Step 1: Navigate to project folder and open SQL*Plus
cd path\to\ecommerce-database-oracle-sql
sqlplus username/password

-- Step 2: Run files in order
@01_schema.sql
@02_insert_data.sql
@03_queries.sql
@04_stored_procedures.sql
```

> Always run in order — schema first, then data, then queries.

---

# Screenshots

# Schema verification
![Schema](screenshots/schema.png)

# Q1 — Top customers
![Top Customers](screenshots/q1_top_customers.png)


# Stored procedure output
![Procedure](screenshots/procedure_output.png)

---

# 🪪 License

This project is licensed under the [MIT License](LICENSE).
