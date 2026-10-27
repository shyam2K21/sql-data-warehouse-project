# SQL Data Warehouse Project

A modern data warehousing solution built with **Microsoft SQL Server**, designed to integrate CRM and ERP data, implement ETL pipelines, improve data quality, and enable business-driven analytics.

## 📌 Project Overview

This project demonstrates the end-to-end development of a modern data warehouse, from raw data ingestion to analytical reporting. Data from two source systems — CRM and ERP — is consolidated into a centralized repository, transformed into a consistent format, and structured for efficient querying and business intelligence.

The implementation follows the **Medallion Architecture**, using Bronze, Silver, and Gold layers to organize data processing, improve data quality, and deliver analysis-ready datasets.

The repository contains the source datasets, SQL scripts, project documentation, setup instructions, and data quality validation queries required to understand and reproduce the solution.

**Getting Started:** If you are setting up the project for the first time, begin with the setup guide in the `00_setup` directory.

---

## 🏗️ Data Architecture

The warehouse follows a three-layer Medallion Architecture.

### 1. Bronze Layer — Raw Data Ingestion
- Imports source data from CRM and ERP CSV files into SQL Server.
- Preserves the original structure of the incoming data.
- Provides a raw-data foundation for subsequent transformations.
- Uses SQL stored procedures to organize and execute data loading.

### 2. Silver Layer — Data Cleansing and Transformation
- Handles missing values, duplicates, and inconsistent records.
- Standardizes formats, data types, and business attributes.
- Resolves data quality issues across the source systems.
- Integrates and prepares datasets for downstream analytical use.

### 3. Gold Layer — Business-Ready Data
- Organizes transformed data into a dimensional model.
- Implements fact and dimension tables using a **Star Schema**.
- Supports efficient analytical queries and reporting.
- Provides a consistent data layer for evaluating sales, customer behavior, and product performance.

---

## 🎯 Project Objectives

The project focuses on the following key areas:

1. **Data Warehouse Design:** Establish a structured warehouse architecture using Bronze, Silver, and Gold layers.
2. **ETL Development:** Build SQL-based pipelines to extract, load, and transform data from CRM and ERP source files.
3. **Data Quality Management:** Identify and resolve data inconsistencies before making datasets available for analysis.
4. **Dimensional Modeling:** Design fact and dimension tables to support analytical workloads.
5. **Data Integration:** Consolidate data from multiple operational systems into a unified analytical model.
6. **SQL Analytics:** Develop queries that uncover business insights and support data-driven decisions.
7. **Documentation and Testing:** Document the architecture, requirements, and data model, and validate the quality of transformed data.

---

## 📂 Repository Structure

```text
sql-data-warehouse-project/
│
├── 00_setup/
│   └── Environment setup guide and Docker configuration
│
├── 01_datasets/
│   ├── source_crm/
│   │   └── CRM source CSV files
│   └── source_erp/
│       └── ERP source CSV files
│
├── 02_docs/
│   └── Requirements, architecture diagrams, and documentation
│
├── 03_scripts/
│   ├── init_database.sql
│   ├── bronze/
│   │   └── Raw data ingestion scripts
│   ├── silver/
│   │   └── Data cleansing and transformation scripts
│   └── gold/
│       └── Dimensional modeling and analytical table scripts
│
└── 04_tests/
    └── Data quality and validation scripts for Silver and Gold
```

### Directory Guide

| Directory | Purpose |
|---|---|
| `00_setup` | Instructions for configuring the SQL Server environment and initializing the project. |
| `01_datasets` | Contains six source CSV files distributed across the CRM and ERP systems. |
| `02_docs` | Stores project specifications, data models, architecture diagrams, and supporting notes. |
| `03_scripts` | Contains SQL scripts organized by processing layer. |
| `04_tests` | Includes validation queries for checking data quality and consistency. |

---

## ⚙️ Technology Stack

- **Database:** Microsoft SQL Server
- **Query Language:** T-SQL
- **Database Management:** SQL Server Management Studio (SSMS)
- **Data Sources:** CRM and ERP CSV files
- **Data Processing:** SQL-based ETL pipelines and stored procedures
- **Data Architecture:** Medallion Architecture
- **Data Modeling:** Dimensional modeling and Star Schema
- **Documentation and Diagrams:** Markdown and draw.io
- **Version Control:** Git and GitHub

---

## 🚀 Getting Started

### Prerequisites

Before running the project, ensure that you have:

- Microsoft SQL Server installed and running.
- SQL Server Management Studio (SSMS), or another compatible SQL client.
- Git installed to clone the repository.
- The project source datasets available locally.

For macOS users, refer to the setup documentation for the supported Docker-based environment.

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
cd sql-data-warehouse-project
```

Replace `<your-repository-url>` with the URL of your GitHub repository.

### Step 2: Configure the Environment

Open the `00_setup` directory and follow the setup guide to configure SQL Server and prepare the database environment.

### Step 3: Initialize the Database

Execute the following script in SQL Server Management Studio:

```sql
03_scripts/init_database.sql
```

Run the script using SSMS rather than entering the file path as a SQL statement.

### Step 4: Configure Source File Paths

The Bronze loading procedure expects the datasets at the following location by default:

```text
C:\sql\dwh_project\01_datasets\
```

Either place the project datasets in the expected directory or update the six source file paths in:

```text
03_scripts/bronze/proc_load_bronze.sql
```

Ensure that SQL Server has the required permissions to access the files.

### Step 5: Execute the ETL Pipeline

Run the SQL scripts in the intended processing order:

1. **Bronze:** Load the raw CRM and ERP datasets.
2. **Silver:** Clean, standardize, and integrate the ingested data.
3. **Gold:** Build the analytical tables and dimensional model.

Follow the script dependencies and execution instructions documented in the repository.

### Step 6: Validate the Results

Execute the relevant scripts in `04_tests` to verify the quality and consistency of the Silver and Gold datasets.

---

## 📊 Business Intelligence and Analytics

The data warehouse provides a foundation for SQL-based analysis across three major business areas.

### Customer Behavior
- Analyze customer attributes and purchasing patterns.
- Understand customer distribution and sales contribution.
- Identify trends that can support customer-focused business decisions.

### Product Performance
- Evaluate product-level sales performance.
- Compare sales across product categories and product lines.
- Identify high-performing products and opportunities for improvement.

### Sales Trends
- Analyze sales performance across available time periods.
- Compare sales across customers and products.
- Calculate relevant business metrics to support performance monitoring.

These analyses demonstrate how integrated, high-quality data can be transformed into actionable business insights.

---

## 📋 Project Requirements

### Data Engineering

**Objective:** Develop a modern SQL Server data warehouse that consolidates sales-related data from CRM and ERP systems for analytical workloads.

**Functional requirements:**

- **Source Integration:** Ingest data from two operational systems provided as CSV files.
- **Data Transformation:** Clean and standardize the source data before integrating it.
- **Data Quality:** Address inconsistencies and validate the transformed datasets.
- **Unified Data Model:** Combine data from both systems into a consistent analytical structure.
- **Data Scope:** Focus on the latest available dataset; historical tracking and historization are outside the current scope.
- **Documentation:** Maintain clear documentation of the architecture, transformations, and dimensional model.

### Analytics and Reporting

**Objective:** Use SQL queries to extract business insights from the curated warehouse.

The analytical scope includes:

- Customer behavior and purchasing patterns.
- Product performance and sales contribution.
- Sales trends and business performance metrics.

---

## 🔗 Resources

- [GitHub](https://github.com/) — Version control and project hosting.
- [draw.io](https://www.drawio.com/) — Architecture and data model diagrams.
- [Notion Templates](https://www.notion.com/templates/sql-data-warehouse-project) — Project planning resources.
- [Project Documentation and Roadmap](https://thankful-pangolin-2ca.notion.site/SQL-Data-Warehouse-Project-16ed041640ef80489667cfe2f380b269?pvs=4) — Project phases and implementation tasks.

For installation instructions and environment-specific troubleshooting, refer to the files in `00_setup`.

---

## 🧪 Testing and Data Validation

Data quality checks are included to help ensure that the transformed datasets are suitable for analytical use.

The test scripts focus on:

- Data completeness and consistency.
- Duplicate and invalid record detection.
- Validation of key relationships between tables.
- Consistency of the Silver and Gold layer outputs.

Run the relevant validation scripts after the pipeline completes to identify potential data quality issues.

---

## 📈 Key Learning Outcomes

This project provides practical experience in:

- Designing a modern data warehouse from the ground up.
- Implementing layered data processing with Medallion Architecture.
- Developing SQL-based ETL pipelines and stored procedures.
- Cleaning and integrating data from multiple source systems.
- Designing fact tables, dimension tables, and Star Schemas.
- Writing SQL queries for business analysis.
- Documenting database architecture and validating data quality.

---

## 📄 License

This project is distributed under the [MIT License](LICENSE). You may use, modify, and distribute the code in accordance with the license terms.

---

## 👋 About Me

Hi, I'm **Shyam Sai**, a data professional with experience in analytics, machine learning, and natural language processing. I enjoy solving complex business problems through data engineering, AI, and analytical solutions.

Through projects like this, I aim to strengthen my expertise in SQL, data warehousing, data modeling, and end-to-end data pipeline development while building practical solutions that bridge raw data and business insights.

**Let's connect and build data-driven solutions!**
