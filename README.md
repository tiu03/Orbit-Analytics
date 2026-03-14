# Orbit-Analytics
Orbit Analytics: A Containerized Medallion Pipeline using PySpark, dbt, and BigQuery.

---

🏗️ Project Architecture: "The Real-Time Medallion Pipeline"
This project simulates a high-frequency data environment (like e-commerce transactions or ride-sharing events) using a Medallion Architecture (Bronze → Silver → Gold).

## 1. The Tech Stack Breakdown

- **Infrastructure:** **Docker** (to containerize your local Spark environment and Airflow).
    
- **Ingestion & Processing:** **PySpark** on **Databricks** (Community Edition is fine) for heavy lifting and data cleaning.
    
- **Transformation:** **dbt (data build tool)** to manage SQL transformations in your warehouse.
    
- **Storage/Warehouse:** **Google BigQuery** (as your cloud data warehouse) or **Delta Lake**.
    
- **Visualization:** **Tableau** (to showcase the final "Gold" layer insights).
