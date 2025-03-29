# End-to-End ELT Pipeline with dbt, Snowflake & Airflow

This project demonstrates an end-to-end **ELT pipeline** using **dbt**, **Snowflake**, and **Apache Airflow**, orchestrated in a containerized environment via the **Astro CLI**. It showcases a modern, testable, and production-aligned data engineering workflow—from raw data ingestion to final reporting layers.

---

## 🚀 Overview

**Pipeline Flow:**

1. Extract sample data from **Snowflake Sample TPCH Dataset**
2. Transform it using **dbt models**, **macros**, and **modular SQL layers**
3. Apply **automated tests** to validate transformations
4. Orchestrate and schedule runs with **Apache Airflow DAGs**
5. Run locally using **Astro CLI (Dockerized Airflow)**

---

## ⚙️ Tools & Technologies

| Tool                | Purpose                                        |
|---------------------|------------------------------------------------|
| **Snowflake**       | Cloud data warehouse (source + target)         |
| **dbt**             | SQL transformations, testing, and lineage      |
| **Apache Airflow**  | Workflow orchestration via DAGs                |
| **Astronomer Cosmos** | Connects dbt projects to Airflow             |
| **Docker / Astro CLI** | Local dev environment for airflow & dbt     |
| **Python**          | DAG and orchestration logic                    |

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



---


✅ Key Features
🧱 Modular dbt model design (staging → intermediate → fact layers)

🔁 Custom macros for DRY SQL logic (e.g., discount calculations)

🧪 Integrated data quality testing:

Generic tests: unique, not_null, relationships, accepted_values

Singular tests: invalid discounts, invalid dates

⚙️ Full DAG orchestration via Cosmos' DbtDag in Airflow

🐳 Dockerized development using Astro CLI for consistent local environment

🧪 DAG: Orchestration Flow
text
Copy
Edit
stg_tpch_orders → stg_tpch_line_items_run
                          ↓
                int_order_items_run
                          ↓
         int_order_items_summary_run
                          ↓
                   fct_orders
Each step corresponds to a dbt model or test and is handled by Cosmos' DbtDag integration inside Airflow.

🧬 Data Validation Tests
Test Type	Description
Generic	Uniqueness, Not Null, Relationships, Accepted Values
Singular	Custom SQL to check date ranges and discount logic
🎯 Why This Project Matters
This project simulates how modern data teams build real pipelines. It reflects critical skills for Data Engineering, Analytics Engineering, and Cloud ETL roles:

✅ Real-world use of the modern data stack

🧱 Layered dbt model design with ref-based dependencies

⚙️ Proficiency in workflow orchestration using DAGs

🧪 Implementation of data quality tests across layers

🐳 Experience with containerized, reproducible environments

The pipeline is modular, testable, reproducible, and ready for scaling or adaptation to production platforms.

📸 DAG Execution Snapshot

🔗 Repository
GitHub: End-to-End-ELT-Pipeline-with-dbt-Snowflake-Airflow

python
Copy
Edit

### ✅ Next Steps (Optional)
Let me know if you'd like me to:
- Add a small "How to Run Locally" section
- Rename `README_assets` and move the DAG image accordingly
- Convert this into a **Notion or Portfolio writeup**

