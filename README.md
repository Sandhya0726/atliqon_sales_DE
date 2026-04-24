# AtliQon Sales Data Engineering Project
### End-to-End Databricks Pipeline | Medallion Architecture | Incremental Processing | Dashboarding

## Project Overview

This project is an end-to-end **Data Engineering pipeline built on Databricks** for the fictional company **AtliQon**, focusing on sales data processing, transformation, and analytics.

The pipeline follows the **Medallion Architecture (Bronze → Silver → Gold)** and includes:
- Full load + incremental processing
- Dimensional modeling (star schema)
- Data orchestration using Databricks Jobs
- Denormalized analytical views
- Interactive dashboard creation
- AI-powered insights using Databricks Genie

---

## Project Structure

```
consolidated_pipeline/
│
├── 01_setup/
│ ├── 01-setup_catalog.ipynb
│ ├── 02_date_table_creation.ipynb
│
├── 02_dimension_data_processing/
│ ├── 01_customers_sb.ipynb
│ ├── 02_products_sb.ipynb
│ ├── 03_pricing_sb.ipynb
│ └── utilities.ipynb
│
├── 03_fact_data_processing/
│ ├── 01_full_load_fact.ipynb
│ ├── 02_incremental_load_fact.ipynb
│ ├── 03_fact_increment_parent.db...
│ └── 04_denormalized_view.dbque...
│
├── assets/
│ ├── image.png
│ └── project_architecture.png
│
├── dashboard/
│ ├── AtliQon Sales Insights.lvdash...
│ ├── dashboard_image_01.png
│ └── dashboard_image_02.png
│
├── orchestration/
│ └── fmcg_incremental_update_job.yml
│
└── README.md
```

---

## Tech Stack

- Databricks (Unified Analytics Platform)
- Apache Spark (PySpark)
- Delta Lake
- SQL (Databricks SQL)
- YAML (Job Orchestration)
- Medallion Architecture
- Databricks Dashboards
- Genie AI (Databricks AI Assistant)

---

## Project Architecture

<p align="center">
<img src="consolidated_pipeline/assets/project_architecture.png" />
</p>

This architecture represents a Medallion-based pipeline using Bronze, Silver, and Gold layers for scalable data processing in Databricks.

---

## Data Architecture Overview

### Layers

#### 1. Setup Layer (`01_setup`)
- Catalog creation
- Date dimension table creation
- Base environment configuration

---

#### 2. Dimension Layer (`02_dimension_data_processing`)
Handles all master data:

- Customers dimension
- Products dimension
- Pricing (gross price)
- Utility functions for reusable logic

---

#### 3. Fact Layer (`03_fact_data_processing`)
Core transactional processing:

- Full load of fact data
- Incremental load using **MERGE (UPSERT) logic**
- Parent-child data merging
- Creation of **denormalized analytical view**

---

## Data Pipeline Flow

1. **Setup Catalog & Tables**
2. **Load & Process Dimension Tables**
3. **Full Load Fact Table**
4. **Incremental Updates (Upsert Logic)**
5. **Merge with Parent Fact Data**
6. **Create Denormalized View for Analytics**
7. **Dashboard Visualization**

---

## Incremental Load Strategy

- Implemented using **Delta Lake MERGE operation**
- Ensures:
  - New records are inserted
  - Existing records are updated
- Prevents duplicate data
- Optimized for production-like pipelines

---

## Dashboard

Built inside **Databricks SQL Dashboard**

### Insights include:
- Sales trends over time
- Revenue analysis
- Product performance
- Customer segmentation

### Dashboard Assets:
- dashboard_image_01.png
- dashboard_image_02.png
- AtliQon Sales Insights dashboard

## Dashboard Preview:

The final dashboard was built using Databricks SQL for business insights.

<p align="center">
  <img src="consolidated_pipeline/dashboard/dashboard_image_01.png" width="900"/>
</p>
<p align="center">
  <img src="consolidated_pipeline/dashboard/dashboard_image_02.png" width="900"/>
</p>

---

## AI Integration (Genie in Databricks)

- Used Databricks **Genie AI**
- Enables natural language queries on sales data
- Helps in faster insights generation
- Improves accessibility for non-technical users

---

## Key Features

✔ Medallion Architecture implementation  
✔ Full + Incremental data processing  
✔ Delta Lake MERGE (Upsert logic)  
✔ Star schema dimensional modeling  
✔ Denormalized analytical table  
✔ Databricks Job orchestration (YAML-based)  
✔ Interactive BI dashboard  
✔ AI-powered analytics using Genie  

---

## Orchestration

- Pipeline automated using Databricks **Jobs (YAML configuration)**
- Handles task dependencies and execution order
- Ensures reliable end-to-end data flow

<p align="center">
  <img src="consolidated_pipeline/assets/image.png" width="900"/>
</p>

---

## Assets

The `assets/` folder contains:
- Project architecture diagram
- Supporting images for documentation

---

## Outcome

This project demonstrates a **real-world Data Engineering pipeline** that is:

- Scalable
- Modular
- Production-like
- Analytics-ready

It successfully delivers:
- Clean data model
- Incremental processing system
- Business-ready dashboard
- AI-enabled analytics layer

---

## Author

**Sandhya Neupane**  
Data Engineering | Data Analyst | Databricks | PySpark
