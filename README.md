# Data Warehouse Project

Welcome to the **Data Warehouse Project** repository! 
This Project demonstrates a comprehensive data warehousing solution, from building a data warehouse to generating actionable insights. Designed as a portfolio project highlights industry best practices in data engineering.

---
###🏗️ Data Architecture
The data architecture for this project follows Medallion Architecture Bronze, Silver, and Gold layers:
<img width="830" height="561" alt="Dataware House Project drawio" src="https://github.com/user-attachments/assets/d392e57b-d328-45fc-a973-85c75d596408" />


**Bronze Layer**: Stores raw data as-is from the source systems. Data is ingested from CSV Files into SQL Server Database.

**Silver Layer**: This layer includes data cleansing, standardization, and normalization processes to prepare data for analysis.

**Gold Layer**: Houses business-ready data modeled into a star schema required for reporting and analytics.

---

📖 **Project Overview**
This project involves:

Data Architecture: Designing a Modern Data Warehouse Using Medallion Architecture Bronze, Silver, and Gold layers.

ETL Pipelines: Extracting, transforming, and loading data from source systems into the warehouse.

Data Modeling: Developing fact and dimension tables optimized for analytical queries.

Analytics & Reporting: Creating SQL-based reports and dashboards for actionable insights.

---

🎯 This repository is an excellent resource for professionals and students looking to showcase expertise in:

SQL Development

Data Architect

Data Engineering

ETL Pipeline Developer

Data Modeling

Data Analytics

---

🛠️ Important Links & Tools:
Everything is for Free!

Datasets: Access to the project dataset (csv files).

SQL Server Express: Lightweight server for hosting your SQL database.

SQL Server Management Studio (SSMS): GUI for managing and interacting with databases.

Git Repository: Set up a GitHub account and repository to manage, version, and collaborate on your code efficiently.

DrawIO: Design data architecture, models, flows, and diagrams.

Notion: Get the Project Template from Notion

Notion Project Steps: Access to All Project Phases and Tasks.

---

#####🚀 Project Requirements
Building the Data Warehouse (Data Engineering)
###Objective
Develop a modern data warehouse using SQL Server to consolidate sales data, enabling analytical reporting and informed decision-making.

####Specifications

**Data Sources**: Import data from two source systems (ERP and CRM) provided as CSV files.

**Data Quality**: Cleanse and resolve data quality issues prior to analysis.

**Integration**: Combine both sources into a single, user-friendly data model designed for analytical queries.

**Scope**: Focus on the latest dataset only; historization of data is not required.

**Documentation**: Provide clear documentation of the data model to support both business stakeholders and analytics teams.

---
## **General Principles**

- **Naming Conventions**: Use snake_case, with lowercase letters and underscores (`_`) to separate words.
- **Language**: Use English for all names.
- **Avoid Reserved Words**: Do not use SQL reserved words as object names.
- 
## **Table Naming Conventions**

### **Bronze Rules**
- All names must start with the source system name, and table names must match their original names without renaming.
- **`<sourcesystem>_<entity>`**  
  - `<sourcesystem>`: Name of the source system (e.g., `crm`, `erp`).  
  - `<entity>`: Exact table name from the source system.  
  - Example: `crm_customer_info` → Customer information from the CRM system.

### **Silver Rules**
- All names must start with the source system name, and table names must match their original names without renaming.
- **`<sourcesystem>_<entity>`**  
  - `<sourcesystem>`: Name of the source system (e.g., `crm`, `erp`).  
  - `<entity>`: Exact table name from the source system.  
  - Example: `crm_customer_info` → Customer information from the CRM system.

### **Gold Rules**
- All names must use meaningful, business-aligned names for tables, starting with the category prefix.
- **`<category>_<entity>`**  
  - `<category>`: Describes the role of the table, such as `dim` (dimension) or `fact` (fact table).  
  - `<entity>`: Descriptive name of the table, aligned with the business domain (e.g., `customers`, `products`, `sales`).  
  - Examples:
    - `dim_customers` → Dimension table for customer data.  
    - `fact_sales` → Fact table containing sales transactions.  

#### **Glossary of Category Patterns**

| Pattern     | Meaning                           | Example(s)                              |
|-------------|-----------------------------------|-----------------------------------------|
| `dim_`      | Dimension table                  | `dim_customer`, `dim_product`           |
| `fact_`     | Fact table                       | `fact_sales`                            |
| `report_`   | Report table                     | `report_customers`, `report_sales_monthly`   |

## **Column Naming Conventions**

### **Surrogate Keys**  
- All primary keys in dimension tables must use the suffix `_key`.
- **`<table_name>_key`**  
  - `<table_name>`: Refers to the name of the table or entity the key belongs to.  
  - `_key`: A suffix indicating that this column is a surrogate key.  
  - Example: `customer_key` → Surrogate key in the `dim_customers` table.
  
### **Technical Columns**
- All technical columns must start with the prefix `dwh_`, followed by a descriptive name indicating the column's purpose.
- **`dwh_<column_name>`**  
  - `dwh`: Prefix exclusively for system-generated metadata.  
  - `<column_name>`: Descriptive name indicating the column's purpose.  
  - Example: `dwh_load_date` → System-generated column used to store the date when the record was loaded.
 
## **Stored Procedure**

- All stored procedures used for loading data must follow the naming pattern:
- **`load_<layer>`**.
  
  - `<layer>`: Represents the layer being loaded, such as `bronze`, `silver`, or `gold`.
  - Example: 
    - `load_bronze` → Stored procedure for loading data into the Bronze layer.
    - `load_silver` → Stored procedure for loading data into the Silver layer.
