# F1 Race Analytics Platform

This project demonstrates how to build a **data engineering pipeline** on Azure Databricks using Formula 1 data from the [FastF1](https://docs.fastf1.dev/) Python library.

## 🚀 Project Overview
- Ingest Formula 1 race schedule, lap timings, telemetry, and results.
- Store raw and processed data in **Delta Lake** following the **Medallion Architecture** (Bronze → Silver → Gold).
- Use **Databricks Jobs** for orchestration and **Databricks SQL** for dashboards.
- Organize project with proper folder structure and notebooks.


## 🛠️ Tech Stack
- **Azure Databricks** (PySpark, Delta Lake, Unity Catalog, Jobs, SQL)
- **Azure Data Lake Storage Gen2**
- **FastF1** (Python library for F1 data)
- **GitHub** (version control and CI/CD later)

## 📅 Development Plan
We follow an incremental plan:
1. Day 1: Setup repo, test FastF1, create catalog/schemas.
2. Day 2: Ingest raw data → Bronze.
3. Day 3: Clean/transform data → Silver.
4. Day 4: Aggregates → Gold.
5. Day 5: Orchestration with Jobs.
6. Day 6: Visualization.
7. Day 7: Documentation + Enhancements.

## ⚡ Getting Started
### Prerequisites
- Databricks Workspace + Cluster
- GitHub account connected to Databricks
- ADLS storage configured
