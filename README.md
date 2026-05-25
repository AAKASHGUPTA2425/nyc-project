# NYC Payroll Data Engineering Pipeline
Project Overview

This project demonstrates the implementation of a complete Azure Data Engineering Pipeline using Azure Data Lake Storage Gen2, Azure Data Factory, Azure Synapse Analytics, and GitHub Integration for processing and analyzing NYC Payroll data.

The workflow includes:

Storing raw files in Azure Data Lake Gen2
Creating SQL tables and external tables
Configuring linked services and datasets
Building dataflows for transformations
Creating pipelines for orchestration
Triggering and monitoring pipeline runs
Generating aggregated payroll summaries
Publishing outputs to Synapse SQL
Integrating with GitHub for version control


#Architecture

Technologies Used
Azure Data Lake Storage Gen2
Azure Data Factory
Azure Synapse Analytics
SQL
GitHub
Azure SQL Database

Project Workflow
1. Data Storage in Azure Data Lake Gen2

The project started with uploading NYC payroll datasets into Azure Data Lake Storage Gen2, which acted as the centralized storage layer for the pipeline. Different files were organized inside storage containers for further processing and transformation. This storage system provided scalable and secure cloud-based storage for the raw payroll datasets.

2. SQL Table Creation

After storing the data, SQL queries were written in Azure Synapse Analytics to create tables and define schemas for payroll datasets. Different tables were created for:

Employee Master
Agency Details
Title Master
NYC Payroll 2020
NYC Payroll 2021
Payroll Summary

These SQL scripts helped organize the raw data into structured relational formats suitable for analytics and transformations.

3. Synapse and Linked Services Configuration

Azure Synapse Analytics was used to create external tables and generate code for the NYC payroll summary process. Linked services were configured between:

Azure Data Lake Storage
Azure SQL Database

These linked services enabled secure connectivity and smooth data transfer between Azure resources.

Dataset Configuration

In Azure Data Factory, datasets were created for both storage files and SQL database tables. Some important datasets included:

agency_ds
empmaster_ds
nyc_payroll2020_ds
nyc_payroll2021_ds
staging
titlemaster_ds
nyc_payroll_summary

These datasets acted as input and output references for pipelines and dataflows.

Dataflows and Transformations

Multiple dataflows were created in Azure Data Factory to perform data transformation and processing operations. The dataflows included:

agencydataflow
employeedataflow
titlemaster_dataflow
nyc_payroll2020dataflow
nyc_payroll2021dataflow
dataflow_summary

These dataflows performed several ETL operations such as:

Data cleaning
Column mapping
Filtering
Aggregation
Data transformation
Loading transformed records into SQL tables

An aggregate dataflow was specifically created to generate the NYC_PAYROLL_SUMMARY, which combined payroll data from multiple years and agencies to calculate summarized payroll statistics.

Pipeline Creation and Execution

Azure Data Factory pipelines were developed to automate the complete ETL workflow. These pipelines executed the dataflows sequentially and managed the movement of data between Azure Storage, SQL Database, and Synapse Analytics.

The pipeline implementation included:

Pipeline debugging
Activity monitoring
Manual pipeline triggering
Execution status tracking

The successful pipeline runs confirmed that all transformation and loading operations were completed correctly.

Final Outputs

The project generated outputs in multiple Azure services:

Storage Account Output

Processed files were successfully stored back into Azure Data Lake Storage Gen2.

SQL Database Output

Transformed payroll records were loaded into Azure SQL Database tables for structured storage and querying.

Synapse Analytics Output

Aggregated payroll summaries were generated successfully in Azure Synapse Analytics. The output included:

Fiscal Year
Agency Name
Total Payroll Amount

These outputs can be used for reporting and business analytics purposes.

GitHub Integration

GitHub was integrated with Azure Data Factory for:

Version control
Collaboration
Backup of pipelines and dataflows
Change tracking

This integration helped maintain project history and improved resource management.

Project Outcomes

This project successfully demonstrates:

End-to-end ETL pipeline implementation
Cloud-based data engineering workflow
Data transformation using Azure Data Factory
Data storage using Azure Data Lake Gen2
Analytics using Azure Synapse
SQL-based payroll processing
GitHub-based version control integration

Overall, the project provides practical experience in modern cloud data engineering and enterprise-level data integration using Microsoft Azure technologies.
