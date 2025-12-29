# Consumer Electronics Sales Data Warehouse

![Status](https://img.shields.io/badge/Status-Completed-success)
![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-blue)
![Type](https://img.shields.io/badge/Type-Data%20Warehousing-orange)

## 📖 Project Overview
This project involves the end-to-end design and implementation of a Data Warehouse for a consumer electronics retail company. The company sells various electronic products through online and offline channels across major cities in the United States.

The goal was to transition from raw operational data to a structured warehouse to analyze sales performance and inventory management.

## 🎯 Learning Objectives
Through this project, I demonstrated the following skills:
* **Dimensional Modeling:** Developed Dimension and Fact tables to organize data for analytical processing.
* **ETL Simulation:** Employed SQL queries to create schemas and load data.
* **Performance Tuning:** Created Materialized Views to optimize query performance for frequent reports.
* **Advanced Aggregation:** Used `GROUPING SETS`, `ROLLUP`, and `CUBE` for multi-level reporting.

## 🏢 Business Scenario & Requirements
The company required a system capable of generating specific high-level reports. The data warehouse was designed to answer:
* Total sales revenue per **year** per **city**.
* Total sales revenue per **month** per **city**.
* Total sales revenue per **quarter** per **city**.
* Total sales revenue per **year** per **product category**.
* Total sales revenue per **product category** per **city**.
* Total sales revenue per **product category** per **store**.

## 🏗️ Data Architecture
The project utilizes a **Star Schema** dimensional model on **PostgreSQL**:

### Fact Table
* **FactSales:** Stores transactional metrics (SalesID, Quantity, TotalAmount).
  * *Foreign Keys:* `DateKey`, `StoreId`, `ProductKey`, `CustomerKey`

### Dimension Tables
* **DimDate:** Attributes for Year, Quarter, Month, Day, Weekday.
* **DimProduct:** Attributes for Product Name, Category, Type, Price.
* **DimCustomerSegment:** Attributes for Segment Name.

## 📂 Project Tasks
The repository allows you to follow the project lifecycle:

### Phase 1: Design & DDL
- [x] **Task 1-4:** Design dimension tables (`DimDate`, `DimProduct`, `DimCustomerSegment`) and fact table (`FactSales`).
- [x] **Task 5-8:** Create the table schemas in PostgreSQL.

### Phase 2: Data Loading
- [x] **Task 9-12:** Load synthetic data into Dimension and Fact tables.

### Phase 3: Analytics & Reporting
- [x] **Task 13:** Create a **Grouping Sets** query.
- [x] **Task 14:** Create a **Rollup** query.
- [x] **Task 15:** Create a **Cube** query (Year, City, ProductID, Average Sales).
- [x] **Task 16:** Create a **Materialized View** (`max_sales`) for performance optimization.

## ℹ️ Dataset & Tools
* **Database:** PostgreSQL
* **Data Source:** This project uses a programmatically created (synthetic) dataset designed specifically for educational simulation of retail scenarios.

## 📂 Data Sources
The project uses the following datasets for the dimension and fact tables. You can download the raw CSV files using the links below:

* **DimDate:** [Download DimDate.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/-omGFpVSWBIZKFSCxUkBwg/DimDate.csv)
    * *Contains:* Calendar dates, years, quarters, months, and weekdays for temporal analysis.
* **DimProduct:** [Download DimProduct.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/Y-76u4An3zb5R6HxxFPabA/DimProduct.csv)
    * *Contains:* Product ID, product names, and categories.
* **DimCustomerSegment:** [Download DimCustomerSegment.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/h_dnxb8yzQyVjeb8oYnm8A/DimCustomerSegment.csv)
    * *Contains:* Customer segmentation data for demographic grouping.
* **FactSales:** [Download FactSales.csv](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/a8kTjzvpdqzOp46ODatyAA/FactSales.csv)
    * *Contains:* Transactional sales data linking dimensions to metrics like Quantity Sold and Price.

## 🚀 How to Run
1. Clone the repository.
2. Ensure you have **PostgreSQL** installed.
3. Execute the `schema_creation.sql` script to set up tables.
4. Run the `data_loading.sql` script.
5. Use `analytical_queries.sql` to generate the reports listed above.

## 👤 Author
**[Abdullah Mahmoud (EL-Yamany)](https://github.com/AbdullahMahmoud23)**
* [LinkedIn](https://www.linkedin.com/in/abdullah-mahmoud-de1344/)
* [Upwork](https://www.upwork.com/freelancers/~018af6686d24e5f7bc?mp_source=share)
