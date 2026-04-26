### **Healthcare Data_360: Medallion Architecutre pipeline**

### **Project Overview**

This project implementations an end-to-end data engineering pipeline in Databricks using the Medallion **Architecture**. It transforms raw healthcare CSV data(Patients, Labs, and Diagnoses) into actionable gold-layer insights for clinical reporting.

### **Architecture Stages**

**-Bronze(Ingestion)**: Raw CSV **files** are ingested from Unity Catalog Volumes into Delta tables with schema enforcement.

**-Gold (Analytics)**: High level aggregates are created to identify high risk patients and top clinic diagnoses.

### **Data Flow Diagram**

graph TD
    subgraph "External Data"
        A[patient.csv]
        B[lab_result.csv]
        C[diagnoses.csv]
    end

    subgraph "Databricks Unity Catalog"
        D[(Bronze Volume: raw_files)]
        E[(Silver Schema: Cleaned)]
        F[(Gold Schema: Analytics)]
    end

    A & B & C -->|Ingest| D
    D -->|Transform & Join| E
    E -->|Aggregate KPIs| F

    style D fill:#f96,stroke:#333,stroke-width:2px
    style E fill:#69f,stroke:#333,stroke-width:2px
    style F fill:#9f6,stroke:#333,stroke-width:2px

**Tech Stack**

**-Platform:** Databricks (Unity Catalog).
**-Language:** PySpark(Python) and Spark SQL.
**-Storage:** Delta Lake.
**-Version Control:** GitHub Integration.

### **Workspace Folders**

-src/**folder:** Contains only 01_bronze_ingestion, 02_silver_transformation, and 03_gold_analytics.

-data/**folder:** Contains your raw CSV samples(optional, as they are already in your Volume).

-sql/**folder:** Any extra SQL scripts you used for manual verification.


