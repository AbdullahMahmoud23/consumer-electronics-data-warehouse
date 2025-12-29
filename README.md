# Consumer Electronics Data Warehouse
## 📄 Project Overview
This project involves the end-to-end design and implementation of a Data Warehouse for a consumer electronics retail company. The goal is to facilitate the analysis of sales performance and inventory management across the company's online and offline channels in the United States.

## 🎯 Objectives
- Dimensional Modeling: Design a Star Schema to efficiently store and retrieve sales data.

- ETL Simulation: Load data into Dimension and Fact tables.

- Advanced Analytics: Utilize advanced SQL aggregations to generate business intelligence reports.

## 🏗️ Schema Design
The data warehouse is structured using a Star Schema architecture:

- Fact Table:

-- FactSales (Transactional sales data)

- Dimension Tables:

-- DimDate (Temporal data for time-based analysis)

-- DimProduct (Product catalog and categorization)

-- DimCustomerSegment (Customer demographics and segmentation)

## 📊 Key Features & Queries
This repository contains SQL scripts to perform the following tasks:

1. DDL & Schema Creation: Defining tables with appropriate primary and foreign keys.

2. Data Loading: Populating the warehouse with sample retail data.

3. OLAP Operations:

-- Grouping Sets: For flexible aggregation across multiple dimensions.

-- ROLLUP: For hierarchical subtotals (e.g., Year > Quarter > Month).

-- CUBE: For cross-dimensional analysis (e.g., Year vs. City vs. Product).

4. Optimization: Creation of Materialized Views to speed up frequent queries like max_sales.

## 📈 Business Insights
The queries in this project are designed to answer critical business questions, such as:

- Total sales revenue per year, quarter, and month by city.

- Sales performance comparisons between different product categories and store locations.

- Identification of high-value product types across different regions.
