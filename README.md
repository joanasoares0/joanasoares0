# Hi, I'm Joana Soares 👋

## About Me

- 🔧 **Analytics Engineer** — transforming raw data into reliable, well-structured pipelines and models
- 📊 Passionate about clean data architecture, good documentation, and making data trustworthy
- 🌱 Currently learning: **dbt · Microsoft Fabric · Databricks · Python & Data Pipelines · Claude & AI**
- 💬 Ask me about **Analytics Engineering, SQL, dbt, Power BI and data modelling**
- 📝 Writing about data & tech on **[Shift with Jo](https://shiftwithjo.substack.com/)**

---

## Get in Touch 📬

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Joana%20Soares-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/joana-raquel-soares/)
[![Substack](https://img.shields.io/badge/Substack-Shift%20with%20Jo-FF6719?style=for-the-badge&logo=substack&logoColor=white)](https://shiftwithjo.substack.com/)
[![Email](https://img.shields.io/badge/Email-joana.raquel.soares0%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:joana.raquel.soares0@gmail.com)

---

## Tech Stack 🛠️

**Transform & Model**

![dbt](https://img.shields.io/badge/dbt-FF694B?style=for-the-badge&logo=dbt&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

**Platforms**

![Microsoft Fabric](https://img.shields.io/badge/Microsoft%20Fabric-742774?style=for-the-badge&logo=microsoft&logoColor=white)
![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=for-the-badge&logo=databricks&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)

**Tools**

![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![VS Code](https://img.shields.io/badge/VS%20Code-007ACC?style=for-the-badge&logo=visualstudiocode&logoColor=white)
![Azure DevOps](https://img.shields.io/badge/Azure%20DevOps-0078D7?style=for-the-badge&logo=azuredevops&logoColor=white)

---
## Projects 🚀

### [User Management — Access Request System](https://github.com/joanasoares0/user_mgt_databricks_aidevkit)
Portfolio case study — Databricks-native replacement for a manual, spreadsheet-and-email access-request process.

A self-service intake app, a guided admin approval app, and a live dashboard, cutting ~17.75 hours of manual admin work down to ~3.25 hours over a 21-day sample — an ~82% reduction — built on Databricks Asset Bundles, Unity Catalog, and Databricks Apps.
- **Intake app:** guided multi-step Streamlit form for new/edit access requests, live-sourced rule dropdowns, per-domain/person duplicate detection, and an edit-access lookup that resumes an existing or pending request
- **Admin app:** deterministic slash-command approval console (no LLM in the write path) — grant/deny, comments, ticket management, and full status/rule correction, every write stamped `reviewed_by`/`updated_at`
- **Data layer:** two Unity Catalog fact tables as the single source of truth, with an AI/BI (Lakeview) dashboard replacing a manual Power BI cross-check
- **Everything as code:** tables, jobs, apps, and dashboard defined and deployed via Databricks Asset Bundles

`Python` `Streamlit` `Databricks` `Unity Catalog` `Delta Lake` `Databricks Asset Bundles`

### [Credit Score ETL Pipeline](https://github.com/joanasoares0/data_girls_bootcamp_project)
Capstone project — Data Engineering track, Data Girls Bootcamp 2026.

An end-to-end ETL pipeline that extracts a credit score dataset from Kaggle, cleans and transforms it with pandas, and loads the result into a Databricks Unity Catalog Volume via the Files API.
- **Transform:** handles corrupted/sentinel values, PII pseudonymization (hashing + reversible ID mapping), type casting, range checks, and outlier/missing-value treatment — with the target column always kept untouched
- **Orchestration:** Apache Airflow running in Docker, backed by a Postgres metadata database so DAG run history and the admin user survive container rebuilds
- **Scheduling:** a daily DAG with automatic retries and a failure callback that logs which task/run failed and where to find the logs
- **Documentation:** every data-quality and architectural decision is explained and justified in the README

`Python` `pandas` `Airflow` `Docker` `Postgres` `Databricks`

### [dbt + Snowflake Capstone Project](https://github.com/joanasoares0/dbt_snowflake_capstone_project)
Capstone project — dbt/Analytics Engineering course.
A dbt project built on Snowflake from scratch: a medallion-architecture pipeline (raw → staging/bronze → silver) over real public aviation data (~72K airports, ~44K runways, and user comments from OurAirports, joined on the `airport_ident` ICAO code).

- **Incremental models:** built to process new/changed data efficiently rather than full-rebuild every run
- **Snapshots:** slowly changing dimensions (SCD Type 2) tracked via dbt's built-in snapshot feature
- **Layered testing:** generic, domain-specific, cross-model, and singular tests, extended with `dbt-expectations`, plus test-failure persistence for debugging
- **Documentation:** `doc()` blocks, full model/column descriptions, and an interconnection overview tying the whole DAG together
- **Environment:** managed with `uv` for reproducible Python/dbt tooling

`dbt-core` `Snowflake` `dbt-expectations` `SQL` `uv`

### [Data Cleaning & Analytics Portfolio](https://github.com/joanasoares0/data_project_w_claude)
Three independent, self-contained data projects, cleaning, static reporting, and a live BI dashboard; each solving the same class of e-commerce/CRM problem with a different final delivery format.

A portfolio repo where every project lives in its own folder with no shared code, its own dataset, and its own README, so eacendently.
- **Sales data cleaning:** Streamlit app + CLI that diagnoses and fixes a CRM sales export, leaked status fields, flagged/contet capitalization and accentuation, mixed date formats, revenue as BR/US-formatted text, with genuinely missing or unparseable values left untouched and surfaced for manual review, never invented.
- **Static analytics report:** a CSV → JSON → HTML pipeline that computes e-commerce KPIs (revenue trends, category/brand bregaps, geographic distribution) into small intermediate JSON files and renders a single static report, keeping the ~3,000-row sales table out of memory/context all at once.
- **Live analytics dashboard:** a multi-page Streamlit dashboard over the same dataset served from a Supabase (Postgres) database read-only via the `anon` key — Sales, Price Positioning, and Customers pages each backed by a pure, unit-tested KPI module, with every formula and data-quality caveat documented.

`Python` `pandas` `Streamlit` `Supabase` `pytest`
