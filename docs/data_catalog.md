# 📘 Gold Layer Data Catalog – SQL Data Warehouse Project

The **Gold Layer** contains business-ready, consumption-optimized views built from the Silver Layer. These are structured in a dimensional model (star schema) to support reporting, analytics, and machine learning.

---

## 🔹 `dim_customers` (Dimension)

**Description:** Contains enriched and standardized customer information from CRM and ERP systems.

| Column Name      | Data Type     | Description                                       |
|------------------|---------------|---------------------------------------------------|
| `customer_key`   | INT           | Surrogate key (primary key).                     |
| `customer_id`    | INT           | Original ID from CRM.                            |
| `customer_number`| NVARCHAR(50)  | Unique customer reference number.                |
| `first_name`     | NVARCHAR(50)  | Customer's first name.                           |
| `last_name`      | NVARCHAR(50)  | Customer's last name.                            |
| `country`        | NVARCHAR(50)  | Country of residence.                            |
| `marital_status` | NVARCHAR(50)  | Marital status (`Single`, `Married`, etc.).      |
| `gender`         | NVARCHAR(50)  | Gender (`Male`, `Female`, `N/A`).                |
| `birthdate`      | DATE          | Date of birth (YYYY-MM-DD).                      |
| `create_date`    | DATE          | Record creation date.                            |

---

## 🔹 `dim_products` (Dimension)

**Description:** Contains product metadata and hierarchy information derived from CRM and ERP product catalogs.

| Column Name        | Data Type     | Description                                               |
|--------------------|---------------|-----------------------------------------------------------|
| `product_key`      | INT           | Surrogate key (primary key).                             |
| `product_id`       | INT           | Product ID from source systems.                          |
| `product_number`   | NVARCHAR(50)  | Unique product identifier (e.g., model number).          |
| `product_name`     | NVARCHAR(50)  | Full product name and description.                       |
| `category_id`      | NVARCHAR(50)  | Category identifier (for grouping).                      |
| `category`         | NVARCHAR(50)  | Main product category (`Bikes`, `Components`, etc.).     |
| `subcategory`      | NVARCHAR(50)  | More granular grouping (e.g., `Road Frames`).            |
| `maintenance`      | NVARCHAR(50)  | Indicates if product needs maintenance (`Yes`, `No`).    |
| `cost`             | INT           | Product cost (monetary units).                           |
| `product_line`     | NVARCHAR(50)  | Classification such as `Road`, `Mountain`, etc.          |
| `start_date`       | DATE          | Date the product became available.                       |

---

## 🔹 `fact_sales` (Fact)

**Description:** Captures transactional sales data, including order-level metrics linked to customers and products.

| Column Name     | Data Type     | Description                                                   |
|-----------------|---------------|---------------------------------------------------------------|
| `order_number`  | NVARCHAR(50)  | Unique sales order ID (e.g., `SO43697`).                     |
| `product_key`   | INT           | Foreign key to `dim_products`.                               |
| `customer_key`  | INT           | Foreign key to `dim_customers`.                              |
| `order_date`    | DATE          | Date when the order was placed.                              |
| `shipping_date` | DATE          | Date when the order was shipped.                             |
| `due_date`      | DATE          | Date the payment was due.                                    |
| `sales_amount`  | INT           | Total revenue from the sale (Quantity × Price).              |
| `quantity`      | INT           | Number of units sold.                                        |
| `price`         | INT           | Unit price of the product.                                   |

---

## ✅ Notes

- All views follow **snake_case** naming conventions.
- Foreign key relationships between dimensions and fact are established through surrogate keys.
- `sales_amount` is a derived metric: `quantity * price`.

---
