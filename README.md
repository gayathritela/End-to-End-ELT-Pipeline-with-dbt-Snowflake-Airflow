# End-to-End ELT Pipeline with dbt, Snowflake & Airflow

This project demonstrates an end-to-end **ELT pipeline** using **dbt**, **Snowflake**, and **Apache Airflow**, orchestrated in a containerized environment via the **Astro CLI**. It reflects a modern data engineering approach—modular, testable, and aligned with production standards.

---

## 🚀 Overview

This project simulates a real-world data transformation workflow using the modern data stack. Here's what it covers:

1. Extract sample data from the **Snowflake TPCH dataset**
2. Transform and model it using **dbt** with **modular SQL layers**
3. Apply **data quality testing** (generic and custom)
4. Schedule and orchestrate runs using **Apache Airflow DAGs**
5. Run locally inside containers using **Astro CLI**

---

## ⚙️ Tools & Technologies

| Tool                  | Purpose                                        |
|-----------------------|------------------------------------------------|
| **Snowflake**         | Cloud data warehouse (source & destination)    |
| **dbt**               | SQL-based modeling, macros, and testing        |
| **Apache Airflow**    | Orchestration engine for scheduling workflows  |
| **Astronomer Cosmos** | Seamless integration between dbt & Airflow     |
| **Docker / Astro CLI**| Containerized local dev environment            |
| **Python**            | DAG construction and operator logic            |

---

## 📁 Project Structure

```bash
├── dags/
│   └── dbt/
│       └── data_pipeline/
│           ├── models/
│           │   ├── staging/
│           │   └── marts/
│           ├── macros/
│           ├── seeds/
│           ├── snapshots/
│           ├── tests/
│           ├── dbt_project.yml
│           └── README.md
│   ├── dbt_dag.py
│   └── .airflowignore
├── include/
├── plugins/
├── tests/
│   └── dags/
├── Dockerfile
├── requirements.txt
├── .astro/
│   └── config.yaml
├── .gitignore
├── .dockerignore
├── airflow_settings.yaml
└── README.md

```  


## ✅ Key Features

- 🧱 **Modular dbt model design** (`staging → intermediate → fact` layers)
- 🔁 **Custom macros** for DRY SQL logic (e.g., discount calculations)
- 🧪 **Integrated data quality testing**
  - **Generic tests**: `unique`, `not_null`, `relationships`, `accepted_values`
  - **Singular tests**: custom checks like `invalid discounts`, `invalid dates`
- ⚙️ **Full DAG orchestration** via Cosmos' `DbtDag` in **Airflow**
- 🐳 **Dockerized development** with **Astro CLI** for a consistent local environment

---

## 🧪 DAG: Orchestration Flow

```
stg_tpch_orders → stg_tpch_line_items_run
                      ↓
            int_order_items_run
                      ↓
     int_order_items_summary_run
                      ↓
               fct_orders
```

Each step corresponds to a **dbt model** or **test** and is executed through **Cosmos’ `DbtDag`** integration inside Airflow.

---

## 🧬 Data Validation Tests

| Test Type | Description                                                |
|-----------|------------------------------------------------------------|
| Generic   | Uniqueness, Not Null, Relationships, Accepted Values       |
| Singular  | Custom SQL tests to validate date ranges and discount logic|

---

## 🎯 Why This Project Matters

This pipeline showcases **core competencies** in modern data engineering and analytics:

- ✅ Real-world use of the **modern data stack**
- 🧱 **Layered dbt model** architecture with `ref()` dependencies
- ⚙️ **Workflow orchestration** using DAGs in Airflow
- 🧪 **Data quality testing** at multiple transformation layers
- 🐳 **Containerized development** with reproducibility across systems

> The pipeline is **modular**, **testable**, **reproducible**, and ready for scaling or adaptation to production-grade environments.

---

## 📸 DAG Execution Snapshot

![image](https://github.com/user-attachments/assets/18dd9b3b-3456-49d1-a9f5-8e8027f3f22d)

