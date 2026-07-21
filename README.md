# Enterprise REST API Medallion Architecture with Microsoft Fabric

## Project Overview

This project demonstrates an end-to-end REST API ingestion and analytics solution built using **Microsoft Fabric**, **Apache Spark**, **Delta Lake**, and the **Medallion Architecture**.

Earthquake event data is continuously retrieved from the **United States Geological Survey (USGS) Earthquake API**, ingested into a Microsoft Fabric Lakehouse, validated through Bronze, Silver, and Gold layers, and prepared for downstream business reporting through a Semantic Model and Power BI.

Although this implementation uses publicly available earthquake data, the architecture is intentionally designed as a reusable engineering pattern for enterprise REST API integrations. The same framework can be adapted for operational systems, ERP platforms, IoT devices, financial applications, weather services, or other external data sources.

The project demonstrates modern analytics engineering practices including API integration, layered data architecture, Spark transformations, orchestration, semantic modeling, and business intelligence.

---

# Business Problem

Organizations increasingly depend on external REST APIs to support reporting, operational monitoring, forecasting, and decision-making.

Common challenges include:

* Ingesting external data reliably
* Preserving raw source data
* Validating and cleansing incoming records
* Building analytics-ready datasets
* Supporting self-service reporting
* Creating a single source of truth

This project demonstrates how Microsoft Fabric can be used to build a scalable ingestion framework that separates raw, validated, and curated data into independent architectural layers.

---

# Solution Architecture

```text
USGS REST API
        │
        ▼
Microsoft Fabric Pipeline
        │
        ▼
Landing
        │
        ▼
Bronze Layer
(Raw API Data)
        │
        ▼
Silver Layer
(Data Validation & Standardization)
        │
        ▼
Gold Layer
(Business-Ready Data)
        │
        ▼
Warehouse / Semantic Model
        │
        ▼
Power BI
```

---

# Project Workflow

The solution follows a modern Medallion Architecture workflow.

1. Retrieve earthquake event data from the USGS REST API.
2. Store raw JSON responses in the Landing layer.
3. Load raw records into the Bronze layer.
4. Cleanse, standardize, and validate records in the Silver layer.
5. Publish analytics-ready datasets to the Gold layer.
6. Expose curated data through a Semantic Model.
7. Deliver business insights through Power BI.

---

# Microsoft Fabric Components

The project demonstrates integration across several Microsoft Fabric services.

### Data Engineering

* Microsoft Fabric Lakehouse
* Apache Spark Notebooks
* Delta Lake

### Data Integration

* REST API ingestion
* Fabric Data Pipeline
* Parameterized execution

### Analytics

* Semantic Model
* Power BI

---

# Technologies Used

* Microsoft Fabric
* Apache Spark
* PySpark
* Python
* Delta Lake
* REST APIs
* JSON
* SQL
* Power BI

---

# Skills Demonstrated

This project demonstrates experience with:

* REST API integration
* Microsoft Fabric
* Lakehouse architecture
* Medallion Architecture
* Apache Spark
* Delta Lake
* Data engineering
* Data validation
* Analytics engineering
* Semantic modeling
* Business intelligence

---

# Business Value

The architecture demonstrated in this project can be adapted for numerous enterprise use cases, including:

* ERP integration
* Financial reporting
* Operational monitoring
* Asset management
* Supply chain analytics
* Weather intelligence
* Construction operations
* IoT telemetry
* Environmental monitoring

The focus of this repository is not earthquake analytics itself, but the engineering framework used to transform external API data into reliable analytical datasets.

---

# Lessons Learned

This project reinforced several analytics engineering principles.

* Preserve raw source data before transformation.
* Separate ingestion, validation, and business logic into independent layers.
* Build reusable API ingestion patterns rather than one-off pipelines.
* Persist curated datasets for downstream analytics.
* Design data platforms to support multiple reporting tools through a shared semantic layer.

---

# Future Enhancements

Potential future improvements include:

* Incremental API ingestion
* Change data detection
* Automated data quality testing
* CI/CD deployment
* Git-based deployment workflows
* Real-time streaming ingestion
* Metadata-driven ingestion framework
* Multi-source API integration

---

# Repository Structure

```text
README.md
notebooks/
pipelines/
sql/
images/
docs/
```

---

# Author

**Devon Johnson**

This repository is part of my Microsoft Fabric and Analytics Engineering portfolio and demonstrates an enterprise approach to REST API ingestion, Medallion Architecture, and modern cloud data platform design.
