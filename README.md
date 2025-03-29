# End-to-End ELT Pipeline with dbt, Snowflake & Airflow

This project demonstrates an end-to-end **ELT pipeline** using **dbt**, **Snowflake**, and **Apache Airflow**—orchestrated and containerized with the **Astro CLI**. It reflects a modern data engineering workflow: raw data ingestion, transformation, testing, and scheduling through automated DAGs.

---

## 🚀 Overview

The goal of this project is to showcase how to:

- Extract sample data from **Snowflake Sample TPCH Dataset**
- Transform it using **dbt models and macros**
- Test and validate outputs using **dbt tests**
- Schedule the DAG with **Apache Airflow**
- Run locally with **Astro CLI** (Dockerized environment)

This is a real-world, modular pipeline that is scalable, testable, and production-ready.

---

## ⚙️ Tools & Technologies

| Tool                | Purpose                             |
|---------------------|-------------------------------------|
| **Snowflake**       | Cloud data warehouse (data source + target) |
| **dbt**             | SQL-based transformation & testing |
| **Astronomer Cosmos** | Integration between dbt & Airflow |
| **Apache Airflow**  | Workflow orchestration |
| **Docker / Astro CLI** | Local containerized environment |
| **Python**          | DAG definition and orchestration |

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
