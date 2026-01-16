# Event-Driven Transactional Sales Data ETL Pipeline on Azure

## 📖 Overview

This project implements an **event-driven, end-to-end ETL pipeline for transactional sales data** using **Azure Data Factory (ADF)** and **Azure Blob Storage**.

Whenever a new transactional sales CSV file is uploaded to the source storage container, a **Storage Event Trigger** automatically activates the pipeline. The pipeline dynamically identifies and processes incoming files, applies transformations using **ADF Mapping Data Flows**, and delivers **analytics-ready sales datasets** to the destination storage layer.

The project simulates a real-world data engineering use case involving **credit card transaction data (Visa, Mastercard, Amex)**, including filtering, enrichment, and aggregation of sales metrics.

---

## 🏗️ Architecture Overview

**High-Level Flow:**

1. CSV file uploaded to Source Blob Storage  
2. Storage Event Trigger activates the pipeline  
3. Metadata-driven file validation and selection  
4. Data transformation using Mapping Data Flows  
5. Curated data written to Destination Blob Storage  

📷 *Architecture / Flow Diagram*  
![Architecture Diagram](images/architecture.png)

---

## ⚙️ Technologies Used

- Azure Data Factory  
- Azure Blob Storage  
- Storage Event Triggers  
- ADF Mapping Data Flows  
- CSV-based Transactional Sales Data  

---

## 🔄 Pipeline Workflow

### 1️⃣ Event-Based Trigger

The pipeline is automatically triggered whenever a new CSV file is added to the source Blob Storage container, enabling fully automated ingestion without manual intervention.

---

### 2️⃣ Metadata-Driven File Processing

- **Get Metadata** retrieves file details dynamically  
- **ForEach** iterates over incoming files  
- **If Condition** validates and filters eligible CSV files  


---

### 3️⃣ Pipeline Orchestration

- Modular pipeline design using **Execute Pipeline** activities  
- Enables clean separation of ingestion, transformation, and loading logic  

---

### 4️⃣ Data Transformation (ADF Mapping Data Flow)

The Mapping Data Flow performs the following transformations on transactional sales data:

- Column renaming and schema standardization  
- Filtering invalid or incomplete records  
- Conditional splits based on card type (Visa, Mastercard, Amex)  
- Derived columns for enriched metrics  
- Aggregations to compute sales summaries  


---

### 5️⃣ Data Movement Across Storage Layers

- Raw transactional data ingested from **Source Container**  
- Intermediate outputs stored in **Reporting Container**  
- Final curated datasets written to **Destination Container**  

---

### 6️⃣ Monitoring & Validation

- Pipeline executions monitored using **ADF Monitoring**  
- Debug runs used to validate data flow and logic  
- Ensures reliable and repeatable pipeline execution  

---

## ✅ Key Features

- Event-driven pipeline triggered by file arrival  
- Metadata-driven dynamic file handling  
- Modular and reusable pipeline design  
- Automated end-to-end ETL workflow  
- Analytics-ready transactional sales datasets  
