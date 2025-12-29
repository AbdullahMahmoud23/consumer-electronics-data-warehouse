# Consumer Electronics Sales Data Warehouse

![Status](https://img.shields.io/badge/Status-Completed-success)
![SQL](https://img.shields.io/badge/Language-SQL-blue)
![Type](https://img.shields.io/badge/Type-Data%20Warehousing-orange)

## 📖 Project Overview
This project involves the design and implementation of a Data Warehouse for a consumer electronics retail company. The company operates both online and offline channels across the United States. The goal of this warehouse is to analyze sales performance, inventory management, and generate key business reports.

This repository contains the SQL scripts for designing the schema, loading data, and performing advanced analytical queries.

## 🏢 Business Scenario
As a Data Engineer, I was tasked with creating a solution to answer questions such as:
* What is the total sales revenue per year per city?
* How does revenue compare across different product categories and stores?
* What are the average and maximum sales figures for specific regions?

## 🏗️ Data Architecture
The project utilizes a **Star Schema** dimensional model:

### Fact Table
* **FactSales:** Stores transactional metrics like quantity sold and total price.
  * *Foreign Keys:* `DateID`, `StoreID`, `ProductKey`, `CustomerSegmentID`

### Dimension Tables
* **DimDate:** Attributes for Year, Quarter, Month, Day, and Weekday.
* **DimProduct:** Attributes for Product Name, Category, Type, and Price.
* **DimCustomerSegment:** Attributes for Segment Name and Demographics.

## 🛠️ Technologies & Skills
* **Database:** [Insert Database Name, e.g., PostgreSQL / DB2 / MySQL]
* **Modeling:** Dimensional Modeling (Star Schema)
* **SQL Techniques:**
  * DDL (Create/Alter Tables)
  * DML (Insert/Load Data)
  * Aggregations (`GROUP BY`)
  * Advanced OLAP (`CUBE`, `ROLLUP`, `GROUPING SETS`)
  * Materialized Views

## 📂 Project Structure & Tasks
The project is divided into the following implementation tasks:

### Phase 1: Design & DDL
- [x] **Task 1-3:** Designed dimension tables (`DimDate`, `DimProduct`, `DimCustomerSegment`).
- [x] **Task 4:** Designed the fact table (`FactSales`).
- [x] **Task 5-8:** Created the table schemas in the database.

### Phase 2: Data Loading (ETL)
- [x] **Task 9-11:** Loaded data into dimension tables.
- [x] **Task 12:** Loaded transactional data into `FactSales`.

### Phase 3: Analysis & Reporting
- [x] **Task 13:** Created **Grouping Sets** queries for flexible aggregation.
- [x] **Task 14:** Created **Rollup** queries for hierarchical reporting (Year > Month).
- [x] **Task 15:** Created **Cube** queries for cross-dimensional analysis (Year vs. City vs. Product).
- [x] **Task 16:** Implementation of **Materialized Views** for performance optimization.

## 🔍 Sample Analytics
*Below is an example of the Cube Query logic used in Task 15:*

```sql
SELECT 
    DimDate.Year, 
    DimStore.City, 
    DimProduct.ProductID, 
    AVG(FactSales.SalesAmount) as Average_Sales
FROM FactSales
JOIN DimDate ON FactSales.DateKey = DimDate.DateKey
JOIN DimProduct ON FactSales.ProductKey = DimProduct.ProductKey
GROUP BY CUBE (DimDate.Year, DimStore.City, DimProduct.ProductID);
