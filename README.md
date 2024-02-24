# Azure Data Engineering Project

## Objective

This project serves as an exploration of various data engineering services within the Azure platform. It is designed to provide insights into the process of migrating an on-premise database to the Azure cloud, specifically for analytical purposes.

![End-to-End Data Engineering On-Premise to Azure](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/66d45565-2fc2-45c0-9460-bed0f051d30e)

## Project Highlights

- Utilized the AdventureWorks dataset and set up an on-premises Microsoft SQL server, safeguarding credentials in Azure Key Vault.
- Executed seamless data transfer from on-premises SQL Server to Azure SQL using Azure Data Factory.
- Implemented Azure Databricks with PySpark for medallion data lake architecture.
- Transferred transformed data to Power BI via Azure Synapse for business intelligence reporting.

## Resource Groups

The project involves working with both Synapse Analytics and Data Factory to gain familiarity and comfort with these Azure services.

![Resource Groups](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/7db59e6f-f3b5-4ed7-a4be-abbabb853c96)

## Data Ingestion

### Source Data

The source data resides in an on-premise SQL server, specifically the [AdventureWorks](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms) database.

![Source Data](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/d21cd2f4-fe3b-47f2-a171-e2e4bff73805)

### Linked Service

Connected the source data with Azure Data Factory using a self-hosted integration runtime for automatic integration, given the database's local location.

![Linked Service](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/bd217eb8-6698-4fb2-af02-cb3662c8e310)
### Pipeline

Implemented a dynamic pipeline using lookup activity to retrieve schema and table names. Conducted copy activities for each table, inserting data into Azure Data Lake's "Bronze" layer.

![Pipeline](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/beaa9f3c-9c2c-4fc4-bc77-a82d66b46632)

### Notebooks

Utilized notebooks for data processing, following the Medallion Architecture to store data in different layers (Bronze, Silver, Gold) for time travel, simplicity, and incremental ETL.

![Notebooks](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/356813f6-73cb-4f3e-819c-a3debeabe039)

### Data Storage

Stored data in Parquet format, an efficient columnar storage system suitable for data analytics and warehousing.

![Data Storage](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/1caa3332-c4c2-4e3e-b247-c922c8af0289)

## Data Loading

In Synapse Analytics, created views for each file stored in Azure Data Lake Storage. Views reflect real-time updates when the underlying data is modified.

![Data Loading](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/95939d44-3427-43fa-9425-56c9b8300e80)
### Stored Procedure

Implemented a pipeline to create views for all tables in the gold layer, enhancing real-time analytics capabilities.

![Stored Procedure](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/a43e3bc7-0d6d-4572-86c1-24a286b05677)

![Stored Procedure](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/65758fe3-aead-4e5a-bbd1-dd4b82515a4e)

### Visualization

Connected Synapse Analytics with Power BI to create interactive visualizations for business intelligence reporting.
![powerbi](https://github.com/espSiyam/On-Prem-SQL-to-Azure---Data-Engineering/assets/42336409/cd3f867b-12cf-4fee-9618-e6970d6379ea)
