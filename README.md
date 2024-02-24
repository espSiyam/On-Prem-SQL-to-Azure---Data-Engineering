# Azure Data Engineering Project

## Objective

This project serves as an exploration of various data engineering services within the Azure platform. It is designed to provide insights into the process of migrating an on-premise database to the Azure cloud, specifically for analytical purposes.

![End-to-End Data Engineering On-Premise to Azure](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/3c88a9d7-c82d-4561-98ea-dcc74ca689a8/End-to-End_Data_Engineering_On-Premise_to_Azure.jpg)

## Project Highlights

- Utilized the AdventureWorks dataset and set up an on-premises Microsoft SQL server, safeguarding credentials in Azure Key Vault.
- Executed seamless data transfer from on-premises SQL Server to Azure SQL using Azure Data Factory.
- Implemented Azure Databricks with PySpark for medallion data lake architecture.
- Transferred transformed data to Power BI via Azure Synapse for business intelligence reporting.

## Resource Groups

The project involves working with both Synapse Analytics and Data Factory to gain familiarity and comfort with these Azure services.

![Resource Groups](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/bce32fe3-8a38-4b88-827c-3a68d121e379/Untitled.png)

## Data Ingestion

### Source Data

The source data resides in an on-premise SQL server, specifically the [AdventureWorks](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms) database.

![Source Data](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/a742fd7a-035b-4608-b614-c2648b9a7a12/Untitled.png)

### Linked Service

Connected the source data with Azure Data Factory using a self-hosted integration runtime for automatic integration, given the database's local location.

![Linked Service](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/4a725894-2282-4bda-bb35-9d1417fe74ef/Untitled.png)

### Pipeline

Implemented a dynamic pipeline using lookup activity to retrieve schema and table names. Conducted copy activities for each table, inserting data into Azure Data Lake's "Bronze" layer.

![Pipeline](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/c44af6c2-f109-47dc-b2df-40fd59fb9e7e/Untitled.png)

### Notebooks

Utilized notebooks for data processing, following the Medallion Architecture to store data in different layers (Bronze, Silver, Gold) for time travel, simplicity, and incremental ETL.

![Notebooks](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/bdbe5b01-ce15-419a-93e9-f8dd45fe429b/Untitled.png)

### Data Storage

Stored data in Parquet format, an efficient columnar storage system suitable for data analytics and warehousing.

![Data Storage](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/91775c7b-c13e-464a-a229-1b73bc08032e/Untitled.png)

## Data Loading

In Synapse Analytics, created views for each file stored in Azure Data Lake Storage. Views reflect real-time updates when the underlying data is modified.

![Data Loading](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/4c475b23-2c3a-46be-8a2e-b711ebf17174/Untitled.png)

### Stored Procedure

Implemented a pipeline to create views for all tables in the gold layer, enhancing real-time analytics capabilities.

![Stored Procedure](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/e33fe987-eb60-4a61-9c6d-625e6f93bc17/Untitled.png)

![Stored Procedure](https://prod-files-secure.s3.us-west-2.amazonaws.com/9d9ef2ca-8606-4f3b-bdde-ac33ab8dfb4d/db6640ec-8805-47cc-94be-0ac014b8e4e9/Untitled.png)

### Visualization

Connected Synapse Analytics with Power BI to create interactive visualizations for business intelligence reporting.

## Conclusion

This project serves as a comprehensive exploration of Azure data engineering services, demonstrating the migration process from on-premise to Azure cloud. Detailed steps, visualizations, and architecture considerations are provided throughout the readme.

Feel free to explore the detailed implementation in the [GitHub Repository](project_github_link_here).
