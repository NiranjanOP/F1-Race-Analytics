# F1 Race Analytics Platform

This project demonstrates how to build a **data engineering pipeline** on Azure Databricks using Formula 1 data from the [FastF1](https://docs.fastf1.dev/) Python library.

---

## 🚀 Project Overview
- Ingest Formula 1 race schedule, lap timings, telemetry, results, weather, and race control messages.
- Store raw and processed data in **Delta Lake** following the **Medallion Architecture**:
  - **Bronze**: Raw ingestion from FastF1 APIs.
  - **Silver**: Cleaned and transformed data with standardized types, flattening, and enriched fields.
  - **Gold**: Aggregated analytics tables for race results, lap performance, telemetry insights, driver standings, and more.
- Implement **incremental ingestion** to fetch only new or updated data.
- Use **Databricks Jobs** and **DLT pipelines** for orchestration.
- Apply **Data Quality (DQ) checks** at each layer to ensure accuracy, completeness, and consistency.
- Organize project with proper folder structure and notebooks for each layer and pipeline.

---

## 🛠️ Tech Stack
- **Azure Databricks**: PySpark, Delta Lake, Unity Catalog, DLT, Jobs, SQL
- **Azure Data Lake Storage Gen2**: Storage for raw, silver, and gold data
- **FastF1**: Python library for F1 data
- **GitHub**: Version control, daily commits for tracking progress
- **Matplotlib / Pandas**: Optional visualizations and intermediate data processing

---

## 📅 Development Plan
We follow a stepwise plan:

**Bronze Layer**
1. Day 1: Setup repository, GitHub, catalog, and schemas.
2. Day 2: Ingest raw data (lap_times, telemetry, weather, session info, session results, race control messages, circuit info) into bronze Delta tables.
3. Day 3: Create remaining bronze tables and validate ingestion.

**Silver Layer**
4. Clean, transform, and standardize data from bronze.
5. Create silver Delta tables (circuit_info, lap_times, telemetry, weather, session_results, session_info, race_control_messages).

**Gold Layer**
6. Build analytical gold tables:
   - `race_results`, `lap_performance`, `race_events`, `telemetry_insights`, `weather_impact`, `season_standings`, `driver_teams`
7. Apply advanced transformations, joins, aggregations, and optimization techniques.

**DLT & Orchestration**
8. Implement **Delta Live Tables (DLT)** pipelines for automated bronze → silver → gold transformations.
9. Add incremental ingestion support in DLT or PySpark notebooks.
10. Schedule daily or event-driven **Databricks Jobs** to refresh tables.

**Data Quality & Monitoring**
11. Apply **DQ checks** at each layer:
    - Null checks, type validation, uniqueness, range checks, session completeness.
12. Maintain **DQ metrics table** for monitoring and alerts.

**Visualization & Insights**
13. Optional dashboards and queries using **Databricks SQL** or visualization libraries.

**Documentation & Enhancements**
14. README, project documentation, code comments, folder structure.

---

## ⚡ Getting Started
### Prerequisites
- Databricks Workspace + Standard/Job Cluster
- GitHub account connected to Databricks
- ADLS Gen2 storage configured with containers for raw, silver, and gold layers
- Python 3.8+ (FastF1 compatible)
- Installed Python libraries: `fastf1`, `pandas`, `matplotlib`, `pyarrow`


### How to Run
1. Clone GitHub repository to Databricks workspace.
2. Set up **Unity Catalog** and Delta tables for bronze, silver, and gold layers.
3. Run ingestion notebooks in order: bronze → silver → gold.
4. Schedule DLT pipelines for automation.
5. Execute DQ notebooks to validate data integrity.
6. Use **Databricks SQL** for analytics dashboards.

---

## 📈 Key Features
- Incremental ingestion for efficiency
- Full bronze → silver → gold medallion architecture
- Delta Live Tables pipelines
- Data quality monitoring and alerts
- Ready for analytics and visualization

---

## 💡 Notes
- Cache FastF1 API responses locally to reduce repeated API calls.
- Store checkpoints for incremental ingestion in a dedicated ADLS folder.
- Keep sensitive credentials out of GitHub (use Databricks secrets).

---

## 📄 References
- [FastF1 Documentation](https://docs.fastf1.dev/)
- [Databricks Delta Lake](https://docs.databricks.com/delta/index.html)
- [Databricks Delta Live Tables](https://docs.databricks.com/delta-live-tables/index.html)
