# Amazon Retail ETL Databricks + Azure Data Factory Project — Medallion Architecture with Unity Catalog

## 🚀 Overview
This beginner-friendly end-to-end project demonstrates how to build a **production-ready ETL pipeline** using **Azure Data Factory**, **Azure Databricks**, and **Delta Lake**, following the **Medallion Architecture** (Bronze → Silver → Gold).  
The solution ingests raw data from **Azure SQL Database** and **API sources** into **Azure Data Lake Storage (ADLS Gen2)** using ADF, transforms it with **Databricks PySpark**, and visualizes the final data in **Power BI** — all governed via **Unity Catalog**.

---

## 🧩 Architecture Overview
![Azure Databricks Medallion Architecture](assets/Untitled%20Diagram-Copy%20of%20Databricks%20End%20to%20End%20Project%20Diagram.drawio.png)

---

## 🧱 Azure Data Factory (ADF) Pipeline
![ADF Pipeline Screenshot](assets/Screenshot%202025-10-31%20213845.png)

I designed an **ADF pipeline** to automate data ingestion from multiple **Azure SQL tables** and an **external API** into **Azure Data Lake (Bronze Layer)** using **Copy Data** activities.  
The pipeline orchestrates the data flow sequentially — integrating structured and semi-structured sources into the Delta Lake ecosystem.

### 🔹 Key Features:
- Automated, scheduled ingestion workflow  
- Source-to-target mapping between Azure SQL and ADLS Gen2  
- Parameterized datasets for flexibility and reuse  
- Combined ingestion from both **SQL** and **API** sources

---

## ⚙️ Project Workflow

### 1️⃣ Data Ingestion (Bronze Layer)
- SQL tables (Transaction, Product, Store) loaded from **Azure SQL Database** via ADF Copy Activities  
- Customer data ingested from **external API (customer.json)**  
- All data stored in **Delta format** in the Bronze zone for consistency and lineage tracking

### 2️⃣ Data Cleaning (Silver Layer)
- Performed in **Azure Databricks (PySpark)**  
- Validates schema, removes duplicates, and standardizes data types

### 3️⃣ Data Transformation (Gold Layer)
- Applies business rules, aggregations, and KPI calculations  
- Outputs BI-ready datasets for analysis

### 4️⃣ Data Visualization
- Connected **Power BI** to Gold tables using DirectQuery 

---

## 🧰 Tech Stack

| Category | Tools & Technologies |
|-----------|----------------------|
| Data Integration | Azure Data Factory (ADF) |
| Data Lake | Azure Data Lake Storage Gen2 |
| Processing | Azure Databricks (PySpark, Delta Lake) |
| Governance | Unity Catalog |
| Database | Azure SQL Database |
| API | REST API (JSON-based customer data) |
| Visualization | Power BI |

---

## 🧭 Key Learnings
- Built a **hybrid data pipeline** handling both SQL and API sources  
- Implemented **Medallion Architecture** using Delta Lake  
- Configured **Unity Catalog** for access governance and lineage  
- Automated ingestion using **ADF pipelines** with parameterization  
- Optimized PySpark transformations for performance and scalability

---

## 📒 Notebooks

| Layer | Notebook | Description |
|--------|-----------|-------------|
| 🟤 Bronze | [Data Ingestion into Bronze Layer](notebooks/1.%20Data%20Ingestion%20into%20Bronze%20Layer.ipynb) | Ingests SQL and API data into ADLS Bronze zone |
| ⚪ Silver | [Data Cleaning in Silver Layer](notebooks/2.%20Data%20Cleaning%20in%20Silver%20Layer.ipynb) | Cleans, validates, and standardizes data using PySpark |
| 🟡 Gold | [Data Transformation in Gold Layer](notebooks/3.%20Data%20Transformation%20in%20Gold%20Layer.ipynb) | Aggregates and generates BI-level datasets |

---

## 💾 Data Folder

📁 **`/data`**  
Contains all raw source data files and SQL scripts used for ingestion.

| File Name | Source | Description |
|------------|---------|-------------|
| `SCRIPT SQL.txt` | Azure SQL Database | SQL script used to create and populate tables (`transaction`, `product`, `store`) |
| `customers.json` | REST API | API response data representing customer details |

📌 The **ADF pipeline** fetches these files:  
- SQL-based tables are executed and extracted to ADLS using **ADF Copy Data** activity  
- `customers.json` is retrieved from an **API endpoint** and stored in **Bronze Layer**

---

## 💡 Outcome
✅ End-to-end data pipeline integrating **SQL + API** sources  
✅ Automated and parameterized ADF pipeline for ingestion  
✅ Clean, governed, and scalable **Medallion Architecture** on Databricks  
✅ BI-ready outputs visualized in **Power BI**

---

## 🪜 Folder Description

| Folder | Description |
|---------|-------------|
| `data/` | Contains SQL scripts and API data for ingestion |
| `notebooks/` | Databricks notebooks for each Medallion layer |
| `assets/` | Architecture and pipeline diagrams |
| `README.md` | Project documentation |

---

## 👨‍💻 Author
**Rishikesh Gundla**  
_Senior Business Intelligence Engineer | Data Engineering & Analytics Enthusiast_  
🔗 [LinkedIn](https://www.linkedin.com/in/rishikeshgundla)
