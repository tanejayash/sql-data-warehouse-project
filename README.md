# SQL Data Warehouse Project – CRM & ERP Data Integration

Welcome to the **SQL Data Warehouse Project**, designed to demonstrate the complete end-to-end development of a modern data warehouse using best practices in ETL, dimensional modeling, and business reporting. This project integrates **CRM** and **ERP** datasets into a centralized data platform following a layered architecture: **Bronze**, **Silver**, and **Gold**.

---

## 📌 Project Objectives

- Build a scalable, modular data warehouse using SQL Server.
- Ingest, cleanse, and enrich raw CRM and ERP data using stored procedures.
- Apply dimensional modeling with star schema for analytics.
- Enable business-ready consumption through the Gold Layer.
- Ensure data traceability, documentation, and maintainability.

---

## 🛠️ Tech Stack

- **Database:** SQL Server
- **ETL Logic:** T-SQL Stored Procedures
- **Data Layers:** Bronze, Silver, Gold
- **Tools:** SSMS, Git
- **Modeling:** Star Schema (Dimensional Modeling)
- **Optional Consumption Layer:** Power BI / Tableau

---

## 🧱 Data Architecture

Sources → Bronze (Raw) → Silver (Cleaned) → Gold (Business-Ready) → BI / ML


- **Bronze Layer:** Raw, unprocessed data from CRM & ERP files.
- **Silver Layer:** Cleaned, standardized data with enriched attributes and business rules.
- **Gold Layer:** Star schema with `dim_customers`, `dim_products`, and `fact_sales` optimized for reporting.

---

## 📊 Gold Layer Overview

This layer contains business-ready **views** structured for analysis.

### ✔️ Views
- [`dim_customers`]
- [`dim_products`]
- [`fact_sales`]

---

## 🧩 Features

- ✅ Full Layered ETL (Truncate & Insert logic)
- ✅ Data Cleansing & Enrichment
- ✅ Data Lineage & Integration Maps
- ✅ Star Schema Design for Analytical Performance
- ✅ Documentation & Naming Standards

---

## 📌 How to Run

1. Clone the repository  
2. Execute Bronze → Silver → Gold scripts sequentially  
3. Review views
4. Use a BI tool (e.g., Tableau or Power BI) to connect and visualize

---

## 🧠 Author

**Yash Taneja**  
📫 [LinkedIn](https://www.linkedin.com/in/yash-taneja-07)  


