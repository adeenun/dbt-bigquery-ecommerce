# E-Commerce Analytics Data Platform

## Objective
This project demonstrates an end-to-end Analytics Engineering workflow using **dbt Core** and **Google BigQuery**. It transforms raw, unstructured e-commerce transactional data into an analytics-ready dimensional model (Star Schema) optimized for Business Intelligence (BI) integrations. 

## Architecture & Data Flow
1. **Raw Data Extraction:** Public e-commerce dataset (`thelook_ecommerce`) ingested into BigQuery.
2. **Staging Layer (dbt):** Cleans raw tables, standardizes data types, and renames columns for consistency.
3. **Marts Layer (dbt):** Joins staging models to create fact and dimension tables tailored for business logic and analytical reporting.

## Tech Stack
* **Data Warehouse:** Google BigQuery
* **Data Transformation:** dbt Core, SQL
* **Data Validation:** dbt tests (Unique, Not Null)
* **Performance Tuning:** BigQuery Table Partitioning

## Key Features
* **SQL-Based Transformations:** Modular and scalable data modeling translating raw tables into performant datasets.
* **Data Governance & Validation:** Enforced data integrity using schema.yml definitions to automate data quality checks.
* **Query Optimization:** Implemented partitioned tables in BigQuery to reduce query latency and processing costs for downstream BI tools like Apache Superset, Metabase, or Looker.
* **Automated Lineage:** Auto-generated dbt documentation and DAGs to track data dependencies.

---

## Local Setup Instructions

**Prerequisites:**
Ensure Python 3.8+ and pip are installed. A Google Cloud Platform (GCP) account with BigQuery access is required.

**1. Clone the repository**
`git clone https://github.com/adeenun/dbt-bigquery-ecommerce.git`

**2. Navigate to the project directory**
`cd dbt-bigquery-ecommerce`

**3. Create a virtual environment**
`python -m venv .venv`

**4. Activate the virtual environment**
`source .venv/bin/activate`

**5. Install dependencies**
`pip install dbt-bigquery`

**6. Configure your profiles.yml**
Set up your GCP Service Account credentials and connect dbt to your BigQuery project.

**7. Run the pipeline**
`dbt run`

**8. Execute data validation tests**
`dbt test`

**9. Generate and view documentation**
`dbt docs generate` followed by `dbt docs serve`

---