# databricks-pipeline
# Azure Databricks Data Engineering Pipeline

## 📌 Project Overview

This project demonstrates an end-to-end data engineering pipeline using
Azure Databricks, PySpark, ADLS Gen2, GitHub, and GitHub Actions.

The pipeline processes raw data from the Bronze layer and performs
transformations to create Silver and Gold datasets using PySpark.

## 🏗️ Architecture

ADLS Gen2
   ↓
Bronze Layer
   ↓
Azure Databricks
   ↓
PySpark Transformations
   ↓
Silver Layer
   ↓
Gold Layer

GitHub
   ↓
Databricks Git Integration
   ↓
GitHub Actions CI

## 🛠️ Technologies Used

- Azure Databricks
- PySpark
- Apache Spark
- Azure Data Lake Storage Gen2 (ADLS Gen2)
- Delta Lake
- GitHub
- GitHub Actions
- Python

## 🔄 Pipeline Process

### 1. Data Storage

Raw CSV data is stored in Azure Data Lake Storage Gen2
under the Bronze layer.

### 2. Data Processing

Azure Databricks is used to read the Bronze data using PySpark.

Data is cleaned and transformed using Spark DataFrames.

### 3. Silver Layer

The transformed and cleaned data is stored in the Silver layer.

### 4. Gold Layer

Business-ready data is generated in the Gold layer for downstream
analytics and reporting.

## 🔐 Secure Storage Access

Azure Storage credentials are not hard-coded in the notebook.

Databricks Secrets are used to securely retrieve the Azure Storage
access key.

```python
storage_key = dbutils.secrets.get(
    scope="azure-storage",
    key="storage-key"
)
