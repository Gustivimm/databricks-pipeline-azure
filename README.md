# Databricks Azure Pipeline

A hands-on sample repository for building end‑to‑end ETL pipelines using **Microsoft Azure**, **Databricks**, and **Azure Data Factory** — developed as part of an Alura course.

## 📂 Project Overview

This project demonstrates a multi‑layer data processing architecture:

- **Bronze layer**: Raw ingestion of source data.
- **Silver layer**: Cleaned, validated, and transformed data.
- **(Optional Gold layer)**: For analytics or BI consumption.

Key components:

- **Azure Data Factory** orchestrating data workflows.
- **Azure Databricks** executing ingestion (Auto Loader) and transformation (Bronze → Silver) using Python/SQL.
- Optionally, Databricks Workflows schedule and manage task dependencies. :contentReference[oaicite:1]{index=1}

## 🚀 Prerequisites

- Azure subscription with:
  - Databricks workspace (Unity Catalog-enabled, serverless or all-purpose compute)
  - Azure Data Factory instance
- GitHub account (for integration with Databricks Repos or pipelines)
- Alura platform environment (for course guidance and exercises)

## 🧱 Architecture & Layers

1. **Data ingestion (Bronze)**  
   - Use Databricks Auto Loader to stream ingested files into raw Delta tables.

2. **Transformation (Silver)**  
   - Clean and validate data using Databricks notebooks or DLT pipelines.

3. **Orchestration**  
   - Azure Data Factory pipelines trigger Databricks jobs:
     - **Bronze ingestion**
     - **Silver transformation**
   - Databricks Workflows enable task sequencing, retries, and scheduling. :contentReference[oaicite:2]{index=2}

4. **Scheduling & Monitoring**  
   - Use ADF triggers, Databricks job schedules/workflows, and integration notifications for observability.

## 🛠️ Getting Started

1. **Clone the repo**  
    ```bash
    git clone https://github.com/Gustivimm/databricks-pipeline-azure.git
    cd databricks-pipeline-azure
    ```

2. **Setup in Databricks**  
   - Import notebooks (e.g. `bronze_ingest.py`, `silver_transform.py`) via Databricks Repos or manually.
   - Configure Auto Loader in the Bronze notebook.

3. **Deploy Azure Data Factory pipelines**  
   - Import or recreate ADF pipelines from `adf/` folder.
   - Ensure linked services point to your ADLS, Databricks workspace, and storage.

4. **Create Databricks jobs / Workflows**  
   - Define tasks: Bronze → Silver.
   - Set triggers (schedule or event-based).

5. **Run end‑to‑end**  
   - Ingest source files (e.g. JSON/CSV) into ADLS.
   - ADF triggers Databricks ingestion job.
   - Transformation job populates Silver tables.
   - Monitor via Azure and Databricks dashboards.

## 🔧 Folder Structure

├── adf/ # Azure Data Factory JSON definitions
├── notebooks/
│ ├── bronze_ingest.py # Ingestion logic with Auto Loader
│ └── silver_transform.py # Data cleaning & validation
├── workflows/ # Databricks job / workflow definitions
├── requirements.txt # Python libraries (e.g., pyspark, dlt)
└── README.md

## 🧠 Course Context (Alura)

This repository supports the Alura course on Azure ETL with Databricks:

1. Students learn how to ingest and transform data across Bronze and Silver layers.
2. Hands‑on exercises integrate Azure Data Factory, Databricks, and Delta Lake.
3. Focus on real‑world architecture, orchestration patterns, and best practices for reliability and monitoring.
