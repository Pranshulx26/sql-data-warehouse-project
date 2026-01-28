# SQL Data Warehouse and Analytics Project

## 📌 Project Overview

Welcome to the **Data Warehouse and Analytics Project** repository!
This project demonstrates the end-to-end development of a modern **Data Warehouse using SQL Server**. The primary goal is to consolidate disparate sales data from two different source systems (**ERP and CRM**) into a centralized **Single Source of Truth**.

By implementing the **Medallion Architecture (Bronze, Silver, Gold)**, raw and messy data is transformed into high-quality, business-ready datasets optimized for **analytical reporting** and **strategic decision-making**.

---

## 🏗️ Data Architecture

The project follows a multi-layered data architecture to ensure data integrity and scalability:

- **Bronze Layer (Raw):**  
  Ingests raw data from CSV files as-is. This serves as the landing zone for ERP and CRM source data.

- **Silver Layer (Cleaned):**  
  Data undergoes cleansing, standardization, and normalization. Key activities include handling null values, fixing data types, and removing duplicates.

- **Gold Layer (Analytical):**  
  Data is modeled into a **Star Schema (Fact and Dimension tables)**. This layer is optimized for high-performance BI queries and dashboarding.

---

## 🚀 Key Features & Skills Demonstrated

- **Advanced SQL Development:**  
  Utilized complex DDL/DML scripts, window functions, and views to manage data flow.

- **Data Integration (ETL):**  
  Designed logic to merge fragmented data from ERP (Product/Sales) and CRM (Customer) systems.

- **Dimensional Modeling:**  
  Developed a robust **Star Schema** consisting of:
  - **Fact Tables:** Sales Transactions  
  - **Dimension Tables:** Customers, Products, and Date/Time  

- **Data Quality Assurance:**  
  Implemented data validation checks at the Silver layer to ensure accuracy before reporting.

- **Business Intelligence:**  
  Created SQL-based analytical views to track **Customer Behavior**, **Product Performance**, and **Sales Trends**.

---

## 📂 Repository Structure

```text
sql-data-warehouse-project/
├── datasets/             # Raw CSV files from ERP and CRM systems
├── scripts/              # SQL Scripts for Environment Setup & ETL
│   ├── bronze/           # DDL for loading raw data
│   ├── silver/           # Data cleaning and transformation logic
│   └── gold/             # Data modeling and Star Schema creation
├── docs/                 # Data Models, ER Diagrams, and Requirements
└── README.md             # Project Documentation
```

## 🛠️ Tools & Technologies

| Technology        | Purpose |
|-------------------|---------|
| **SQL Server**    | Database engine for warehouse storage |
| **T-SQL**         | Querying, transformations, and analytics |
| **SSMS / VS Code**| Development environments for SQL |
| **Draw.io**       | Data models and architecture diagrams |
| **CSV Files**     | Source ERP & CRM datasets |

---

## 🔎 Business Problem Solved

This project tackles real-world data challenges:

✔ Consolidates data from distinct operational systems  
✔ Automates data cleansing and transformation  
✔ Models data in a business-ready format  
✔ Enables fast, consistent analytical queries  
✔ Supports reporting on customer behavior, product performance, and sales trends  

---

## 🧱 Key Project Phases

### 1) Data Ingestion & ETL

- Loaded source CSVs representing ERP and CRM data  
- Established automated ETL patterns for staging  
- Ensured schema consistency and data standardization  

### 2) Medallion Architecture

- **Bronze:** Raw tables for traceability  
- **Silver:** Cleansed and normalized tables  
- **Gold:** Business dimension & fact tables  

### 3) Star Schema & Analytics

Designed the **Gold Layer** for fast reporting:

- `dim_customers` – enriched customer dimension  
- `dim_products` – product dimension with business attributes  
- `fact_sales` – sales facts for metrics and trends  

These tables support high-performance analytical queries for dashboards and business reporting.

---

## 📊 Example Analytical Queries

```sql
-- Top 10 products by revenue
SELECT TOP 10
    p.product_name,
    SUM(f.sales_amount) AS total_revenue
FROM gold.fact_sales f
JOIN gold.dim_products p 
    ON f.product_key = p.product_key
GROUP BY p.product_name
ORDER BY total_revenue DESC;

-- Monthly revenue trend
SELECT
    YEAR(order_date) AS year,
    MONTH(order_date) AS month,
    SUM(sales_amount) AS monthly_revenue
FROM gold.fact_sales
GROUP BY YEAR(order_date), MONTH(order_date)
ORDER BY year, month;
```

## 🧾 Documentation

Documentation including **data catalogs, architecture diagrams, naming conventions, and modeling diagrams** can be found in the `docs/` directory. These explain the design choices, table definitions, and workflow diagrams in detail.

---

## 🎯 Skills & Concepts Demonstrated

This project highlights real, employer-relevant skills:

✔ Data modeling & warehouse architecture  
✔ ETL pipeline design & implementation  
✔ SQL query writing (business logic, reporting, aggregation)  
✔ Data quality checks and schema best practices  
✔ Analytical reporting support for business decisions  

## 🎯 Conclusion

This project highlights my ability to bridge the gap between raw data and actionable business insights. It showcases a disciplined approach to **Data Engineering**, ensuring that data is not just stored, but is **accurate, integrated, and accessible** for analytical and business use.

# 🛡️ License
This project is licensed under the **[MIT License](https://opensource.org/licenses/MIT)**.  
You are free to use, modify, and share this project with proper attribution.

---

# 🌟 About Me
Hi there! I’m **Pranshul Sharma**, a **B.Tech student in Information Technology** and a **Data Analyst enthusiast** on a mission to build a strong career in data analytics. I am passionate about transforming raw data into meaningful insights using **SQL, Python, and data visualization tools**.

I enjoy working on real-world datasets, exploring patterns, and presenting insights that support data-driven decision-making. Through continuous learning and hands-on projects, I am actively developing my skills in **data analysis, business intelligence, and analytical storytelling**, with the goal of becoming a proficient and impactful **Data Analyst**.


