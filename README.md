# 🧠 Databricks + Azure Data Factory Project — Medallion Architecture with Unity Catalog

## 🚀 Overview
This end-to-end project demonstrates how to build a **production-ready ETL pipeline** using **Azure Data Factory**, **Azure Databricks**, and **Delta Lake**, following the **Medallion Architecture** (Bronze → Silver → Gold).  
The solution ingests raw data from **Azure SQL Database** into **Azure Data Lake Storage (ADLS Gen2)** using ADF, transforms it with **Databricks PySpark**, and visualizes the final data in **Power BI** — all governed via **Unity Catalog**.

---

## 🧩 Architecture Overview
![Azure Databricks Medallion Architecture](assets/Untitled%20Diagram-Copy%20of%20Databricks%20End%20to%20End%20Project%20Diagram.drawio.png)

---

## 🧱 Azure Data Factory (ADF) Pipeline
![ADF Pipeline Screenshot](assets/Screenshot%202025-10-31%20213845.png)

I designed an **ADF pipeline** to automate data ingestion from multiple **Azure SQL tables** into **Azure Data Lake (Bronze Layer)** using **Copy Data** activities.  
The pipeline orchestrates the flow sequentially — ingesting data from:
- 🧾 **Transaction**
- 📦 **Product**
- 🏬 **Store**
- 👤 **Customer**

Each step writes to **ADLS Gen2 in Parquet/Delta format**, enabling downstream Databricks processing.

### 🔹 Key Features:
- Automated, scheduled ingestion workflow  
- Source-to-target mapping between Azure SQL and ADLS Gen2  
- Schema drift handling and error management  
- Dynamic dataset parameterization for reusable pipelines

---

## ⚙️ Project Workflow

### 1️⃣ Data Ingestion (Bronze Layer)
- Automated ingestion via **ADF Copy Activities**
- Data stored in **Delta format** in Bronze zone for traceability

### 2️⃣ Data Cleaning (Silver Layer)
- Performed in **Azure Databricks (PySpark)**
- Data validated, deduplicated, and standardized

### 3️⃣ Data Transformation (Gold Layer)
- Applied business logic, aggregations, and KPI creation
- Gold datasets optimized for BI consumption

### 4️⃣ Data Visualization
- Connected **Power BI** to Gold tables using DirectQuery
- Created dashboards with DAX-based measures and visual analytics

---

## 🧰 Tech Stack

| Category | Tools & Technologies |
|-----------|----------------------|
| Data Integration | Azure Data Factory (ADF) |
| Data Lake | Azure Data Lake Storage Gen2 |
| Processing | Azure Databricks (PySpark, Delta Lake) |
| Governance | Unity Catalog |
| Database | Azure SQL Database |
| Visualization | Power BI (Data Modeling, DAX) |

---

## 🧭 Key Learnings
- Built an **end-to-end data pipeline** across Azure services  
- Implemented **Medallion Architecture** (Bronze, Silver, Gold)  
- Configured **Unity Catalog** for data governance and lineage  
- Designed **ADF pipelines** for automated ingestion and error handling  
- Practiced **ETL design, schema validation, and BI integration**

---

## 📒 Notebooks

| Layer | Notebook | Description |
|--------|-----------|-------------|
| 🟤 Bronze | [Data Ingestion into Bronze Layer](notebooks/1.%20Data%20Ingestion%20into%20Bronze%20Layer.ipynb) | Ingests data from Azure SQL into ADLS via ADF |
| ⚪ Silver | [Data Cleaning in Silver Layer](notebooks/2.%20Data%20Cleaning%20in%20Silver%20Layer.ipynb) | Cleans, validates, and deduplicates data using PySpark |
| 🟡 Gold | [Data Transformation in Gold Layer](notebooks/3.%20Data%20Transformation%20in%20Gold%20Layer.ipynb) | Applies business aggregations and generates KPIs |

---

## 💡 Outcome
✅ Automated end-to-end data pipeline using ADF + Databricks  
✅ Secure, governed, and scalable architecture  
✅ Power BI dashboards built on optimized Gold layer data

---

## 🪜 Folder Description

| Folder | Description |
|---------|-------------|
| `notebooks/` | Databricks notebooks for each Medallion layer |
| `assets/` | Contains ADF and architecture diagrams |
| `README.md` | Project documentation |
| `LICENSE` | Optional open-source license |

---

## 👨‍💻 Author
**Rishikesh Gundla**  
_Senior Business Intelligence Engineer | Data Engineering & Analytics Enthusiast_  
🔗 [LinkedIn](https://www.linkedin.com/in/rishikeshgundla)
