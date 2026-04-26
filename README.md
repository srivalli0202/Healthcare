### **Healthcare Data_360: Medallion Architecutre pipeline**

### **Project Overview**

This project implementations an end-to-end data engineering pipeline in Databricks using the Medallion **Architecture**. It transforms raw healthcare CSV data(Patients, Labs, and Diagnoses) into actionable gold-layer insights for clinical reporting.

### **Architecture Stages**

**-Bronze(Ingestion)**: Raw CSV **files** are ingested from Unity Catalog Volumes into Delta tables with schema enforcement.

**-Gold (Analytics)**: High level aggregates are created to identify high risk patients and top clinic diagnoses.

### **Data Flow Architecture**

```text
[   patient.csv   ]  [ lab_result.csv ]  [ diagnoses.csv ]
           |                   |                 |
           V                   V                 V
-------------------------------------------------------
|                1. BRONZE (Ingest)                   |
| (Files to raw Delta Tables in Unity Catalog Volume) |
-------------------------------------------------------
                           |
                           V
-------------------------------------------------------
|               2. SILVER (Transform)                 |
| (Clean Dates, Join Tables, Apply Abnormal Flags)    |
|       Result: unified_patient_health_record        |
-------------------------------------------------------
                           |
                           V
-------------------------------------------------------
|                3. GOLD (Analytics)                  |
| (Aggregates KPIs: high_risk_patients, top_diagnoses)|
-------------------------------------------------------

```

###**Tech Stack**

**-Platform:** Databricks (Unity Catalog).
**-Language:** PySpark(Python) and Spark SQL.
**-Storage:** Delta Lake.
**-Version Control:** GitHub Integration.

### **Workspace Folders**

-src/**folder:** Contains only 01_bronze_ingestion, 02_silver_transformation, and 03_gold_analytics.

-data/**folder:** Contains your raw CSV samples(optional, as they are already in your Volume).

-sql/**folder:** Any extra SQL scripts you used for manual verification.



