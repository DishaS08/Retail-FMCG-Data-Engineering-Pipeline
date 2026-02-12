# Retail FMCG Data Engineering Pipeline

## Project Overview
This project implements an end-to-end data engineering pipeline for a retail FMCG company. It processes sales, customer, and product data to provide actionable insights through a dashboard.

## Architecture
The project follows the **Medallion Architecture** using **Databricks** and **Unity Catalog**:
1.  **Bronze Layer**: Raw data ingestion from CSV files.
2.  **Silver Layer**: Cleaned, transformed, and normalized data.
3.  **Gold Layer**: Enriched data organized in a Star Schema (Facts and Dimensions) ready for reporting.

## Tech Stack
-   **Platform**: Databricks
-   **Languages**: Python (PySpark), SQL
-   **Data Modeling**: Star Schema (Fact Orders, Dim Customers, Dim Products, Dim Date)
-   **Orchestration**: Databricks Notebooks

## Project Structure
-   `0_data/`: Contains raw CSV data files for Parent and Child companies (including incremental loads).
-   `1_codes/`: Databricks notebooks for the pipeline:
    -   **Setup**: Catalog/Schema creation and utility functions.
    -   **Dimension Processing**: Handling Customer, Product, and Pricing dimensions.
    -   **Fact Processing**: Full and Incremental loading for Fact Orders.
-   `2_dashboarding/`: SQL queries for data enrinchment (`denormalise_table_query_fmcg.txt`) and final Dashboard PDF.

## Key Features
-   **Incremental Loading**: Handles daily data updates efficiently.
-   **Data Enrichment**: Joins complex datasets to calculate metrics like `total_amount_inr`.
-   **Scalable**: Built on Spark for handling large volumes of FMCG data.
