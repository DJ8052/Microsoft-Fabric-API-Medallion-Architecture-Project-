# Microsoft Fabric Earthquake Analytics (Medallion Architecture)

This repository showcases a complete, end-to-end analytics solution built using **Microsoft Fabric**, following a **Medallion Architecture (Bronze → Silver → Gold)**.

The project ingests real-time earthquake data from the **USGS Earthquake API**, processes it through structured transformation layers, orchestrates execution using **Fabric Data Factory**, and delivers insights through **Power BI**.

---

## Architecture Overview

### Bronze Layer
- Ingests raw earthquake data from the USGS API
- Stores raw JSON in the Fabric Lakehouse
- Parameterized date ingestion
- Designed for both manual execution and pipeline orchestration

### Silver Layer
- Flattens nested JSON structures
- Extracts latitude, longitude, magnitude, significance, and timestamps
- Applies data quality handling and type conversions
- Writes structured Delta tables

### Gold Layer
- Applies business logic and enrichment
- Adds significance classification (Low / Moderate / High)
- Prepares analytics-ready datasets
- Handles platform constraints pragmatically

---

## Orchestration (Fabric Data Factory)

- End-to-end pipeline orchestrates Bronze → Silver → Gold
- Pipeline parameters:
  - `p_start_date`
  - `p_end_date`
- Notebooks are dual-mode:
  - Manual execution for development
  - Pipeline execution for automation
- Daily trigger enabled (no incremental cost)

---

## Reporting (Power BI)

- Gold layer exposed via a semantic model
- Power BI report built on curated Gold data
- Geographic visualization uses latitude and longitude
- DAX used selectively for presentation-level cleanup

---

## Key Design Decisions

### External Library Constraints
Fabric Environments in this tenant did not support external Python libraries (e.g., reverse geocoding).

**Response:**
- Implemented guarded imports and fallback logic
- Avoided brittle or unsupported workarounds
- Used coordinate-based mapping in Power BI
- Deferred non-critical enrichment to the visualization layer

---

## Technologies Used
- Microsoft Fabric
- Lakehouse (Delta)
- Fabric Notebooks (PySpark)
- Fabric Data Factory
- Power BI
- USGS Earthquake API

---

## Why This Project Matters
This project emphasizes:
- Real-world data engineering patterns
- Platform-aware decision making
- Separation of ingestion, transformation, orchestration, and visualization
- Delivering value despite technical constraints
