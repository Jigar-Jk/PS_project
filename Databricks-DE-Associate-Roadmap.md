# Databricks Certified Data Engineer Associate — Caveman-Mode Documentation Roadmap
*Mapped to the official Exam Guide (version as of May 4, 2026). Read top → bottom.*

Note on terminology: the exam guide uses **Declarative Automation Bundles** (formerly **Databricks Asset Bundles / DABs**) and **Lakeflow Jobs** (formerly **Databricks Workflows**). Some doc URLs/snippets still say the old names — this is called out inline where relevant.

---

## Section 1.0 — Databricks Intelligence Platform (6%)

### 1.1 Architecture & Core Concepts
• What is Databricks (Data Intelligence Platform): https://docs.databricks.com/aws/en/introduction

• Scope of the Databricks platform: https://docs.databricks.com/aws/en/lakehouse-architecture/scope

• Databricks components (workspace, clusters, data objects): https://docs.databricks.com/aws/en/getting-started/concepts

• Workspace UI / navigation: https://docs.databricks.com/aws/en/workspace

• Reference architectures (Lakehouse, Lakeflow, DWH): https://docs.databricks.com/aws/en/lakehouse-architecture/reference

### 1.2 Delta Lake
• What is Delta Lake: https://docs.databricks.com/aws/en/delta

• Tutorial: Create and manage Delta Lake tables: https://docs.databricks.com/aws/en/delta/tutorial

• Medallion architecture (Bronze/Silver/Gold): https://docs.databricks.com/aws/en/lakehouse/medallion

### 1.3 Unity Catalog
• Unity Catalog overview: https://docs.databricks.com/aws/en/data-governance/unity-catalog

• Database objects (catalogs, schemas, tables, volumes, views): https://docs.databricks.com/aws/en/database-objects

### 1.4 Compute
• Compute overview (serverless vs classic vs SQL warehouses hub): https://docs.databricks.com/aws/en/compute

• Serverless compute: https://docs.databricks.com/aws/en/compute/serverless

• Classic compute config best practices: https://docs.databricks.com/aws/en/compute/cluster-config-best-practices

• Compute configuration reference (driver/worker types, autoscaling, pools): https://docs.databricks.com/aws/en/compute/configure

• SQL warehouses: https://docs.databricks.com/aws/en/compute/sql-warehouse

• Photon engine: https://docs.databricks.com/aws/en/compute/photon

• Instance pools: https://docs.databricks.com/aws/en/compute/pool-index

### 1.5 Compute Selection & Cost
• Cost management (usage, budgets): https://docs.databricks.com/aws/en/admin/usage

• Compute policies (governing what users can create): https://docs.databricks.com/aws/en/admin/clusters/policies

• Configure compute for Lakeflow Jobs (which task type needs which compute): https://docs.databricks.com/aws/en/jobs/compute

---

## Section 2.0 — Data Ingestion and Loading (21%)

### 2.1 Ingestion Fundamentals
• Data engineering overview: https://docs.databricks.com/aws/en/data-engineering

• Lakeflow Connect overview: https://docs.databricks.com/aws/en/ingestion/overview

• Ingest data from cloud object storage (Auto Loader vs COPY INTO): https://docs.databricks.com/aws/en/ingestion/cloud-object-storage

• Create/modify a table via file upload (local files): https://docs.databricks.com/aws/en/ingestion/create-or-modify-table

### 2.2 COPY INTO
• Get started using COPY INTO to load data: https://docs.databricks.com/aws/en/ingestion/cloud-object-storage/copy-into

### 2.3 Auto Loader
• What is Auto Loader: https://docs.databricks.com/aws/en/ingestion/cloud-object-storage/auto-loader

• Schema inference & schema evolution in Auto Loader: https://docs.databricks.com/aws/en/ingestion/cloud-object-storage/auto-loader/schema

• File notification mode (vs. directory listing): https://docs.databricks.com/aws/en/ingestion/cloud-object-storage/auto-loader/file-notification-mode

• Tutorial: Set up incremental ingestion from S3/ADLS/GCS: https://docs.databricks.com/aws/en/ingestion/cloud-object-storage/onboard-data

### 2.4 Schema Inference / Enforcement / Evolution (Delta side)
• Schema enforcement: https://docs.databricks.com/aws/en/tables/schema-enforcement

• Update table schemas with schema evolution: https://docs.databricks.com/aws/en/tables/update-schema

### 2.5 Lakeflow Connect (Managed & Standard Connectors)
• Standard connectors: https://docs.databricks.com/aws/en/ingestion

• Managed connectors overview: https://docs.databricks.com/aws/en/ingestion/lakeflow-connect

• SaaS connectors (Salesforce, Workday, etc.): https://docs.databricks.com/aws/en/ingestion/lakeflow-connect/saas-overview

• Database connectors / CDC: https://docs.databricks.com/aws/en/ingestion/lakeflow-connect/cdc-overview

• Managed file source connectors: https://docs.databricks.com/aws/en/ingestion/lakeflow-connect/file-connectors-overview

• Managed streaming connectors (Kafka, etc.): https://docs.databricks.com/aws/en/ingestion/lakeflow-connect/streaming-overview

### 2.6 JDBC / ODBC / REST Clients
• Connect to data sources & external services (federation, JDBC, HTTP overview): https://docs.databricks.com/aws/en/connect

• Connect to external systems via JDBC: https://docs.databricks.com/aws/en/connect/external-systems

• JDBC driver: https://docs.databricks.com/aws/en/integrations/jdbc-oss

• ODBC driver: https://docs.databricks.com/aws/en/integrations/odbc

### 2.7 Semi-Structured Data / JSON / Nested Data
• Model semi-structured data (best practices): https://docs.databricks.com/aws/en/semi-structured

• Read JSON files: https://docs.databricks.com/aws/en/query/formats/json

• Read/write XML: https://docs.databricks.com/aws/en/query/formats/xml

### 2.8 Choosing an Ingestion Method
• Data sources overview (compare formats & connectors): https://docs.databricks.com/aws/en/query/formats

• Lakeflow Connect overview (re-read for decision matrix — Auto Loader vs COPY INTO vs managed connectors): https://docs.databricks.com/aws/en/ingestion/overview

---

## Section 3.0 — Data Transformation and Modeling (22%)

### 3.1 DataFrame Fundamentals
• Load & transform data using Spark DataFrames (tutorial): https://docs.databricks.com/aws/en/getting-started/dataframes

• PySpark on Databricks: https://docs.databricks.com/aws/en/pyspark

• DataFrame class reference (select/filter/withColumn/groupBy/join in one page): https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe

### 3.2 Reading/Writing Delta Tables
• (Re-use) What is Delta Lake: https://docs.databricks.com/aws/en/delta

• Upsert with MERGE: https://docs.databricks.com/aws/en/delta/merge

• Selectively overwrite data: https://docs.databricks.com/aws/en/delta/selective-overwrite

### 3.3 Data Cleaning — Null Handling & Type Standardization
• fillna (null handling): https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/fillna

• SQL data types reference: https://docs.databricks.com/aws/en/sql/language-manual/sql-ref-datatypes

• Constraints (enforce data quality on write): https://docs.databricks.com/aws/en/tables/constraints

### 3.4 Joins (Inner / Left / Broadcast / Multi-key / Cross)
• DataFrame class reference (join examples — inner/left/cross): https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe

• broadcast() function: https://docs.databricks.com/aws/en/pyspark/reference/functions/broadcast

• Join hints (BROADCAST / MERGE / SHUFFLE_HASH) & autoBroadcastJoinThreshold: https://docs.databricks.com/aws/en/sql/language-manual/sql-ref-syntax-qry-select-hints

### 3.5 Union & Deduplication
• union (position-based, like UNION ALL): https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/union

• unionByName (name-based union): https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/unionByName

• dropDuplicates: https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/dropDuplicates

### 3.6 Column & Row Manipulation, Filtering, Explode
• filter: https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/filter

• where: https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/where

• explode (arrays/maps → rows): https://docs.databricks.com/aws/en/pyspark/reference/functions/explode

### 3.7 Aggregations
• GroupedData.agg: https://docs.databricks.com/aws/en/pyspark/reference/classes/groupeddata/agg

• count: https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/count

• approx_count_distinct: https://docs.databricks.com/aws/en/pyspark/reference/functions/approx_count_distinct

• DataFrame.summary (count/mean/stddev/min/max/percentiles): https://docs.databricks.com/aws/en/pyspark/reference/classes/dataframe/summary

### 3.8 Spark Tuning Parameters
• Set Spark configuration properties (shuffle partitions, session/notebook/compute scope): https://docs.databricks.com/aws/en/spark/conf

• Compute configuration reference (driver memory, executor memory, node types): https://docs.databricks.com/aws/en/compute/configure

• Spark overview hub (parallelism, AQE, links to Spark UI guide): https://docs.databricks.com/aws/en/spark

• Join hints & autoBroadcastJoinThreshold (re-use from 3.4): https://docs.databricks.com/aws/en/sql/language-manual/sql-ref-syntax-qry-select-hints

### 3.9 Materialized Views, Streaming Tables & Views
• Lakeflow pipelines concepts (materialized views, streaming tables, flows): https://docs.databricks.com/aws/en/ldp/concepts

• Views (UC views, temp views, dynamic views): https://docs.databricks.com/aws/en/views

### 3.10 Bronze/Silver/Gold & Data Quality Checks
• Medallion architecture (re-use from 1.2): https://docs.databricks.com/aws/en/lakehouse/medallion

• Manage data quality with pipeline expectations: https://docs.databricks.com/aws/en/ldp/expectations

---

## Section 4.0 — Working with Lakeflow Jobs (16%)

### 4.1 Lakeflow Jobs Fundamentals (Jobs, Tasks, DAG)
• Lakeflow Jobs overview: https://docs.databricks.com/aws/en/jobs

• Configure tasks (notebook / SQL / dashboard / pipeline / Python / dbt task types): https://docs.databricks.com/aws/en/jobs/configure-task

### 4.2 Task Dependencies, Control Flow & Retries
• Control the flow of tasks (retries, run-if, overview of all control-flow options): https://docs.databricks.com/aws/en/jobs/control-flow

• Configure task dependencies (Run if: All succeeded / At least one failed / All done, etc.): https://docs.databricks.com/aws/en/jobs/run-if

### 4.3 Branching & Looping
• Add branching logic with the If/else task: https://docs.databricks.com/aws/en/jobs/if-else

• Use a For each task to run another task in a loop: https://docs.databricks.com/aws/en/jobs/tasks/for-each

### 4.4 Schedules & Triggers
• Automate jobs with schedules and triggers (overview: scheduled/table update/file arrival/continuous): https://docs.databricks.com/aws/en/jobs/triggers

• Trigger jobs when new files arrive (file arrival trigger): https://docs.databricks.com/aws/en/jobs/file-arrival-triggers

• Trigger jobs when source tables are updated (table update trigger): https://docs.databricks.com/aws/en/jobs/trigger-table-update

### 4.5 Monitoring Job Runs
• Monitoring and observability for Lakeflow Jobs (matrix/list views, run history): https://docs.databricks.com/aws/en/jobs/monitor

• Troubleshoot and repair job failures: https://docs.databricks.com/aws/en/jobs/repair-job-failures

---

## Section 5.0 — Implementing CI/CD (10%)

### 5.1 Databricks Git Folders
• Git integration / Git folders (Repos) — clone, branch, commit, push, pull requests: https://docs.databricks.com/aws/en/repos

### 5.2 Declarative Automation Bundles (formerly Databricks Asset Bundles / DABs)
• What are Declarative Automation Bundles: https://docs.databricks.com/aws/en/dev-tools/bundles

• Bundle configuration reference (databricks.yml top-level keys): https://docs.databricks.com/aws/en/dev-tools/bundles/reference

• Bundle resources (jobs, pipelines, apps in a bundle): https://docs.databricks.com/aws/en/dev-tools/bundles/resources

• Bundle project templates: https://docs.databricks.com/aws/en/dev-tools/bundles/templates

### 5.3 Variables & Environment-Specific Configuration (Dev/Test/Prod)
• Substitutions and variables in bundles: https://docs.databricks.com/aws/en/dev-tools/bundles/variables

• Deployment modes (dev/staging/prod targets, `mode: development` / `mode: production`): https://docs.databricks.com/aws/en/dev-tools/bundles/deployment-modes

### 5.4 Databricks CLI & Deployment
• Databricks CLI overview: https://docs.databricks.com/aws/en/dev-tools/cli

• CLI command reference: https://docs.databricks.com/aws/en/dev-tools/cli/commands

• `bundle` command group (`databricks bundle validate/deploy/run`): https://docs.databricks.com/aws/en/dev-tools/cli/bundle-commands

### 5.5 CI/CD Workflows & Deploying Jobs/Pipelines
• CI/CD on Databricks (overview, best practices): https://docs.databricks.com/aws/en/dev-tools/ci-cd

• Developer best practices (source control, environment mgmt, managed deployments): https://docs.databricks.com/aws/en/developers/best-practices

---

## Section 6.0 — Troubleshooting, Monitoring, and Optimization (10%)

### 6.1 Monitoring Jobs
• (Re-use) Monitoring and observability for Lakeflow Jobs: https://docs.databricks.com/aws/en/jobs/monitor

• (Re-use) Troubleshoot and repair job failures: https://docs.databricks.com/aws/en/jobs/repair-job-failures

### 6.2 Spark UI
• Debugging with the Spark UI: https://docs.databricks.com/aws/en/compute/troubleshooting/debugging-spark-ui

• Diagnose cost and performance issues using the Spark UI (step-by-step guide): https://docs.databricks.com/aws/en/optimizations/spark-ui-guide

### 6.3 Performance Bottlenecks / Optimization Techniques
• Optimizations & performance recommendations (hub page): https://docs.databricks.com/aws/en/optimizations

### 6.4 Data Skew
• Adaptive Query Execution (AQE) handles skew by default — covered in: https://docs.databricks.com/aws/en/optimizations/spark-ui-guide

### 6.5 Shuffle / 6.6 Disk Spilling
• (Same Spark UI guide covers "look for skew or spill" as a diagnostic step): https://docs.databricks.com/aws/en/optimizations/spark-ui-guide

• Set Spark configuration properties (shuffle partitions tuning — re-use from 3.8): https://docs.databricks.com/aws/en/spark/conf

### 6.7 Liquid Clustering
• Use liquid clustering for tables: https://docs.databricks.com/aws/en/tables/clustering

• Optimize data file layout (OPTIMIZE, ZORDER vs. liquid clustering): https://docs.databricks.com/aws/en/delta/optimize

### 6.8 Predictive Optimization
• Predictive optimization for Unity Catalog managed tables (auto OPTIMIZE/VACUUM/ANALYZE): https://docs.databricks.com/aws/en/optimizations/predictive-optimization

### 6.9 Cluster Startup Failures / Library Conflicts
• Troubleshoot compute issues (start-up failures, metastore issues): https://docs.databricks.com/aws/en/compute/troubleshooting

• Classic compute termination error codes: https://docs.databricks.com/aws/en/compute/troubleshooting/cluster-error-codes

• Notebook-scoped Python libraries (avoiding/resolving library conflicts): https://docs.databricks.com/aws/en/libraries/notebooks-python-libraries

### 6.10 Memory / OOM Problems
• Debugging with the Spark UI (re-use — identify OOM/skewed stages): https://docs.databricks.com/aws/en/compute/troubleshooting/debugging-spark-ui

• Compute configuration reference (re-use — sizing driver/executor memory): https://docs.databricks.com/aws/en/compute/configure

---

## Section 7.0 — Governance and Security (15%)

### 7.1 Unity Catalog Core Objects
• (Re-use) Unity Catalog overview: https://docs.databricks.com/aws/en/data-governance/unity-catalog

• Table types (managed / external / foreign — comparison): https://docs.databricks.com/aws/en/tables/types

• Managed tables (create/query/update/drop): https://docs.databricks.com/aws/en/tables/managed

• External tables (create/query/update/drop): https://docs.databricks.com/aws/en/tables/external

### 7.2 Converting Managed ⇄ External Tables
• Convert an external table to a managed table (`SET MANAGED`): https://docs.databricks.com/aws/en/tables/convert-external-managed

• Convert external/foreign Delta tables to managed tables: https://docs.databricks.com/aws/en/tables/convert-to-managed

### 7.3 GRANT / REVOKE / DENY
• Privileges and securable objects in Unity Catalog: https://docs.databricks.com/aws/en/sql/language-manual/sql-ref-privileges

• GRANT statement: https://docs.databricks.com/aws/en/sql/language-manual/security-grant

• REVOKE statement: https://docs.databricks.com/aws/en/sql/language-manual/security-revoke

• DENY statement (⚠️ legacy Hive metastore only — **not supported in Unity Catalog**; UC uses ABAC deny policies instead, see 7.6): https://docs.databricks.com/aws/en/sql/language-manual/security-deny

• Manage privileges in Unity Catalog (how-to, UI + SQL): https://docs.databricks.com/aws/en/data-governance/unity-catalog/manage-privileges

• Unity Catalog privileges reference (full list per object type): https://docs.databricks.com/aws/en/data-governance/unity-catalog/access-control/privileges-reference

### 7.4 Users, Groups, Service Principals
• User and group management: https://docs.databricks.com/aws/en/admin/users-groups

• Service principals: https://docs.databricks.com/aws/en/admin/users-groups/service-principals

### 7.5 Security Hierarchy & Permissions
• Access control in Unity Catalog (privileges, ownership, hierarchy overview): https://docs.databricks.com/aws/en/data-governance/unity-catalog/access-control

### 7.6 Column Masking, Row-Level Security & ABAC
• Row and column filters (row filters + column masks): https://docs.databricks.com/aws/en/data-governance/unity-catalog/filters-and-masks

• Attribute-based access control (ABAC) overview: https://docs.databricks.com/aws/en/data-governance/unity-catalog/abac

• Create and manage ABAC policies (row filter / column mask / GRANT / DENY policies): https://docs.databricks.com/aws/en/data-governance/unity-catalog/abac/policies

• Governed tags (tag-driven policy enforcement): https://docs.databricks.com/aws/en/admin/governed-tags

---

## Coverage Check

Section 1 — Covered
Section 2 — Covered
Section 3 — Covered
Section 4 — Covered
Section 5 — Covered
Section 6 — Covered
Section 7 — Covered

**Partial-coverage notes (no single dedicated page exists — closest official pages given instead):**
- *"Default parallelism" as a standalone tunable* — Not directly covered by a single official documentation page. It's discussed inline within the general Spark configuration page (`spark/conf`) rather than having its own article; `spark.default.parallelism` / `spark.sql.shuffle.partitions` are mentioned in passing across the Spark tuning and optimization docs rather than one canonical reference.
- *Out-of-memory (OOM) troubleshooting for standard (non-GPU) Spark jobs* — Not directly covered by a single official documentation page. Databricks' official OOM-specific article covers only GPU/CUDA OOM. For CPU-side driver/executor OOM, the closest official coverage is diagnostic (Spark UI guide) + configuration (Compute configuration reference), linked in 6.10.
- *REST client ingestion as a distinct pattern* — Covered indirectly via the "Connect to data sources and external services" and JDBC/ODBC pages (2.6); Databricks doesn't have a single dedicated "REST client ingestion" tutorial page — it's folded into the general external-systems connectivity docs.

---

*Everything above is official `docs.databricks.com` documentation (AWS edition, which mirrors GCP/Azure content 1:1 for these topics — swap `/aws/en/` for `/gcp/en/` or use `learn.microsoft.com/en-us/azure/databricks/...` if you work on a different cloud).*
