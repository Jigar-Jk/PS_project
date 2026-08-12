# SnowPro Core Complete MCQ Collection


====================================================================================================
# snowpro_1-100.md
====================================================================================================

# SnowPro Core Practice Questions --- Cleaned and Documentation-Checked

> Source text was OCR-damaged and contained several old SnowPro-era
> questions. I reconstructed the wording, normalized the options, and
> corrected answers that conflict with current Snowflake documentation
> as of **July 2026**.

> **Important:** These are study questions, not claimed to be current
> official exam questions. Questions tied to the retired Classic
> Console, old release behavior, old MFA guidance, or undocumented
> infrastructure/server counts have been modernized or flagged.

## Documentation cross-check used

-   Snowflake architecture and warehouses:
    https://docs.snowflake.com/en/user-guide/intro-key-concepts and
    https://docs.snowflake.com/en/user-guide/warehouses
-   Warehouse scaling policies:
    https://docs.snowflake.com/en/sql-reference/sql/create-warehouse
-   Micro-partitions and clustering:
    https://docs.snowflake.com/en/user-guide/tables-clustering-micropartitions
-   Persisted query results:
    https://docs.snowflake.com/en/user-guide/querying-persisted-results
-   Snowsight Query History:
    https://docs.snowflake.com/en/user-guide/ui-snowsight-activity
-   UDF languages:
    https://docs.snowflake.com/en/developer-guide/udf/udf-overview
-   Time Travel and Fail-safe:
    https://docs.snowflake.com/en/user-guide/data-availability
-   Snowflake editions:
    https://docs.snowflake.com/en/user-guide/intro-editions
-   PUT and internal-stage encryption:
    https://docs.snowflake.com/en/sql-reference/sql/put
-   Snowpipe:
    https://docs.snowflake.com/en/user-guide/data-load-snowpipe-intro
-   MFA guidance and rollout:
    https://docs.snowflake.com/en/user-guide/security-mfa and
    https://docs.snowflake.com/en/user-guide/security-mfa-rollout

------------------------------------------------------------------------

## Question 1

What Snowflake feature lets customers explicitly influence data clustering beyond natural clustering?

- A. Micro-partitions
- B. Clustering keys
- C. Key partitions
- D. Clustered partitions

<details>
<summary><strong>Show Answer</strong></summary>

### ✅ Correct Answer

**Answer:** **B. Clustering keys**

**Why this is correct**

Clustering keys allow users to explicitly influence how data is organized within micro-partitions. This improves pruning and can reduce the amount of data scanned.

---

<details>
<summary><strong>❌ Why the Other Options Are Wrong</strong></summary>

**A. Micro-partitions**

Micro-partitions are automatically created and managed by Snowflake. Users cannot directly control their creation or clustering.

---

**C. Key partitions**

This is not a Snowflake feature or terminology.

---

**D. Clustered partitions**

This is not an official Snowflake feature. Snowflake uses **clustering keys**, not "clustered partitions."

</details>

---

### 📖 Overall Explanation

Snowflake automatically stores data in **micro-partitions** and naturally clusters data as it is loaded. However, for very large tables with frequent filtering on specific columns, the natural clustering may become inefficient over time.

To improve query performance, Snowflake allows you to define **clustering keys**. These keys tell Snowflake which columns should be considered when reorganizing data to improve partition pruning. Better clustering reduces the number of micro-partitions scanned, resulting in faster queries and lower compute costs.

#### Key Takeaways

- Micro-partitions are automatic.
- Clustering keys are user-defined.
- Clustering improves partition pruning.
- Better pruning means less data scanned and faster queries.

</details>

------------------------------------------------------------------------

## Question 2

Which are valid multi-cluster warehouse scaling policies? (Choose two.)

-   A. Custom
-   B. Economy
-   C. Optimized
-   D. Standard

<details>
<summary>Show Answer</summary>

**Correct Answer: B, D**

</details>

------------------------------------------------------------------------

## Question 3

True or False: A single database can exist in more than one Snowflake
account.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 4

Which system role is recommended for creating and managing users and
roles?

-   A. SYSADMIN
-   B. SECURITYADMIN
-   C. PUBLIC
-   D. ACCOUNTADMIN

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 5

True or False: Bulk unloading from Snowflake supports using a SELECT
statement as the source.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 6

Which are the three types of internal stages? (Choose three.)

-   A. Named stage
-   B. User stage
-   C. Table stage
-   D. Schema stage

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C**

</details>

------------------------------------------------------------------------

## Question 7

True or False: A customer using SnowSQL or native connectors cannot also
use the Snowflake web interface unless Snowflake Support explicitly
grants UI access.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 8

Where can account-level storage usage be monitored in Snowsight?

-   A. Data » Databases
-   B. Admin » Cost Management / usage views
-   C. INFORMATION_SCHEMA.ACCOUNT_USAGE_HISTORY
-   D. ACCOUNT_USAGE.ACCOUNT_USAGE_METRICS

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 9

Virtual warehouse credit consumption is primarily based on which two
factors? (Choose two.)

-   A. Number of users
-   B. Warehouse size
-   C. Amount of data processed
-   D. Number of active clusters

<details>
<summary>Show Answer</summary>

**Correct Answer: B, D**

</details>

------------------------------------------------------------------------

## Question 10

Which statement best describes clustering in Snowflake?

-   A. It describes how data is grouped within micro-partitions
-   B. An administrator must define clustering for every table
-   C. A clustering key must be specified in COPY
-   D. Clustering can be disabled account-wide

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 11

True or False: COPY must always specify a named file format object.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 12

Which command sets the virtual warehouse for the current session?

-   A. COPY WAREHOUSE FROM `<config_file>`{=html}
-   B. SET WAREHOUSE = `<warehouse_name>`{=html}
-   C. USE WAREHOUSE `<warehouse_name>`{=html}
-   D. USE VIRTUAL WAREHOUSE `<warehouse_name>`{=html}

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 13

Which objects can be cloned? (Choose four from these options.)

-   A. Tables
-   B. Named file formats
-   C. Schemas
-   D. Shares
-   E. Databases

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C, E**

</details>

------------------------------------------------------------------------

## Question 14

Which Snowflake object can enforce credit-consumption limits?

-   A. Account Tracking
-   B. Resource Monitor
-   C. Warehouse Limit Parameter
-   D. Credit Consumption Tracker

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 15

Snowflake is primarily designed for which workload characteristics?
(Choose two.)

-   A. OLAP / analytics workloads
-   B. OLTP workloads
-   C. Concurrent workloads
-   D. On-premises workloads

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C**

</details>

------------------------------------------------------------------------

## Question 16

What are the three main layers of Snowflake architecture? (Choose
three.)

-   A. Compute
-   B. Tri-Secret Secure
-   C. Storage
-   D. Cloud Services

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C, D**

</details>

------------------------------------------------------------------------

## Question 17

Why would a customer resize a warehouse from Small to Medium?

-   A. To add more clusters for concurrency
-   B. To add more users
-   C. To handle workload fluctuations automatically
-   D. To provide more compute for a more complex workload

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 18

True or False: Reader accounts create no compute cost for the data
provider.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

> **Documentation update:** Corrected: reader-account compute is paid by
> the provider account, so the provider can incur compute cost.

</details>

------------------------------------------------------------------------

## Question 19

Which clients can use MFA-based authentication when supported and
configured? (Choose all that apply.)

-   A. JDBC
-   B. SnowSQL
-   C. Snowsight
-   D. ODBC
-   E. Python connector

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C, D, E**

</details>

------------------------------------------------------------------------

## Question 20

True or False: Snowflake charges a storage premium specifically because
data is semi-structured.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 21

Which statements describe benefits of separating compute and storage?
(Choose all that apply.)

-   A. Storage and compute must grow together
-   B. Storage can expand without adding compute
-   C. Compute can scale without adding storage
-   D. Multiple compute clusters can access shared stored data without
    storage contention

<details>
<summary>Show Answer</summary>

**Correct Answer: B, C, D**

</details>

------------------------------------------------------------------------

## Question 22

True or False: Snowflake can unload table/query data to JSON and Parquet
formats.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 23

In which architecture layer does Snowflake manage metadata and
optimization statistics?

-   A. Storage
-   B. Compute
-   C. Database
-   D. Cloud Services

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 24

True or False: Customers can directly delete data from Fail-safe.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 25

True or False: Snowflake was built from the ground up for the cloud
rather than on an existing database or Hadoop platform.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 26

Which statements about virtual warehouses are true? (Choose all that
apply.)

-   A. Warehouse size can be changed after creation
-   B. A running warehouse can be resized
-   C. A warehouse can auto-suspend after inactivity
-   D. A warehouse can auto-resume when a statement needs compute

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C, D**

</details>

------------------------------------------------------------------------

## Question 27

Which statements about PUT are true? (Choose two.)

-   A. It automatically creates a file
-   B. It automatically uses the last-created stage
-   C. By default it compresses eligible files using gzip
-   D. Files on internal stages are encrypted

<details>
<summary>Show Answer</summary>

**Correct Answer: C, D**

</details>

------------------------------------------------------------------------

## Question 28

Which table type exists only for the current session?

-   A. Temporary
-   B. Transient
-   C. Provisional
-   D. Permanent

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 29

Which interfaces can create or manage virtual warehouses?

-   A. Snowsight
-   B. SQL commands
-   C. Tools that issue supported Snowflake SQL/API operations
-   D. All of the above

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 30

What happens when a pipe is recreated with CREATE OR REPLACE PIPE?

-   A. The new pipe has no retained load history for duplicate detection
-   B. REFRESH is automatically TRUE
-   C. Previously loaded files are always ignored
-   D. All of the above

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 31

What is the minimum Snowflake edition generally intended for customers
storing highly sensitive regulated data requiring enhanced security
capabilities?

-   A. Standard
-   B. Premier
-   C. Enterprise
-   D. Business Critical

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 32

Which three table types exist in Snowflake? (Choose three.)

-   A. Temporary
-   B. Transient
-   C. Provisional
-   D. Permanent

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, D**

</details>

------------------------------------------------------------------------

## Question 33

True or False: Snowpipe's REST API can reference only external stages.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 34

True or False: A third-party tool that supports standard JDBC/ODBC but
has no Snowflake-specific driver can connect without using a Snowflake
JDBC/ODBC driver.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 35

True or False: Data can be loaded without creating a named FILE FORMAT
object.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 36

True or False: A table can be queried only by the warehouse that loaded
it.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 37

Which are recommended data-loading practices? (Choose three.)

-   A. VARIANT JSON null is distinct from SQL NULL
-   B. Perform frequent single-row DML whenever possible
-   C. Validate data before loading into the target table
-   D. Use staging tables when useful for MERGE-based processing

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C, D**

</details>

------------------------------------------------------------------------

## Question 38

Which statements about micro-partitions are true? (Choose two.)

-   A. They contain roughly 50--500 MB of uncompressed data
-   B. Compression occurs only when COMPRESS=TRUE is set on the table
-   C. They are immutable
-   D. They are encrypted only in Enterprise Edition and above

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C**

> **Documentation update:** Corrected outdated size wording: current
> docs describe micro-partitions as 50--500 MB of uncompressed data;
> storage is compressed automatically.

</details>

------------------------------------------------------------------------

## Question 39

True or False: Query IDs are unique identifiers that can be provided to
Snowflake Support when troubleshooting queries.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 40

A deterministic query is executed and its result is persisted. Which
statements are true? (Choose two.)

-   A. Snowflake always reuses the result for 24 hours
-   B. The same query can reuse the result when reuse conditions are met
    and underlying data has not changed
-   C. The result is reused even if underlying data changed
-   D. Reusing a persisted result resets its 24-hour retention window,
    up to the documented maximum lifetime

<details>
<summary>Show Answer</summary>

**Correct Answer: B, D**

> **Documentation update:** Clarified persisted-result reuse: reuse is
> conditional; each successful reuse resets the 24-hour retention
> period, up to 31 days from initial execution.

</details>

------------------------------------------------------------------------

## Question 41

Increasing MAX_CLUSTER_COUNT for a multi-cluster warehouse is an example
of:

-   A. Rhythmic scaling
-   B. Scaling max
-   C. Scaling out
-   D. Scaling up

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 42

Which statement best describes Snowflake tables?

-   A. They are logical representations of underlying Snowflake-managed
    storage
-   B. They are user-managed physical files
-   C. Every table requires a clustering key
-   D. Tables are owned directly by users rather than roles

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 43

Which migration item generally does not apply to Snowflake?

-   A. Migrate data
-   B. Migrate schemas
-   C. Migrate indexes
-   D. Build the data pipeline

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 44

Which table types help reduce storage costs for short-lived/transitory
data? (Choose two.)

-   A. Temporary
-   B. Transient
-   C. Provisional
-   D. Permanent

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B**

</details>

------------------------------------------------------------------------

## Question 45

Which statement correctly describes micro-partition size?

-   A. Exactly 8 GB compressed
-   B. Approximately 16 MB compressed
-   C. Approximately 50--500 MB uncompressed, with smaller compressed
    storage
-   D. Exactly 4 TB

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

> **Documentation update:** Corrected outdated '16 MB maximum compressed
> size' wording.

</details>

------------------------------------------------------------------------

## Question 46

Which are current top-level Snowsight navigation areas relevant to these
functions? (Choose three.)

-   A. Data
-   B. Tables
-   C. Compute
-   D. Projects / Worksheets

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C, D**

> **Documentation update:** Modernized Classic Console navigation
> wording to current Snowsight areas.

</details>

------------------------------------------------------------------------

## Question 47

Which Snowflake data type is recommended for semi-structured data such
as JSON?

-   A. VARCHAR
-   B. RAW
-   C. LOB
-   D. VARIANT

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 48

Which statements best describe Snowflake releases? (Choose two.)

-   A. Snowflake continuously delivers releases/updates as a managed
    service
-   B. Customers must manually install monthly releases
-   C. Service upgrades are designed to be transparent to running
    customer workloads
-   D. Every customer receives a mandatory downtime window

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C**

> **Documentation update:** Modernized release wording; the old
> question's release-cadence phrasing is no longer a good certification
> question.

</details>

------------------------------------------------------------------------

## Question 49

Which are common zero-copy cloning use cases? (Choose three.)

-   A. Rapid Dev/Test/QA provisioning
-   B. Logical snapshots or backup-like copies
-   C. Point-in-time clones using Time Travel
-   D. Direct query performance optimization

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C**

</details>

------------------------------------------------------------------------

## Question 50

Warehouse compute resources roughly double with each size step. If a
Small warehouse is treated as 2 units, how many units does Medium have?

-   A. 4
-   B. 16
-   C. 32
-   D. 128

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

> **Documentation update:** Corrected answer from the OCR/dump: Medium
> is 4 units if Small is 2; warehouse sizes roughly double compute per
> size step.

</details>

------------------------------------------------------------------------

## Question 51

True or False: A consumer of a direct share can re-share that imported
database to other consumers.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 52

Which statements about network policies are true? (Choose two.)

-   A. Network policies are available across Snowflake editions
-   B. They are Business Critical-only
-   C. They can allow or block network identifiers such as IP ranges
-   D. They are activated with ALTER DATABASE

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C**

</details>

------------------------------------------------------------------------

## Question 53

True or False: Snowflake charges a separate fee to a provider for each
share object created.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 54

How long is a persisted query result normally retained after it is
generated or successfully reused, assuming reuse remains valid?

-   A. 1 hour
-   B. 3 hours
-   C. 12 hours
-   D. 24 hours

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 55

A role owns two tables and is dropped. What happens to the owned tables?

-   A. They become orphaned
-   B. Ownership transfers to the user
-   C. Ownership always transfers to SYSADMIN
-   D. The DROP ROLE operation requires ownership handling; current
    Snowflake behavior should be evaluated via dependent
    privileges/OWNERSHIP rules

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

> **Documentation update:** Reworded because role dropping/OWNERSHIP
> behavior is more nuanced than the old dump's simplistic answer.

</details>

------------------------------------------------------------------------

## Question 56

Which client downloads were historically exposed in the classic
Snowflake web interface? (Choose two.)

-   A. SnowSQL
-   B. ODBC driver
-   C. Hive
-   D. None

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B**

> **Documentation update:** Marked as historical Classic Console
> wording; not a current Snowsight navigation question.

</details>

------------------------------------------------------------------------

## Question 57

Which DML-style command is not a Snowflake SQL command?

-   A. UPSERT
-   B. MERGE
-   C. UPDATE
-   D. TRUNCATE TABLE

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 58

Which statement about zero-copy cloning is true?

-   A. A clone immediately duplicates all storage
-   B. Every cloned object inherits all source privileges
-   C. Cloning requires a separate feature license
-   D. At creation, clone and source initially share underlying
    micro-partitions

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 59

True or False: When a user creates a role, the user personally owns the
role until ownership is transferred.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 60

How much query history does the Snowsight Query History page display?

-   A. 60 minutes
-   B. 24 hours
-   C. 14 days
-   D. 90 days
-   E. 1 year

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 61

How do you configure a multi-cluster warehouse for Auto-scale mode?

-   A. Set only MAX_CLUSTER_COUNT
-   B. Set warehouse TYPE
-   C. Set MIN_CLUSTER_COUNT and MAX_CLUSTER_COUNT to the same value
-   D. Set MIN_CLUSTER_COUNT and MAX_CLUSTER_COUNT to different values,
    with max greater than min

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 62

Which term best describes Snowflake's architecture?

-   A. Columnar shared-nothing
-   B. Shared disk
-   C. Multi-cluster, shared data
-   D. Cloud-native shared memory

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 63

Which are warehouse configuration options? (Choose two.)

-   A. AUTO_DROP
-   B. AUTO_RESIZE
-   C. AUTO_RESUME
-   D. AUTO_SUSPEND

<details>
<summary>Show Answer</summary>

**Correct Answer: C, D**

</details>

------------------------------------------------------------------------

## Question 64

Warehouse AUTO_SUSPEND and AUTO_RESUME settings apply to:

-   A. Only the primary cluster
-   B. The warehouse
-   C. The database
-   D. Individual queries

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 65

Fail-safe is unavailable for which table types? (Choose two.)

-   A. Temporary
-   B. Transient
-   C. Provisional
-   D. Permanent

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B**

</details>

------------------------------------------------------------------------

## Question 66

Which object is not protected by Time Travel?

-   A. Tables
-   B. Schemas
-   C. Databases
-   D. Stages

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 67

True or False: Micro-partition metadata allows some metadata-only
operations/queries to be answered without warehouse compute.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 68

Which operations are generally non-blocking with respect to concurrent
table reads because of Snowflake's concurrency architecture? (Choose
two.)

-   A. UPDATE
-   B. INSERT
-   C. MERGE
-   D. COPY INTO table

<details>
<summary>Show Answer</summary>

**Correct Answer: B, D**

</details>

------------------------------------------------------------------------

## Question 69

Which statements about Snowpipe are true? (Choose two.)

-   A. It can load only from internal stages
-   B. Every COPY INTO option is supported in a pipe definition
-   C. Snowflake manages the compute used by classic Snowpipe
-   D. Snowpipe tracks files already loaded

<details>
<summary>Show Answer</summary>

**Correct Answer: C, D**

> **Documentation update:** Updated MFA guidance: current Snowflake
> guidance/rollout applies MFA to human password users, not only
> ACCOUNTADMIN.

</details>

------------------------------------------------------------------------

## Question 70

Which users should use MFA under current Snowflake security guidance?

-   A. Only SECURITYADMIN and ACCOUNTADMIN
-   B. Only SYSADMIN
-   C. Only ACCOUNTADMIN
-   D. All human users; Snowflake is phasing out single-factor password
    sign-ins

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 71

When can a virtual warehouse begin running queries?

-   A. Only 12 AM--5 AM
-   B. Only in administrator-defined time slots
-   C. When provisioning/resume is complete enough to accept work
-   D. After replication

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 72

True or False: Users can automatically see query result sets of other
users merely because they share the same role.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 73

True or False: A user must choose the specific cluster that runs a query
in a multi-cluster warehouse.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 74

True or False: Pipes can be paused/suspended and resumed.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

> **Documentation update:** Corrected outdated UDF language answer:
> current UDF handlers support Java, JavaScript, Python, Scala, and SQL.

</details>

------------------------------------------------------------------------

## Question 75

Which languages are currently supported for Snowflake UDF handlers?
(Choose all that apply.)

-   A. Java
-   B. JavaScript
-   C. SQL
-   D. Python
-   E. Scala

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C, D, E**

</details>

------------------------------------------------------------------------

## Question 76

When might disabling AUTO_SUSPEND be reasonable? (Choose two.)

-   A. For sporadic workloads throughout a day
-   B. For a steady workload
-   C. When avoiding resume latency is important
-   D. Because AUTO_RESUME does not exist

<details>
<summary>Show Answer</summary>

**Correct Answer: B, C**

> **Documentation update:** Corrected: bulk COPY from an internal stage
> is also a valid loading method.

</details>

------------------------------------------------------------------------

## Question 77

Which are valid ways to load data into a Snowflake table? (Choose all
that apply.)

-   A. COPY INTO from a stage
-   B. Continuous loading with Snowpipe
-   C. Snowsight load-data workflow
-   D. Bulk COPY from an internal stage

<details>
<summary>Show Answer</summary>

**Correct Answer: A, B, C, D**

</details>

------------------------------------------------------------------------

## Question 78

When does AUTO_SUSPEND suspend a warehouse?

-   A. When all sessions terminate
-   B. Immediately after the last query
-   C. When there are no logins
-   D. After the configured period of warehouse inactivity

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 79

True or False: Snowflake MFA works only with SSO.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 80

Which factors influence how many queries a warehouse can process
concurrently? (Choose two.)

-   A. Query complexity/resource demand
-   B. A fixed account-wide concurrency number
-   C. Data volume/resource requirements of queries
-   D. The client tool name

<details>
<summary>Show Answer</summary>

**Correct Answer: A, C**

</details>

------------------------------------------------------------------------

## Question 81

Which statements about VALIDATION_MODE are true? (Choose two.)

-   A. It is a CREATE STAGE option
-   B. It is an option of COPY INTO
    ```{=html}
    <table>
    ```
-   C. It validates while completing the load
-   D. It validates input without loading data and returns validation
    results/errors

<details>
<summary>Show Answer</summary>

**Correct Answer: B, D**

</details>

------------------------------------------------------------------------

## Question 82

Which privileges are required to create a task?

-   A. Only global CREATE TASK
-   B. Only ACCOUNTADMIN can create tasks
-   C. No task-specific privileges are needed
-   D. CREATE TASK on the schema plus required object privileges; task
    execution also depends on EXECUTE TASK or serverless task privileges
    as applicable

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 83

Which three qualities are commonly sought in an enterprise data
warehouse? (Choose three.)

-   A. On-premises availability
-   B. Simplicity
-   C. Open-source base
-   D. Concurrency
-   E. Performance

<details>
<summary>Show Answer</summary>

**Correct Answer: B, D, E**

</details>

------------------------------------------------------------------------

## Question 84

True or False: Some metadata-only queries can be answered without an
active warehouse.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 85

Scaling out by adding clusters to a multi-cluster warehouse primarily
improves:

-   A. Concurrency / queued workload handling
-   B. Single-query performance
-   C. Storage capacity
-   D. Time Travel retention

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

> **Documentation update:** Corrected outdated answer: Secure Data
> Sharing is available in Standard Edition.

</details>

------------------------------------------------------------------------

## Question 86

What is the minimum Snowflake edition that supports Secure Data Sharing?

-   A. Standard
-   B. Premier
-   C. Enterprise
-   D. Business Critical

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 87

True or False: Snowsight worksheets can use different database, schema,
and warehouse contexts.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 88

True or False: Snowflake can query files in an external stage directly
without first loading them into a table.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

> **Documentation update:** Corrected FLATTEN: it is primarily for
> semi-structured values such as VARIANT/OBJECT/ARRAY.

</details>

------------------------------------------------------------------------

## Question 89

The FLATTEN table function is primarily used with which data?

-   A. Structured relational data only
-   B. Semi-structured data
-   C. Both equally as its primary purpose
-   D. None

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

> **Documentation update:** Clarified COPY INTO: warehouse requirements
> depend on the COPY form/service; classic Snowpipe is Snowflake-managed
> compute.

</details>

------------------------------------------------------------------------

## Question 90

True or False: A user-managed virtual warehouse is required for every
COPY INTO statement.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 91

True or False: Private connectivity such as AWS PrivateLink can provide
private network connectivity between customer networks and Snowflake
without traversing the public internet.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 92

True or False: Snowflake maintains metadata about columns in
micro-partitions for pruning and optimization.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 93

True or False: It is best practice to define a clustering key on every
table.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: B**

</details>

------------------------------------------------------------------------

## Question 94

Which statement about Snowflake is true?

-   A. It was built specifically for the cloud
-   B. It was an on-premises database later ported to cloud
-   C. It is primarily a hybrid on-prem/cloud database
-   D. It was built on Hadoop
-   E. It is based on Oracle architecture

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 95

What is the minimum edition that provides multi-cluster warehouses and
extended Time Travel up to 90 days?

-   A. Standard
-   B. Premier
-   C. Enterprise
-   D. Business Critical

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

> **Documentation update:** Marked the old fixed share-limit question as
> outdated and unsuitable without a current limits reference.

</details>

------------------------------------------------------------------------

## Question 96

How many shares can a data consumer consume?

-   A. 10
-   B. 50
-   C. 100, hard limit
-   D. This old fixed-limit question is outdated; current sharing limits
    are governed by current Snowflake limits and feature behavior rather
    than this exam's 'Unlimited' claim

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 97

What is the lowest edition that supports Time Travel retention up to 90
days?

-   A. Standard
-   B. Premier
-   C. Enterprise
-   D. Business Critical

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------

## Question 98

Which statements about schemas are true? (Choose two.)

-   A. A schema contains databases
-   B. A database can contain schemas
-   C. A schema logically groups database objects
-   D. A schema is contained in a warehouse

<details>
<summary>Show Answer</summary>

**Correct Answer: B, C**

</details>

------------------------------------------------------------------------

## Question 99

True or False: A virtual warehouse can be resized while queries are
running.

-   A. True
-   B. False

<details>
<summary>Show Answer</summary>

**Correct Answer: A**

</details>

------------------------------------------------------------------------

## Question 100

What is the most granular object level at which
DATA_RETENTION_TIME_IN_DAYS can be set among these options?

-   A. Account
-   B. Database
-   C. Schema
-   D. Table

<details>
<summary>Show Answer</summary>

**Correct Answer: D**

</details>

------------------------------------------------------------------------

## Question 101

Which statement about Snowflake micro-partitioning is true?

-   A. It inherently introduces data skew
-   B. It requires a partitioning scheme up front
-   C. It is automatic and initially reflects the ordering of data as it
    is loaded/inserted
-   D. It can be disabled account-wide

<details>
<summary>Show Answer</summary>

**Correct Answer: C**

</details>

------------------------------------------------------------------------



====================================================================================================
# SnowPro_102-200.md
====================================================================================================

# SnowPro Core Practice Questions (102–200)

> Reformatted from a garbled source, cross-checked against current Snowflake documentation (July 2026). Where the original "community vote" answer was outdated or wrong based on current docs, it has been corrected and flagged with **⚠ Updated**.
>
> Click **Show Answer** to reveal each answer.

---

### Question 102
**True or False:** Snowflake bills for a minimum of five minutes each time a Virtual Warehouse is started.

<details><summary>Show Answer</summary>

**False.** Snowflake bills compute with a **60-second minimum** per start/resume, then per-second thereafter — not five minutes.
</details>

---

### Question 103
When scaling **up** a Virtual Warehouse (increasing its t-shirt size), you are primarily scaling for improved:

- -  A. Concurrency
- -  B. Performance

<details><summary>Show Answer</summary>

**-  B. Performance.** Scaling up gives a warehouse more compute power for complex/large queries. Scaling *out* (multi-cluster) is what improves concurrency.
</details>

---

### Question 104
As a best practice, clustering keys should only be considered for tables of which minimum size?

-  A. Multi-Kilobyte (KB) range
-  B. Multi-Megabyte (MB) range
-  C. Multi-Gigabyte (GB) range
-  D. Multi-Terabyte (TB) range

<details><summary>Show Answer</summary>

**-  D. Multi-Terabyte (TB) range.** Snowflake's automatic micro-partitioning is usually sufficient below this scale; clustering keys add reclustering costs, so they're recommended only for very large tables.
</details>

---

### Question 105
How are Snowpipe charges calculated?

-  A. Per-second, based on the warehouse t-shirt size used
-  B. Based on serverless compute resource consumption
-  C. Based on the number of pipes in the account
-  D. Based on total cloud storage bucket size

<details><summary>Show Answer</summary>

**-  B. Based on serverless compute resource consumption.**

**⚠ Updated:** Historically, Snowpipe was billed with **per-second/per-core granularity** on the serverless compute it consumed. As of the **2025-12-08 release**, Snowflake moved to **simplified per-GB pricing** — a fixed credit rate (0.0037 credits/GB, subject to change) per gigabyte of data ingested, rather than tracking compute-second/core utilization. Either way, Snowpipe is **not** billed by warehouse t-shirt size, pipe count, or storage bucket size, so B is still the best available answer, but the underlying billing mechanics have changed — verify current rates in the Snowflake Consumption Table.
</details>

---

### Question 106
**True or False:** A Snowflake account is charged for data stored in both internal and external stages.

<details><summary>Show Answer</summary>

**False.** Snowflake charges storage for **internal stages** (data lives in Snowflake-managed storage). Data in **external stages** resides in the customer's own cloud storage and is billed directly by the cloud provider, not by Snowflake.
</details>

---

### Question 107
**True or False:** When active, a Pipe uses a dedicated Virtual Warehouse.

<details><summary>Show Answer</summary>

**False.** Snowpipe uses Snowflake-managed **serverless compute**, not a customer-managed dedicated virtual warehouse.
</details>

---

### Question 108
**True or False:** Snowflake supports federated authentication in all editions.

<details><summary>Show Answer</summary>

**True.** Federated authentication (SSO) has been a baseline feature available in **all editions**, including Standard, since March 2019.
</details>

---

### Question 109
**True or False:** When a new Snowflake object is created, it is automatically owned by the user who created it.

<details><summary>Show Answer</summary>

**False.** In Snowflake's RBAC model, an object is owned by the **role** that was active in the session when the object was created — not the individual user.
</details>

---

### Question 110
**True or False:** A Virtual Warehouse consumes Snowflake credits even when inactive (suspended).

<details><summary>Show Answer</summary>

**False.** Suspended warehouses consume **zero credits**. Credits are only consumed while a warehouse is actively running.
</details>

---

### Question 111
**True or False:** During data unloading, only JSON and CSV files can be compressed.

<details><summary>Show Answer</summary>

**False.** Unloaded files can be compressed regardless of format (e.g., Parquet is compressed by default too), not just JSON/CSV.
</details>

---

### Question 112
Which of the following are options when creating a Virtual Warehouse? (Choose two.)

-  A. Auto-suspend
-  B. Auto-resume
-  C. Local SSD size
-  D. User count

<details><summary>Show Answer</summary>

**-  A. Auto-suspend** and **-  B. Auto-resume.** Local disk/SSD size and user count are not configurable warehouse creation parameters.
</details>

---

### Question 113
Which formats are supported for **unloading** data from Snowflake? (Choose two.)

-  A. Delimited (CSV, TSV, et-  C.)
-  B. Avro
-  C. JSON
-  D. ORC

<details><summary>Show Answer</summary>

**-  A. Delimited** and **-  C. JSON** (Parquet is also supported for unload, but wasn't offered as a valid pairing here). Avro, ORC, and XML are **load-only** formats — Snowflake cannot unload to them.
</details>

---

### Question 114
**True or False:** A Data Provider can share data with only a single Data Consumer.

<details><summary>Show Answer</summary>

**False.** A provider can share data with **multiple consumer accounts** simultaneously.
</details>

---

### Question 115
The Fail-safe retention period is how many days?

-  A. 1 day
-  B. 7 days
-  C. 45 days
-  D. 90 days

<details><summary>Show Answer</summary>

**-  B. 7 days.** This is a fixed, non-configurable period for all permanent tables in all editions.
</details>

---

### Question 116
**True or False:** Once created, a micro-partition will never be changed.

<details><summary>Show Answer</summary>

**True.** Micro-partitions are immutable. Any DML that modifies rows results in **new** micro-partitions being written; old ones are retained for Time Travel/Fail-safe until they age out.
</details>

---

### Question 117
What services does Snowflake automatically provide for customers that they may have previously been responsible for with an on-premises system? (Choose all that apply.)

-  A. Installing and configuring hardware
-  B. Patching software
-  C. Physical security
-  D. Maintaining metadata and statistics

<details><summary>Show Answer</summary>

**A, B, -  D.** Snowflake (via its cloud providers) also handles physical security, but in the classic SnowPro answer key this item is scoped to services Snowflake itself directly manages as a SaaS platform: hardware provisioning, software patching, and metadata/statistics maintenance.
</details>

---

### Question 118
Which of the following statements would be used to export/unload data from Snowflake?

-  A. `COPY INTO @stage`
-  B. `EXPORT TO @stage`
-  C. `INSERT INTO @stage`
-  D. `GET @stage`

<details><summary>Show Answer</summary>

**-  A. `COPY INTO @stage`.** This is the command used to unload table data to a stage.
</details>

---

### Question 119
**True or False:** A 4X-Large Warehouse may, at times, take longer to provision than an X-Small Warehouse.

<details><summary>Show Answer</summary>

**True.** Larger warehouses require more compute nodes to be provisioned, which can take more time, especially if there isn't spare capacity immediately available.
</details>

---

### Question 120
How would you determine the appropriate size of the virtual warehouse used for a task?

-  A. Since a root task may execute concurrently, leave margin in the execution window to avoid missed executions
-  B. Query the size of a stream's content to help determine warehouse size
-  C. If using a stored procedure to execute multiple SQL statements, test-run the procedure separately first to size the compute resource
-  D. Configure the warehouse for automatic concurrency handling using a multi-cluster warehouse to match the task schedule

<details><summary>Show Answer</summary>

**-  C.** Test-run the stored procedure separately (outside the task) to correctly size the warehouse before scheduling it as a task.
</details>

---

### Question 121
The Information Schema and Account Usage share provide storage information for which of the following objects? (Choose three.)

-  A. Users
-  B. Tables
-  C. Databases
-  D. Internal Stages

<details><summary>Show Answer</summary>

**B, C, D** — Tables, Databases, and Internal Stages. User objects don't have "storage" metrics tracked this way.
</details>

---

### Question 122
What is the default file format used in the `COPY INTO` command if one is not specified?

-  A. CSV
-  B. JSON
-  C. Parquet
-  D. XML

<details><summary>Show Answer</summary>

**-  A. CSV.**
</details>

---

### Question 123
**True or False:** Reader Accounts are able to extract data from shared data objects for use outside of Snowflake.

<details><summary>Show Answer</summary>

**False.** Reader accounts can only **query** shared data from within Snowflake — they cannot unload/export it for use outside the platform.
</details>

---

### Question 124
**True or False:** You can define multiple columns within a clustering key on a table.

<details><summary>Show Answer</summary>

**True.** A clustering key can be composed of multiple columns or expressions.
</details>

---

### Question 125
**True or False:** Snowflake enforces unique, primary key, and foreign key constraints during DML operations.

<details><summary>Show Answer</summary>

**False.** These constraint types are supported for **documentation/informational purposes** and by some tools, but are **not enforced** by Snowflake at DML time (NOT NULL is the exception — it *is* enforced).
</details>

---

### Question 126
**True or False:** Loading data into Snowflake requires that source data files be no larger than 16 M-  B.

<details><summary>Show Answer</summary>

**False.** There's no hard 16 MB limit on source file size for loading. Snowflake *recommends* compressed files in the 100–250 MB range for load efficiency, but larger files are allowed (they just load less efficiently/in parallel).
</details>

---

### Question 127
**True or False:** A Virtual Warehouse can be resized while suspended.

<details><summary>Show Answer</summary>

**True.** `ALTER WAREHOUSE ... SET WAREHOUSE_SIZE = ...` works whether the warehouse is running or suspended.
</details>

---

### Question 128
**True or False:** When you create a custom role, it is a best practice to immediately grant that role to ACCOUNTADMIN.

<details><summary>Show Answer</summary>

**False.** Best practice is to build a role hierarchy under **SYSADMIN**, not to grant custom roles directly to ACCOUNTADMIN (which should be reserved for account-level administration, not day-to-day object ownership).
</details>

---

### Question 129
Which of the following accurately represents how a table fits into Snowflake's logical container hierarchy?

-  A. Account → Table → Schema → Database
-  B. Account → Database → Schema → Table
-  C. Database → Table → Schema → Account
-  D. Table → Schema → Account → Database

<details><summary>Show Answer</summary>

**-  B. Account → Database → Schema → Table.**
</details>

---

### Question 130
**True or False:** All Snowflake table types include Fail-safe storage.

<details><summary>Show Answer</summary>

**False.** Only **permanent** tables have Fail-safe. Temporary and transient tables do not.
</details>

---

### Question 131
What are two ways to create and manage Data Shares in Snowflake? (Choose two.)

-  A. Via the Snowflake Web Interface (Snowsight)
-  B. Via a session parameter
-  C. Via SQL commands
-  D. Via Virtual Warehouses

<details><summary>Show Answer</summary>

**A** and **C** — through Snowsight or via SQL (`CREATE SHARE`, `GRANT ... TO SHARE`, et-  C.).
</details>

---

### Question 132
**True or False:** Time Travel can be completely disabled for a Snowflake account.

<details><summary>Show Answer</summary>

**False.** Time Travel cannot be turned off entirely. You can set `DATA_RETENTION_TIME_IN_DAYS = 0` at the account level (which effectively minimizes it for new objects), but the feature itself, and Fail-safe, cannot be disabled outright.
</details>

---

### Question 133
**True or False:** It is possible for a user to run a query against the query result cache without requiring an active Warehouse.

<details><summary>Show Answer</summary>

**True.** The result cache is served by the Cloud Services layer, so a **running warehouse is not required** to retrieve a previously cached result.
</details>

---

### Question 134
**True or False:** When Snowflake is configured to use Single Sign-On (SSO), Snowflake receives the usernames and credentials from the SSO service and loads them into the customer's Snowflake account.

<details><summary>Show Answer</summary>

**False.** In federated authentication, Snowflake never receives or stores the user's IdP credentials — only a signed SAML assertion confirming successful authentication.
</details>

---

### Question 135
Which of the following are best practices for loading data into Snowflake? (Choose three.)

-  A. Aim to produce compressed data files in the 100–250 MB range
-  B. Load data from a cloud storage service in a different region/platform than your Snowflake account, to save on cost
-  C. Enclose fields that contain delimiter characters in single or double quotes
-  D. Split large files into a greater number of smaller files to better distribute the load across compute resources
-  E. When planning warehouse size for loading, start with the largest warehouse possible
-  F. Partition staged data into large folders with random paths, letting Snowflake determine the best load strategy

<details><summary>Show Answer</summary>

**A, C, -  D.**
</details>

---

### Question 136
Which feature is used both for querying and for restoring data?

-  A. Clustering keys
-  B. Time Travel
-  C. Fail-safe
-  D. Cloning

<details><summary>Show Answer</summary>

**-  B. Time Travel** — you can both query historical data (`AT`/`BEFORE`) and restore dropped objects (`UNDROP`) with it. Fail-safe is restore-only (and only by Snowflake Support), not queryable by users.
</details>

---

### Question 137
What do the terms "scale up" and "scale out" refer to in Snowflake? (Choose two.)

-  A. Scaling out adds clusters of the same size to a virtual warehouse to handle more concurrent queries
-  B. Scaling out adds clusters of varying sizes to a virtual warehouse
-  C. Scaling out adds additional database servers to an existing running cluster
-  D. Snowflake recommends using both scaling up and scaling out together to handle more concurrent queries
-  E. Scaling up resizes a virtual warehouse so it can handle more complex workloads
-  F. Scaling up adds additional database servers to an existing running cluster

<details><summary>Show Answer</summary>

**A** and **-  E.**
</details>

---

### Question 138
What is the minimum Snowflake edition that has column-level security enabled?

-  A. Standard
-  B. Enterprise
-  C. Business Critical
-  D. Virtual Private Snowflake

<details><summary>Show Answer</summary>

**-  B. Enterprise** (or higher). Confirmed current in Snowflake's edition documentation.
</details>

---

### Question 139
What parameter controls whether a virtual warehouse starts immediately after the `CREATE WAREHOUSE` statement runs?

-  A. `INITIALLY_SUSPENDED = TRUE | FALSE`
-  B. `AUTO_RESUME = TRUE | FALSE`
-  C. `START_TIME = 60` (seconds from now)
-  D. `START_TIME = CURRENT_DATE()`

<details><summary>Show Answer</summary>

**-  A. `INITIALLY_SUSPENDED`.**
</details>

---

### Question 140
When cloning a database, what is cloned with it? (Choose two.)

-  A. Privileges granted **on** the database object itself
-  B. Existing child objects within the database
-  C. Future child objects (created after the clone) within the database
-  D. Privileges on the schemas/objects **within** the database
-  E. Only schemas and tables (no other object types)

<details><summary>Show Answer</summary>

**B** and **-  D.** Existing child objects are copied into the clone, and grants that exist on those child objects carry over — but privileges granted directly **on** the database object itself are not copied, and future objects obviously aren't included since they didn't exist yet.
</details>

---

### Question 141
Which of the following describes the Snowflake Cloud Services layer?

-  A. Coordinates activities across the Snowflake account (authentication, metadata, optimization, et-  C.)
-  B. Executes queries submitted by Snowflake users
-  C. Manages quotas on Snowflake account storage
-  D. Manages the virtual warehouse cache to speed up queries

<details><summary>Show Answer</summary>

**-  A.** The Cloud Services layer coordinates the platform (auth, metadata, query parsing/optimization, security) — it does **not** execute queries (that's compute) or manage the local warehouse cache.
</details>

---

### Question 142
What is the maximum total Continuous Data Protection (CDP) time incurred for a temporary table?

-  A. 30 days
-  B. 7 days
-  C. 48 hours
-  D. 24 hours

<details><summary>Show Answer</summary>

**-  D. 24 hours.** Temporary tables get up to 1 day of Time Travel and no Fail-safe, since they don't persist beyond the session/24 hours.
</details>

---

### Question 143
When reviewing a Query Profile, what is a symptom that a query is too large to fit into memory?

-  A. A single join node uses more than [X]% of query time
-  B. Partitions scanned equals partitions total
-  C. An Aggregate operator node is present
-  D. The query is spilling to local or remote storage

<details><summary>Show Answer</summary>

**-  D. The query is spilling to storage.** Spilling (especially to remote/cloud storage) indicates the warehouse doesn't have enough memory for the operation and is a classic sign to resize up.
</details>

---

### Question 144
What type of query benefits the **most** from Search Optimization?

-  A. A query using only disjunction (OR) predicates
-  B. A query that includes analytical expressions
-  C. A query that uses equality predicates or predicates using `IN`
-  D. A query that filters on semi-structured data types

<details><summary>Show Answer</summary>

**-  C.** Search Optimization is designed for point-lookup queries — equality and `IN` predicates on high-cardinality columns.
</details>

---

### Question 145
What transformations are supported in a `CREATE PIPE AS COPY FROM (SELECT ...)` statement? (Choose two.)

-  A. Data can be filtered by an optional `WHERE` clause
-  B. Incoming data can be joined with other tables
-  C. Columns can be reordered
-  D. Columns can be omitted
-  E. Row-level access can be defined

<details><summary>Show Answer</summary>

**C** and **-  D.** Snowpipe's `COPY` transformation supports column reordering, casting, and omission — but not joins, filters, or row access policies during the copy.
</details>

---

### Question 146
Which of the following are characteristics of Snowflake virtual warehouses? (Choose two.)

-  A. Auto-suspend applies only to the last-started warehouse in a multi-cluster warehouse
-  B. The ability to auto-suspend is only available in Enterprise Edition or above
-  C. SnowSQL supports both a configuration file and a command-line option for specifying a default warehouse
-  D. A user cannot specify a default warehouse when using the ODBC driver
-  E. The default virtual warehouse size can be changed at any time

<details><summary>Show Answer</summary>

**C** and **-  E.**
</details>

---

### Question 147
Which command should be used to load data from a file located in an external stage into a table in Snowflake?

-  A. `INSERT`
-  B. `PUT`
-  C. `GET`
-  D. `COPY INTO`

<details><summary>Show Answer</summary>

**-  D. `COPY INTO <table>`.**
</details>

---

### Question 148
The Snowflake Data Cloud platform is described as having which of the following architectures?

-  A. Shared-disk
-  B. Shared-nothing
-  C. Multi-cluster, shared data
-  D. Serverless query engine

<details><summary>Show Answer</summary>

**-  C. Multi-cluster, shared data architecture.**
</details>

---

### Question 149
Which of the following is a data tokenization integration partner?

-  A. Protegrity
-  B. Tableau

<details><summary>Show Answer</summary>

**-  A. Protegrity.**
</details>

---

### Question 150
Which editions of Snowflake are commonly used to help manage compliance with Personal Identifiable Information (PII) requirements? (Choose two.)

-  A. Custom Edition
-  B. Virtual Private Snowflake
-  C. Business Critical Edition
-  D. Standard Edition
-  E. Enterprise Edition

<details><summary>Show Answer</summary>

**B** and **C** — Virtual Private Snowflake and Business Critical Edition provide the enhanced data protection features most relevant to sensitive/PII data compliance requirements.
</details>

---

### Question 151
What are supported file formats for **unloading** data from Snowflake? (Choose three.)

-  A. XML
-  B. JSON
-  C. Parquet
-  D. ORC
-  E. Avro
-  F. CSV

<details><summary>Show Answer</summary>

**B, C, F — JSON, Parquet, and CSV.**

**⚠ Updated:** The original source listed the answer as JSON/Parquet/Avro. Per current Snowflake documentation, `COPY INTO <location>` only supports **delimited (CSV/TSV), JSON, and Parquet** for unloading. XML, ORC, and Avro are **load-only** formats and cannot be used to unload dat-  A.
</details>

---

### Question 152
The Snowflake Cloud Services layer is responsible for which two of the following tasks?

-  A. Local disk caching
-  B. Authentication and access control
-  C. Metadata management
-  D. Query processing (execution)
-  E. Database storage

<details><summary>Show Answer</summary>

**B** and **-  C.**
</details>

---

### Question 153
What is a key feature of Snowflake's architecture?

-  A. Zero-copy cloning creates a mirror copy of a database that updates with the original
-  B. Software updates are automatically applied on a quarterly basis
-  C. Snowflake eliminates resource contention with its virtual warehouse implementation
-  D. Multi-cluster warehouses allow users to run a single query that spans across multiple clusters
-  E. Snowflake sorts data on ingest for fast retrieval by date

<details><summary>Show Answer</summary>

**-  C.** Because each virtual warehouse is an independent compute cluster operating on the same shared storage layer, workloads in one warehouse don't compete for resources with workloads in another.
</details>

---

### Question 154
When publishing a Snowflake Data Marketplace listing into a remote region, what should be taken into consideration? (Choose two.)

-  A. There is a need to have, in the target region, a share created for each consumer
-  B. The listing metadata is replicated into all selected regions automatically, but the underlying data is not replicated until requested
-  C. The user must have the ORGADMIN role in at least one account to link accounts for replication
-  D. Shares attached to listings in remote regions can be viewed from any account in the organization
-  E. For a standard listing, the provider can wait until the first customer requests the data before replicating it to the target region

<details><summary>Show Answer</summary>

**B** and **-  E.**
</details>

---

### Question 155
When loading data into Snowflake via Snowpipe, what is the recommended compressed file size?

-  A. 10–50 MB
-  B. 100–250 MB
-  C. 300–500 MB
-  D. 1000–1500 MB

<details><summary>Show Answer</summary>

**-  B. 100–250 M-  B.**
</details>

---

### Question 156
Which Snowflake feature allows a user to substitute a randomly generated identifier for sensitive data — to prevent unauthorized users from accessing the real data — **before** loading it into Snowflake?

-  A. External Tokenization
-  B. External Tables
-  C. Materialized Views
-  D. Table Functions (UDTFs)

<details><summary>Show Answer</summary>

**-  A. External Tokenization.**
</details>

---

### Question 157
Which of the following are examples of operations that require an active Virtual Warehouse to complete, assuming no queries have been executed previously (i.e., nothing is cached)? (Choose three.)

-  A. `MIN(<column>)`
-  B. `COPY`
-  C. `SUM(<column>)`
-  D. `UPDATE`

<details><summary>Show Answer</summary>

**B, C, -  D.** `COPY`, `SUM()`, and `UPDATE` all require compute. A simple `MIN()`/`MAX()` with no `WHERE` clause can sometimes be resolved directly from micro-partition metadata (which Snowflake maintains regardless of warehouse state), without needing an active warehouse.
</details>

---

### Question 158
What `SNOWFLAK-  E.ACCOUNT_USAGE` view contains information about which objects were read by queries within the last 365 days?

-  A. `VIEWS_HISTORY`
-  B. `OBJECT_HISTORY`
-  C. `ACCESS_HISTORY`
-  D. `LOGIN_HISTORY`

<details><summary>Show Answer</summary>

**-  C. `ACCESS_HISTORY`.**
</details>

---

### Question 159
Which feature is only available in the Enterprise Edition or higher?

-  A. Column-level security
-  B. SOC 2 Type II certification
-  C. Multi-factor Authentication (MFA)
-  D. Object-level access control

<details><summary>Show Answer</summary>

**-  A. Column-level security.** SOC 2 Type II, MFA, and object-level access control are available in all editions, including Standard.
</details>

---

### Question 160
Will data cached in a warehouse be lost when the warehouse is resized?

-  A. Possibly — if resized to a smaller size, the cache may no longer fit
-  B. Yes, because the compute resource is replaced in its entirety with a new compute resource
-  C. No, because the size of the cache is independent from the warehouse size
-  D. Yes, because the compute resource will no longer have access to the cache encryption key

<details><summary>Show Answer</summary>

**-  B.** Resizing a warehouse provisions new compute nodes, so the previous local disk cache is lost regardless of direction (larger or smaller).
</details>

---

### Question 161
Which semi-structured file formats are supported when **unloading** data from a table? (Choose two.)

-  A. ORC
-  B. XML
-  C. Avro
-  D. Parquet
-  E. JSON

<details><summary>Show Answer</summary>

**D** and **E — Parquet and JSON.** ORC, XML, and Avro are load-only formats.
</details>

---

### Question 162
A running virtual warehouse is suspended, then restarted. What is the **minimum** amount of time that the warehouse will be billed for upon restart?

-  A. 1 second
-  B. 60 seconds
-  C. 5 minutes
-  D. 60 minutes

<details><summary>Show Answer</summary>

**-  B. 60 seconds.** Per-second billing kicks in after the first minute.
</details>

---

### Question 163
What are the responsibilities of Snowflake's Cloud Services layer? (Choose three.)

-  A. Authentication
-  B. Resource management
-  C. Virtual warehouse local disk caching
-  D. Query parsing and optimization
-  E. Query execution
-  F. Physical storage of micro-partitions

<details><summary>Show Answer</summary>

**A, B, -  D.** Query execution (E) happens in the compute layer, and warehouse-local caching (C) and micro-partition storage (F) belong to the compute and storage layers respectively — not Cloud Services.
</details>

---

### Question 164
How long is the Fail-safe period for temporary and transient tables?

-  A. There is no Fail-safe period for these tables
-  B. 1 day
-  C. 14 days
-  D. 31 days
-  E. 90 days

<details><summary>Show Answer</summary>

**-  A. No Fail-safe period.** Only permanent tables have Fail-safe.
</details>

---

### Question 165
Which command should be used to download files from a Snowflake stage to a local folder on a client machine?

-  A. `PUT`
-  B. `GET`
-  C. `COPY INTO`
-  D. `SELECT`

<details><summary>Show Answer</summary>

**-  B. `GET`.**
</details>

---

### Question 166
How does Snowflake Fail-safe protect data in a table?

-  A. Fail-safe makes data available for up to 1 day, recoverable by user operations
-  B. Fail-safe makes data available for 7 days, recoverable by user operations
-  C. Fail-safe makes data available for 7 days, recoverable only by Snowflake Support
-  D. Fail-safe makes data available for up to 1 day, recoverable only by Snowflake Support

<details><summary>Show Answer</summary>

**-  C.** Fail-safe is a non-configurable, 7-day, disaster-recovery-only mechanism that requires contacting Snowflake Support — end users cannot self-service recover from it.
</details>

---

### Question 167
A virtual warehouse is created:
```sql
CREATE WAREHOUSE my_wh WITH
  WAREHOUSE_SIZE = MEDIUM
  AUTO_SUSPEND = 60
  AUTO_RESUME = TRUE;
```
Its utilization graph over two days shows frequent, spiky bursts of concurrent activity throughout the day. What action should be taken to address this situation?

-  A. Increase the warehouse size from Medium to 2X-Large
-  B. Increase the value of `AUTO_SUSPEND`
-  C. Configure the warehouse as a multi-cluster warehouse
-  D. Lower the value of `AUTO_SUSPEND`

<details><summary>Show Answer</summary>

**-  C.** Bursty, concurrent workload patterns are best handled by **multi-cluster warehouses**, which spin additional clusters up/down automatically to absorb concurrency spikes — resizing (A) helps single-query performance, not concurrency.
</details>

---

### Question 168
Which minimum Snowflake edition provides a fully dedicated, isolated environment (including a dedicated metadata/cloud services layer not shared with other accounts)?

-  A. Standard
-  B. Enterprise
-  C. Business Critical
-  D. Virtual Private Snowflake

<details><summary>Show Answer</summary>

**-  D. Virtual Private Snowflake (VPS).** VPS is Snowflake's highest tier, offering a completely separate environment with no shared hardware/resources with accounts outside the VPS.
</details>

---

### Question 169
Network policies can be set at which Snowflake levels? (Choose two.)

-  A. Role
-  B. Schema
-  C. User
-  D. Database
-  E. Account
-  F. Table

<details><summary>Show Answer</summary>

**C** and **E** — User and Account levels (network policies can also be attached to security integrations in current Snowflake, but of the options given, User and Account are correct).
</details>

---

### Question 170
What are the correct default parameters for Time Travel and Fail-safe in Snowflake **Enterprise Edition**?

-  A. Default Time Travel = 0 days, Max Time Travel = 30 days, Fail-safe = 1 day
-  B. Default Time Travel = 1 day, Max Time Travel = 365 days, Fail-safe = 7 days
-  C. Default Time Travel = 0 days, Max Time Travel = 90 days, Fail-safe = 7 days
-  D. Default Time Travel = 1 day, Max Time Travel = 90 days, Fail-safe = 7 days
-  E. Default Time Travel = 7 days, Max Time Travel = 1 day, Fail-safe = 90 days

<details><summary>Show Answer</summary>

**-  D.** Default Time Travel retention is 1 day, extendable up to a maximum of 90 days with Enterprise Edition or higher, and Fail-safe is a fixed 7 days. Confirmed current against Snowflake's Time Travel documentation.
</details>

---

### Question 171
Which of the following objects are contained within a schema? (Choose two.)

-  A. Role
-  B. Table
-  C. Warehouse
-  D. External table
-  E. User
-  F. Share

<details><summary>Show Answer</summary>

**B** and **D** — Tables and External Tables. Roles, warehouses, users, and shares are all account-level objects, not schema-level objects.
</details>

---

### Question 172
Which of the following statements describe features of Snowflake data caching? (Choose two.)

-  A. When a virtual warehouse is suspended, its local disk data cache is saved to remote storage
-  B. When the data cache is full, the least-recently-used data is cleared to make room
-  C. A user can only access their own queries from the query result cache
-  D. A user must set a parameter to `TRUE` to enable the metadata cache
-  E. The `RESULT_SCAN` table function can access and filter the contents of the query result cache

<details><summary>Show Answer</summary>

**B** and **-  E.**
</details>

---

### Question 173
A table needs to be loaded. The input data is in JSON format, consisting of a concatenation of multiple JSON documents. The file is 3 GB, and an X-Small warehouse is being used with:
```sql
COPY INTO sample FROM @stage FILE_FORMAT = (TYPE = JSON)
```
The load fails with:
```
Max LOB size (16777216) exceeded. Actual size of parsed column is 17894470.
```
How can this issue be resolved?

-  A. Compress the file before loading it
-  B. Split the file into multiple files in the recommended 100–250 MB size range
-  C. Use a larger-sized warehouse
-  D. Set `STRIP_OUTER_ARRAY = TRUE` in the `COPY INTO` command

<details><summary>Show Answer</summary>

**-  D.** The error means a single parsed VARIANT value exceeds the 16 MB limit — this happens when multiple JSON documents are wrapped/concatenated into one oversized structure. `STRIP_OUTER_ARRAY = TRUE` breaks the outer array into individual rows so each parsed value stays under the limit.
</details>

---

### Question 174
What is a feature of a stored procedure in Snowflake?

-  A. They can access secured metadata across all databases regardless of role
-  B. They can only access tables from a single database
-  C. They can only contain a single SQL statement
-  D. They can be created to run with either the caller's rights or the owner's rights

<details><summary>Show Answer</summary>

**-  D.** Stored procedures support both **caller's rights** and **owner's rights** execution contexts.
</details>

---

### Question 175
Which columns are part of the result set of the `LATERAL FLATTEN` command? (Choose two.)

-  A. `CONTENT`
-  B. `PATH`
-  C. `BYTE_SIZE`
-  D. `INDEX`
-  E. `DATATYPE`

<details><summary>Show Answer</summary>

**B** and **D** — `PATH` and `INDEX`. The full `FLATTEN` output includes `SEQ`, `KEY`, `PATH`, `INDEX`, `VALUE`, and `THIS` — not `CONTENT`, `BYTE_SIZE`, or `DATATYPE`.
</details>

---

### Question 176
What is the minimum edition required to create a materialized view?

-  A. Standard Edition
-  B. Enterprise Edition
-  C. Business Critical Edition
-  D. Virtual Private Snowflake Edition

<details><summary>Show Answer</summary>

**-  B. Enterprise Edition** (or higher). Confirmed current.
</details>

---

### Question 177
Which Snowflake function interprets an input string as a JSON document and produces a VARIANT value?

<details><summary>Show Answer</summary>

**`PARSE_JSON`.**
</details>

---

### Question 178
How are serverless features generally billed?

-  A. Per second, multiplied by an automatic sizing determined for the job
-  B. Per minute, multiplied by an automatic sizing, with a minimum of one minute
-  C. Per second, multiplied by a fixed size set by a parameter
-  D. Serverless features are not billed unless the total monthly cost exceeds a set percentage of warehouse credits

<details><summary>Show Answer</summary>

**-  A.** Most serverless features (Automatic Clustering, Search Optimization, Query Acceleration, et-  C.) bill per-second based on compute that Snowflake automatically sizes for the job — with no fixed minimum.

**Note:** Snowpipe specifically switched to a flat **per-GB** pricing model as of December 2025 (see Question 105), so it's now an exception to this general per-second serverless billing pattern.
</details>

---

### Question 179
Which Snowflake architectural layer is responsible for generating a query execution plan?

-  A. Compute
-  B. Data storage
-  C. Cloud Services
-  D. Cloud provider

<details><summary>Show Answer</summary>

**-  C. Cloud Services.** Query parsing and optimization happen here before execution is handed off to the compute (warehouse) layer.
</details>

---

### Question 180
When unloading data to a stage, which of the following is a recommended practice?

-  A. Set `SINGLE = TRUE` for larger files
-  B. Use headers when unloading with Parquet
-  C. Avoid the use of the `CAST` function
-  D. Define an individual, explicit file format

<details><summary>Show Answer</summary>

**-  D. Define an individual file format** rather than relying on defaults, so unload behavior (compression, delimiters, headers, et-  C.) is explicit and predictable.
</details>

---

### Question 181
Which SQL commands, when committed, will consume a stream and advance its offset? (Choose two.)

-  A. `UPDATE ... FROM STREAM`
-  B. `SELECT * FROM STREAM`
-  C. `INSERT INTO table SELECT * FROM STREAM`
-  D. `ALTER TABLE ... AS SELECT FROM STREAM`
-  E. `BEGIN ... COMMIT` (empty transaction)

<details><summary>Show Answer</summary>

**A** and **-  C.** A DML statement that references the stream as its source and is committed advances the stream's offset. A plain `SELECT` does not consume the stream.
</details>

---

### Question 182
Which methods can be used to delete staged files from a Snowflake stage? (Choose two.)

-  A. Use the `DROP FILE` command after the load completes
-  B. Specify a purge option when creating the file format
-  C. Specify the `PURGE` copy option in the `COPY INTO <table>` command
-  D. Use the `REMOVE` command after the load completes
-  E. Use a `DELETE LOAD HISTORY` command after the load completes

<details><summary>Show Answer</summary>

**C** and **-  D.**
</details>

---

### Question 183
On which of the following cloud platforms can a Snowflake account be hosted? (Choose three.)

-  A. Amazon Web Services
-  B. Private Virtual Cloud
-  C. Oracle Cloud
-  D. Microsoft Azure
-  E. Google Cloud Platform
-  F. Alibaba Cloud

<details><summary>Show Answer</summary>

**A, D, E — AWS, Microsoft Azure, and Google Cloud Platform.**
</details>

---

### Question 184
What Snowflake role must be granted for a user to create and manage additional Snowflake **accounts**?

-  A. ACCOUNTADMIN
-  B. ORGADMIN
-  C. SECURITYADMIN
-  D. SYSADMIN

<details><summary>Show Answer</summary>

**-  B. ORGADMIN.** This role manages operations at the organization level, including creating new accounts.
</details>

---

### Question 185
Assume a table consists of five micro-partitions with values ranging from A to Z. Which layout indicates a **well-clustered** table?

<details><summary>Show Answer</summary>

A well-clustered table is one where each micro-partition contains a **narrow, largely non-overlapping** range of the clustering key's values (e.g., partition 1 = A–E, partition 2 = F–J, et-  C.), rather than every partition containing values scattered across the full A–Z range. Narrow, non-overlapping ranges allow Snowflake to prune (skip) most partitions when a query filters on the clustering key.

*(Note: the original source referenced a diagram that wasn't legible/reproducible from the source material — the concept above is what the correct diagram choice represents.)*
</details>

---

### Question 186
What feature can be used to reorganize a very large table on one or more columns to improve pruning?

-  A. Micro-partitions
-  B. Clustering keys
-  C. Key partitions
-  D. Clustered partitions

<details><summary>Show Answer</summary>

**-  B. Clustering keys.**
</details>

---

### Question 187
What is an advantage of using an Explain Plan instead of the Query Profiler to evaluate query performance?

-  A. The plan output is available graphically
-  B. An Explain Plan can be used to analyze performance **without executing** the query
-  C. An Explain Plan handles queries with temporary tables while the Query Profiler will not
-  D. An Explain Plan's output displays automatic data-skew optimization information

<details><summary>Show Answer</summary>

**-  B.** `EXPLAIN` shows the planned execution path without actually running (and paying for) the query.
</details>

---

### Question 188
Which data types are supported by Snowflake for semi-structured data? (Choose two.)

-  A. VARIANT
-  B. VARRAY
-  C. STRUCT
-  D. ARRAY
-  E. QUEUE

<details><summary>Show Answer</summary>

**A** and **D — VARIANT and ARRAY.** (OBJECT is the third semi-structured type, but wasn't offered here.) VARRAY, STRUCT, and QUEUE are not Snowflake semi-structured data types.
</details>

---

### Question 189
Why does Snowflake recommend file sizes of 100–250 MB compressed when loading data?

-  A. Optimizes the virtual warehouse's multi-cluster setting to economy mode
-  B. Allows a user to import files in a strictly sequential order
-  C. Increases latency during staging and accuracy when loading data
-  D. Allows optimization of parallel operations

<details><summary>Show Answer</summary>

**-  D.** This file size range lets Snowflake distribute the load efficiently across all available compute threads/nodes for maximum load parallelism.
</details>

---

### Question 190
Which of the following features are available with the Snowflake **Enterprise** edition? (Choose two.)

-  A. Database replication and failover
-  B. Automated index management
-  C. Customer-managed encryption keys (Tri-Secret Secure)
-  D. Extended Time Travel (up to 90 days)
-  E. Native support for geospatial data

<details><summary>Show Answer</summary>

**A** and **D — Database replication/failover, and Extended Time Travel.**

**⚠ Updated:** The original source listed D and E as correct. That's outdated/incorrect:
- **Geospatial data support (E) is available in all editions**, including Standard — it is not Enterprise-exclusive.
- **Snowflake has no concept of "indexes"** (option B doesn't exist as a real feature), so it's a distractor.
- **Tri-Secret Secure / customer-managed keys (C) require Business Critical Edition**, not Enterprise.
- Extended Time Travel up to 90 days and cross-account database replication/failover are genuinely Enterprise-tier features, so **A and D** are correct.
</details>

---

### Question 191
What is the default file size limit when unloading data from Snowflake using the `COPY INTO` command?

-  A. 1 MB
-  B. 8 GB
-  C. 16 MB
-  D. 32 MB

<details><summary>Show Answer</summary>

**-  C. 16 MB** (per unloaded file, unless `MAX_FILE_SIZE` is set otherwise).
</details>

---

### Question 192
What features that are part of the Continuous Data Protection (CDP) feature set do **not require additional configuration**? (Choose two.)

-  A. Row access policies
-  B. Data masking policies
-  C. Data encryption
-  D. Time Travel
-  E. External tokenization

<details><summary>Show Answer</summary>

**C** and **D — Data encryption and Time Travel.** Both are automatically on for every account/object with no setup required. Masking policies, row access policies, and external tokenization all require explicit configuration by an administrator.
</details>

---

### Question 193
Which Snowflake layer is always leveraged when accessing a query from the result cache?

-  A. Metadata
-  B. Data Storage
-  C. Compute
-  D. Cloud Services

<details><summary>Show Answer</summary>

**-  D. Cloud Services.** The result cache is managed and served by the Cloud Services layer, which is why it can be used without an active warehouse.
</details>

---

### Question 194
Which connectors are available in the downloads section of the Snowflake web interface? (Choose two.)

-  A. SnowSQL
-  B. JDBC
-  C. ODBC
-  D. Hive
-  E. Scala

<details><summary>Show Answer</summary>

**A** and **C — SnowSQL and ODB-  C.**
</details>

---

### Question 195
A Snowflake Administrator needs to ensure that sensitive corporate data in Snowflake tables is not visible to end users, but is partially visible to functional managers. How can this requirement be met?

-  A. Use data encryption
-  B. Use dynamic data masking
-  C. Use secure materialized views
-  D. Revoke all roles for functional managers and end users

<details><summary>Show Answer</summary>

**-  B. Dynamic data masking.** A masking policy can be written to reveal full, partial, or masked values depending on the querying role.
</details>

---

### Question 196
Users are responsible for data storage costs until what occurs?

-  A. Data expires from Time Travel
-  B. Data expires from Fail-safe
-  C. Data is deleted from a table
-  D. Data is truncated from a table

<details><summary>Show Answer</summary>

**-  B. Data expires from Fail-safe.** Storage costs continue to accrue as long as the historical data is retained anywhere — including through the entire Time Travel *and* the subsequent 7-day Fail-safe period.
</details>

---

### Question 197
A user has an application that writes a new file to a cloud storage location every 5 minutes. What is the **most efficient** way to get these files into Snowflake?

-  A. Create a task that runs a `COPY INTO` from an external stage every 5 minutes
-  B. Create a task that `PUT`s the files into an internal stage and automates the data load
-  C. Create a task that runs a `GET` operation to intermittently check for new files
-  D. Set up cloud provider event notifications on the storage location and use Snowpipe with auto-ingest

<details><summary>Show Answer</summary>

**-  D.** Snowpipe with event-based auto-ingest is designed exactly for this near-real-time, continuous ingestion pattern — it avoids the overhead and latency of a fixed polling schedule.
</details>

---

### Question 198
What affects whether the query result cache can be used?

-  A. Whether the query contains a deterministic function
-  B. Whether the virtual warehouse has been suspended
-  C. Whether the referenced data in the table has changed
-  D. Whether multiple users are using the same virtual warehouse

<details><summary>Show Answer</summary>

**-  C.** If the underlying table's data changed since the result was cached, the cache is invalidated for that query.
</details>

---

### Question 199
Which of the following is an example of an operation that can be completed **without** requiring compute, assuming no queries have been executed previously?

-  A. `SELECT AVG(ORDER_AMT) FROM SALES`
-  B. `SELECT * FROM SALES`
-  C. `SELECT MIN(ORDER_AMT) FROM SALES`
-  D. `SELECT ORDER_AMT, ORDER_QTY FROM SALES`

<details><summary>Show Answer</summary>

**-  C.** A simple, unfiltered `MIN()`/`MAX()` can be answered directly from micro-partition metadata that Snowflake already maintains, without spinning up compute — unlike `AVG()`, `SELECT *`, or multi-column projections, which require scanning actual dat-  A.
</details>

---

### Question 200
How many days is Snowpipe load history retained?

-  A. 1 day
-  B. 30 days
-  C. 14 days
-  D. 60 days

<details><summary>Show Answer</summary>

**-  C. 14 days.**
</details>

---

## Summary of Corrections Made vs. the Original Source

| Question | Change |
|---|---|
| 105 | Clarified that Snowpipe billing moved from per-second/per-core granularity to **flat per-GB pricing** as of Dec 8, 2025. |
| 151 | Corrected unload-supported formats to **JSON, Parquet, CSV** (removed Avro, which is load-only). |
| 161 | Confirmed only **Parquet and JSON** are valid semi-structured unload formats (not ORC/XML/Avro). |
| 178 | Clarified this general serverless billing rule now has an exception for Snowpipe's new flat-rate model. |
| 190 | Corrected Enterprise-exclusive features to **Database replication/failover + Extended Time Travel**, removing "native geospatial support" (available in *all* editions, not Enterprise-only) and the non-existent "automated index management." |

All other answers were checked against current Snowflake documentation (as of July 2026) and found to still be accurate.



====================================================================================================
# snowpro_200-300.md
====================================================================================================

# SnowPro Core Practice Questions (201–300)

*Reconstructed and cleaned from a garbled OCR source. Answers have been cross-checked against current Snowflake documentation (as of July 2026); corrections are flagged with ⚠ Updated. Questions are renumbered sequentially for clarity, since the original numbering in the source was inconsistent.*

---

### Question 201
What Snowflake features support virtual warehouses in handling high-concurrency workloads? (Choose two.)

- A. The ability to add warehouses
- B. The use of warehouse auto-scaling
- C. The ability to resize warehouses
- D. The use of multi-clustered warehouses
- E. The use of warehouse indexing

<details><summary>Show Answer</summary>
Correct Answer: B, D. Multi-cluster warehouses (with auto-scaling) automatically start and stop additional clusters to absorb concurrent query load. Resizing (C) helps individual query performance, not concurrency, and "warehouse indexing" (E) is not a real Snowflake feature.
</details>

---

### Question 202
Which `COPY INTO <location>` option outputs the unloaded data into a single file?

- A. `SINGLE = TRUE`
- B. `MAX_FILE_SIZE`
- C. `FILE_FORMAT`
- D. `MULTIPLE = FALSE`

<details><summary>Show Answer</summary>
Correct Answer: A. Setting `SINGLE = TRUE` in `COPY INTO <location>` unloads all query results into one file instead of Snowflake's default of splitting output into multiple files.
</details>

---

### Question 203
In which scenarios would an account pay Cloud Services costs? (Choose two.)

- A. Compute Credits = 50, Cloud Services Credits = 10
- B. Compute Credits = 80, Cloud Services Credits = 5
- C. Compute Credits = 100, Cloud Services Credits = 8
- D. Compute Credits = 120, Cloud Services Credits = 10
- E. Compute Credits = 200, Cloud Services Credits = 26

<details><summary>Show Answer</summary>
Correct Answer: A, E. Snowflake only charges for Cloud Services usage that exceeds 10% of daily compute credit consumption. A (10 > 5) and E (26 > 20) both exceed that 10% threshold; B, C, and D all fall at or under it.
</details>

---

### Question 204
A user created a new worksheet within the Snowsight UI and wants to share it with teammates. How can this worksheet be shared?

- A. Create a zero-copy clone of the worksheet and grant permissions to teammates.
- B. Create a private Data Exchange so that any teammate can use the worksheet.
- C. Share the worksheet with teammates directly within Snowsight.
- D. Create a database and grant all permissions to teammates.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowsight worksheets have a native "Share" option that lets you grant view or edit access to specific users or roles.
</details>

---

### Question 205
How can a row access policy be applied to a table or a view? (Choose two.)

- A. Within the policy DDL at creation time
- B. Within the `CREATE TABLE` or `CREATE VIEW` statement
- C. Via a future grant that applies the policy to all objects in a schema
- D. Within a separate control table
- E. Using the command `ALTER <object> ADD ROW ACCESS POLICY <policy>`

<details><summary>Show Answer</summary>
Correct Answer: B, E. A row access policy can be attached when the table/view is first created, or later via `ALTER TABLE`/`ALTER VIEW ... ADD ROW ACCESS POLICY`.
</details>

---

### Question 206
Which command can be used to load local data files into a Snowflake stage?

- A. `JOIN`
- B. `COPY INTO`
- C. `PUT`
- D. `GET`

<details><summary>Show Answer</summary>
Correct Answer: C. `PUT` uploads (stages) local files into a Snowflake stage. `COPY INTO` then loads staged files into a table, and `GET` downloads files from a stage back to local storage.
</details>

---

### Question 207
What types of data listings are available in the Snowflake Marketplace? (Choose two.)

- A. Reader
- B. Consumer
- C. Vendor
- D. Standard
- E. Personalized

<details><summary>Show Answer</summary>
Correct Answer: D, E. Snowflake Marketplace listings are published as either Standard listings (available to any consumer) or Personalized listings (shared with a specific consumer account).
</details>

---

### Question 208
What is the maximum Time Travel retention period for a temporary Snowflake table?

- A. 90 days
- B. 1 day
- C. 7 days
- D. 45 days

<details><summary>Show Answer</summary>
Correct Answer: B. Temporary tables (like transient tables) support a maximum Time Travel retention of 1 day, and they exist only for the session in which they were created.
</details>

---

### Question 209
When should a multi-cluster warehouse be used in auto-scale mode?

- A. When it is unknown how much compute power is needed
- B. If the SELECT statement contains a large number of CTEs
- C. If the runtime of the executed query is very slow
- D. When a large number of concurrent queries are run against the same warehouse

<details><summary>Show Answer</summary>
Correct Answer: D. Auto-scaling multi-cluster warehouses exist to absorb concurrency (many simultaneous queries/users), not to speed up any single slow query.
</details>

---

### Question 210
What happens when a cloned table is replicated to a secondary database? (Choose two.)

- A. A read-only copy of the cloned table is stored.
- B. The replication will not be successful.
- C. The physical data is replicated.
- D. Additional storage costs are charged to the secondary account.
- E. Metadata pointers to the cloned table are replicated.

<details><summary>Show Answer</summary>
Correct Answer: C, D. A clone is normally "zero-copy" (it just points to the source object's micro-partitions). But replication crosses account boundaries, so the secondary account can't share the primary account's storage — the clone's physical data must actually be copied, and that consumes (and is billed as) additional storage in the secondary account.
</details>

---

### Question 211
Snowflake supports the use of external stages with which cloud platforms? (Choose three.)

- A. Amazon Web Services
- B. Docker
- C. IBM Cloud
- D. Microsoft Azure
- E. Google Cloud Platform
- F. Oracle Cloud

<details><summary>Show Answer</summary>
Correct Answer: A, D, E. External stages can point to buckets/containers in AWS S3, Azure Blob Storage, or Google Cloud Storage.
</details>

---

### Question 212
What is a limitation of a materialized view?

- A. A materialized view cannot support any aggregate functions.
- B. A materialized view can only reference up to two tables.
- C. A materialized view cannot be joined with other tables.
- D. A materialized view cannot be defined with a JOIN.

<details><summary>Show Answer</summary>
Correct Answer: D. A materialized view's defining query cannot include a JOIN (among other restrictions, such as no window functions, `HAVING`, `ORDER BY`, or references to other views).
</details>

---

### Question 213
In the Snowflake access control model, which entity owns an object by default?

- A. The user who created the object
- B. The SYSADMIN role
- C. Ownership depends on the type of object
- D. The role that was used to create the object

<details><summary>Show Answer</summary>
Correct Answer: D. Snowflake follows Discretionary Access Control (DAC): the role active in the session when an object is created becomes its owner, not the individual user.
</details>

---

### Question 214
What is the minimum Snowflake edition required to use Dynamic Data Masking?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: B. Column-level security (masking policies / Dynamic Data Masking) requires Enterprise Edition or higher.
</details>

---

### Question 215
Which services does the Snowflake Cloud Services layer manage? (Choose two.)

- A. Compute resources
- B. Query execution
- C. Authentication
- D. Data storage
- E. Metadata

<details><summary>Show Answer</summary>
Correct Answer: C, E. The Cloud Services layer handles authentication, infrastructure management, metadata, query parsing/optimization, and access control — not the actual query execution (Compute layer) or physical data storage (Storage layer).
</details>

---

### Question 216
A company needs to allow some users to see Personally Identifiable Information (PII) while limiting other users from seeing its full value. Which Snowflake feature supports this?

- A. Row access policies
- B. Data masking policies
- C. Encryption
- D. Role-based access control

<details><summary>Show Answer</summary>
Correct Answer: B. Masking policies conditionally obscure column values (e.g., showing only the last 4 digits) based on the querying role, while leaving the underlying data intact for authorized roles.
</details>

---

### Question 217
A user unloaded data from a Snowflake table to an external stage. Which command can be used to verify the data was uploaded to the external stage named `my_stage`?

- A. `VIEW @my_stage`
- B. `LIST @my_stage`
- C. `SHOW @my_stage`
- D. `DISPLAY @my_stage`

<details><summary>Show Answer</summary>
Correct Answer: B. `LIST @my_stage` (or its alias `LS`) returns the files present in a stage.
</details>

---

### Question 218
Which tasks are performed by the Snowflake Cloud Services layer? (Choose two.)

- A. Management of metadata
- B. Computing/processing data
- C. Maintaining availability zones
- D. Infrastructure security
- E. Parsing and optimizing queries

<details><summary>Show Answer</summary>
Correct Answer: A, E. Metadata management and query parsing/optimization happen in Cloud Services. Actual data computation happens in the Compute layer; availability zones and infrastructure security are underlying cloud-provider concerns.
</details>

---

### Question 219
What is true about sharing data in Snowflake? (Choose two.)

- A. The provider pays for both data storage and the compute used to query shared data.
- B. Shared data is copied into the consumer account, so the consumer can modify it without impacting the provider's data.
- C. A Snowflake account can both provide and consume shared data.
- D. The provider is charged for compute resources used by the consumer to query the shared data.
- E. The consumer pays only for the compute resources used to query the shared data.

<details><summary>Show Answer</summary>
Correct Answer: C, E. Secure Data Sharing is read-only and live (no data copying) — the provider pays for storage, and each consumer pays only for the compute it uses to query the shared objects. Any Snowflake account can act as both a provider and a consumer.
</details>

---

### Question 220
The following JSON is stored in a VARIANT column called `src` in the `CAR_SALES` table:

```json
{
  "customer": [
    {
      "address": "San Francisco, CA",
      "name": "Jane Doe"
    }
  ],
  "date": "2022-01-28",
  "dealership": "Town Auto Sales"
}
```

How can a user extract the dealership information from the JSON?

- A. `select src:dealership from car_sales;`
- B. `select src.dealership from car_sales;`
- C. `select * from car_sales;`
- D. `select dealership from car_sales;`

<details><summary>Show Answer</summary>
Correct Answer: A. The colon (`:`) operator accesses a top-level element of a VARIANT column by key name.
</details>

---

### Question 221
Which of the following significantly improves the performance of selective point-lookup queries on a table?

- A. Clustering
- B. Materialized views
- C. Zero-copy cloning
- D. Search Optimization Service

<details><summary>Show Answer</summary>
Correct Answer: D. The Search Optimization Service builds a persisted search access path specifically to speed up highly selective point-lookup and substring-search queries.
</details>

---

### Question 222
Which of the following accurately describes shares?

- A. Tables, secure views, and secure UDFs can be shared.
- B. Shares themselves can be shared onward by the consumer.
- C. A new table can be cloned directly from a share.
- D. Access to a share cannot be revoked once granted.

<details><summary>Show Answer</summary>
Correct Answer: A. A provider can include tables, secure views, and secure UDFs in a share. Shares cannot be re-shared by consumers, cloning from a shared object isn't supported the way it is for objects you own, and providers can revoke access at any time.
</details>

---

### Question 223
What are best-practice recommendations for using the ACCOUNTADMIN system role? (Choose two.)

- A. Ensure all users with the ACCOUNTADMIN role use Multi-Factor Authentication (MFA).
- B. All users granted ACCOUNTADMIN must be owned by the ACCOUNTADMIN role.
- C. The ACCOUNTADMIN role must be granted to only one user.
- D. Assign the ACCOUNTADMIN role to at least two users, but as few as possible.
- E. All users granted ACCOUNTADMIN must also be granted SECURITYADMIN.

<details><summary>Show Answer</summary>
Correct Answer: A, D. Snowflake recommends enforcing MFA for ACCOUNTADMIN users and assigning the role to at least two people (for redundancy/business continuity) while keeping the group as small as possible.
</details>

---

### Question 224
In the Query Profile view for a query, which components represent areas that can help optimize query performance? (Choose two.)

- A. Bytes scanned
- B. Bytes sent over the network
- C. Number of partitions scanned
- D. Percentage scanned from cache
- E. External bytes scanned

<details><summary>Show Answer</summary>
Correct Answer: A, C. Bytes scanned and partitions scanned (especially relative to total partitions) are the key indicators of how much pruning is happening and where a query is spending its time.
</details>

---

### Question 225
What is the minimum Snowflake edition required for row-level security?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake

<details><summary>Show Answer</summary>
Correct Answer: B. Row access policies (row-level security) require Enterprise Edition or higher.
</details>

---

### Question 226
What is the minimum Fail-safe retention time period for transient tables?

- A. 1 day
- B. 7 days
- C. 12 hours
- D. 0 days

<details><summary>Show Answer</summary>
Correct Answer: D. Transient tables (and temporary tables) have no Fail-safe period at all — 0 days.
</details>

---

### Question 227
What is a machine learning and data science partner within the Snowflake Partner Ecosystem?

- A. Informatica
- B. Power BI
- C. Adobe
- D. DataRobot

<details><summary>Show Answer</summary>
Correct Answer: D. DataRobot is listed among Snowflake's machine learning / data science ecosystem partners; the others fall under data integration (Informatica) or BI (Power BI).
</details>

---

### Question 228
Which statements are correct concerning the use of third-party data from the Snowflake Marketplace? (Choose two.)

- A. Data is live, ready-to-query, and can be personalized.
- B. Data needs to be loaded into a cloud-provider account as a consumer.
- C. Data is available for copying/moving into an individual Snowflake account.
- D. Data is available without copying or moving it.
- E. Data transformations are always required when combining Marketplace datasets with existing data.

<details><summary>Show Answer</summary>
Correct Answer: A, D. Marketplace data listings provide live, ready-to-query access without any data movement or ETL required to make the data queryable.
</details>

---

### Question 229
What impacts the credit consumption of maintaining a materialized view? (Choose two.)

- A. Whether it is also a secure view
- B. How often the underlying base table is queried
- C. How often the base table changes
- D. Whether the materialized view has a clustering key defined
- E. How often the materialized view itself is queried

<details><summary>Show Answer</summary>
Correct Answer: C, D. Snowflake automatically refreshes a materialized view in the background whenever the base table changes — more frequent changes mean more background maintenance credits. If the materialized view also has a clustering key, ongoing automatic reclustering adds further maintenance cost. Querying the MV itself is billed as regular compute, not "maintenance."
</details>

---

### Question 230
What `COPY INTO <location>` setting should be used to unload data into multiple files?

- A. `SINGLE = TRUE`
- B. `MULTIPLE = TRUE`
- C. `MULTIPLE = FALSE`
- D. `SINGLE = FALSE`

<details><summary>Show Answer</summary>
⚠ Updated: The real `COPY INTO <location>` syntax only has a `SINGLE` parameter (there is no `MULTIPLE` parameter in Snowflake SQL). `SINGLE = FALSE` is the default and produces multiple output files. Correct Answer: D.
</details>

---

### Question 231
When cloning a database containing stored procedures and regular views that have fully qualified table references, what happens?

- A. The cloned views and stored procedures will reference the cloned tables in the new database.
- B. An error will occur, as views with qualified references cannot be cloned.
- C. An error will occur, as stored objects cannot be cloned.
- D. The stored procedures and views will continue to refer to tables in the original database.

<details><summary>Show Answer</summary>
Correct Answer: D. Views and stored procedures store fully qualified references at creation time; cloning the database does not rewrite those references, so they keep pointing back to the original (source) objects.
</details>

---

### Question 232
When loading data into Snowflake, how should the data be organized for best performance?

- A. Into files with roughly 100–250 MB of compressed data per file
- B. Into files with roughly 1–100 MB of compressed data per file
- C. Into files with a maximum size of 1 GB of compressed data per file
- D. Into files with a maximum size of 4 GB of data per file

<details><summary>Show Answer</summary>
Correct Answer: A. Snowflake recommends splitting data into compressed files of roughly 100–250 MB (or larger) to maximize parallelism during loading.
</details>

---

### Question 233
Which of the following objects can be directly restored using the `UNDROP` command? (Choose two.)

- A. Schema
- B. View
- C. Internal Stage
- D. Table
- E. User
- F. Role

<details><summary>Show Answer</summary>
⚠ Updated: Correct Answer (from the given options): A, D. `UNDROP` has always supported Table, Schema, and Database. Note that Snowflake has since expanded `UNDROP` support to many more object types (Dynamic Tables, Iceberg Tables, Notebooks, Streamlit apps, Tags, external volumes, and even accounts) — but among the six options listed here, only Schema and Table are (and were) valid. Views, internal stages, users, and roles are not restorable with `UNDROP`.
</details>

---

### Question 234
Which Snowflake SQL statement would be used to determine which users and roles have access to a role called `MY_ROLE`?

- A. `SHOW GRANTS OF ROLE MY_ROLE`
- B. `SHOW GRANTS TO ROLE MY_ROLE`
- C. `SHOW GRANTS FOR ROLE MY_ROLE`
- D. `SHOW GRANTS ON ROLE MY_ROLE`

<details><summary>Show Answer</summary>
Correct Answer: A. `SHOW GRANTS OF ROLE <name>` lists the users and roles to which the role has been granted. (`SHOW GRANTS TO ROLE <name>` instead lists the privileges the role itself holds.)
</details>

---

### Question 235
What is the minimum edition of Snowflake required to use a SCIM security integration?

- A. Business Critical Edition
- B. Standard Edition
- C. Virtual Private Snowflake (VPS)
- D. Enterprise Edition

<details><summary>Show Answer</summary>
Correct Answer: B. SCIM 2.0 provisioning is available across all Snowflake editions, including Standard.
</details>

---

### Question 236
A user created a transient table and made several changes to it over the course of several days. Three days after the table was created, the user wants to go back to the first version of the table. How can this be accomplished?

- A. Use Time Travel as long as `DATA_RETENTION_TIME_IN_DAYS` is set to at least 3 days.
- B. It cannot be done — transient tables have a maximum Time Travel retention of only 1 day and no Fail-safe period.
- C. Contact Snowflake Support to have the data retrieved from Fail-safe storage.
- D. Use the `FAILSAFE` parameter with Time Travel to retrieve the data from Fail-safe storage.

<details><summary>Show Answer</summary>
Correct Answer: B. Transient tables cap out at 1 day of Time Travel retention (it cannot be set to 3 days), and they have zero days of Fail-safe, so the original version is unrecoverable after that window closes.
</details>

---

### Question 237
When reviewing warehouse load, the load-monitoring chart shows a high volume of queries constantly queuing. According to best practice, what should be done to reduce the queue? (Choose two.)

- A. Use multi-cluster warehousing to scale out warehouse capacity.
- B. Scale up the warehouse size so queries execute faster.
- C. Stop and start the warehouse to clear the queued queries.
- D. Migrate some queries to a new warehouse to reduce load.
- E. Restrict users from accessing the warehouse so fewer queries run against it.

<details><summary>Show Answer</summary>
Correct Answer: A, D. Queuing is a concurrency problem, best solved by scaling out (multi-cluster) or spreading the workload across multiple warehouses — not by scaling up (which helps individual query speed, not queuing) or restarting the warehouse (which doesn't add capacity).
</details>

---

### Question 238
Which of the following features, associated with Continuous Data Protection (CDP), require additional Snowflake-provided data storage? (Choose two.)

- A. Tri-Secret Secure
- B. Time Travel
- C. Fail-safe
- D. Data encryption
- E. External stages

<details><summary>Show Answer</summary>
Correct Answer: B, C. Time Travel and Fail-safe both retain historical versions of data, which consumes additional storage that is billed to the account.
</details>

---

### Question 239
Where can a user find and review the failed logins of a specific user for the past 30 days?

- A. The `USERS` view in `ACCOUNT_USAGE`
- B. The `LOGIN_HISTORY` view in `ACCOUNT_USAGE`
- C. The `ACCESS_HISTORY` view in `ACCOUNT_USAGE`
- D. The `SESSIONS` view in `ACCOUNT_USAGE`

<details><summary>Show Answer</summary>
Correct Answer: B. `SNOWFLAKE.ACCOUNT_USAGE.LOGIN_HISTORY` records login attempts, including failures, and (unlike `INFORMATION_SCHEMA.LOGIN_HISTORY`) retains up to 365 days of history.
</details>

---

### Question 240
What is the purpose of an External Function?

- A. To call code that executes outside of Snowflake
- B. To run a function in another Snowflake database
- C. To share data in Snowflake with external parties
- D. To ingest data from on-premises data sources

<details><summary>Show Answer</summary>
Correct Answer: A. External functions let SQL code call out to a remote service (e.g., an AWS Lambda or Azure Function) hosted outside of Snowflake.
</details>

---

### Question 241
Which of the following statements apply to Snowflake in terms of security? (Choose two.)

- A. Snowflake leverages a Role-Based Access Control (RBAC) model.
- B. Snowflake requires a user to configure an IAM user to connect to the database.
- C. All data in Snowflake is encrypted.
- D. Snowflake can run entirely within a user's own Virtual Private Cloud (VPC).
- E. All data in Snowflake is compressed.

<details><summary>Show Answer</summary>
Correct Answer: A, C. Snowflake's access model combines RBAC and DAC, and all data is automatically encrypted at rest and in transit by default, regardless of edition.
</details>

---

### Question 242
A single user of a virtual warehouse has set it to auto-resume and auto-suspend after 10 minutes. The warehouse is currently suspended, and the user performs the following:
1. Runs a query that takes 3 minutes to complete.
2. Leaves for 15 minutes.
3. Returns and runs a query that takes 10 seconds to complete.
4. Manually suspends the warehouse as soon as the last query completes.

How much billable compute time will have been consumed?

- A. 4 minutes
- B. 13 minutes
- C. 14 minutes
- D. 24 minutes

<details><summary>Show Answer</summary>
Correct Answer: C. 3 minutes (query 1) + 10 minutes idle before auto-suspend kicks in (the 15-minute absence exceeds the 10-minute timeout) + 1 minute minimum billing for the second query (Snowflake bills with a 60-second minimum) = 14 minutes.
</details>

---

### Question 243
What can be used to view warehouse usage time? (Choose two.)

- A. The `LOAD_HISTORY` view
- B. The Query History view
- C. The `SHOW WAREHOUSES` command
- D. The `WAREHOUSE_METERING_HISTORY` view in `ACCOUNT_USAGE`
- E. The Billing & Usage tab in the Snowflake web UI

<details><summary>Show Answer</summary>
Correct Answer: D, E. `ACCOUNT_USAGE.WAREHOUSE_METERING_HISTORY` and the Billing & Usage area in Snowsight both report warehouse credit/usage time.
</details>

---

### Question 244
What actions will prevent leveraging of the result set (query results) cache? (Choose two.)

- A. Removing a column from the query's SELECT list
- B. Stopping the virtual warehouse the query is running against
- C. Clustering the data used by the query
- D. Executing the `RESULT_SCAN` table function
- E. The underlying data used by the query has changed

<details><summary>Show Answer</summary>
Correct Answer: A, E. Any change to the query text (like removing a column) or to the underlying table data invalidates the cached result. Stopping the warehouse doesn't affect the cache (it's independent of any warehouse), and `RESULT_SCAN` reads the cache rather than breaking it.
</details>

---

### Question 245
Which statement is true about running tasks in Snowflake?

- A. A task can be called using a `CALL` statement to run a set of predefined SQL commands.
- B. A task allows a user to execute a single SQL statement or stored procedure call on a predefined schedule.
- C. A task allows a user to execute a set of SQL commands on a predefined schedule.
- D. A task can be executed using a `SELECT` statement to run a predefined SQL command.

<details><summary>Show Answer</summary>
Correct Answer: B. Each individual task executes one SQL statement (which can itself be a call to a stored procedure containing multiple statements) on a schedule; chaining multiple tasks together forms a task graph (DAG) for more complex workflows.
</details>

---

### Question 246
Which data types does Snowflake support when querying semi-structured data? (Choose two.)

- A. VARIANT
- B. VARCHAR
- C. XML
- D. ARRAY
- E. BLOB

<details><summary>Show Answer</summary>
Correct Answer: A, D. VARIANT stores arbitrary semi-structured data, and ARRAY/OBJECT are the structured sub-types used to navigate it. VARCHAR and BLOB are not semi-structured types, and XML is a file format, not a Snowflake column data type.
</details>

---

### Question 247
In an auto-scaling multi-cluster virtual warehouse with `SCALING_POLICY = ECONOMY`, when is an additional cluster started?

- A. When the system has enough load for 2 minutes
- B. When the system has enough load for 6 minutes
- C. When the system has enough load for 8 minutes
- D. When the system has enough load for 10 minutes

<details><summary>Show Answer</summary>
Correct Answer: B. The ECONOMY scaling policy favors keeping existing clusters fully loaded and only starts a new cluster if the queued load is expected to keep it busy for at least 6 minutes (this conserves credits compared to the STANDARD policy).
</details>

---

### Question 248
What is the following SQL command used for?

```sql
SELECT * FROM TABLE(VALIDATE(t1, JOB_ID => '_last'));
```

- A. To validate external table files against table t1 across all sessions
- B. To validate task SQL statements against table t1 over the last 14 days
- C. To validate a file for errors before it gets loaded via a `COPY` command
- D. To return errors from the last executed `COPY` command into table t1, within the current session

<details><summary>Show Answer</summary>
Correct Answer: D. `VALIDATE(table_name, JOB_ID => '_last')` returns the load errors from the most recent `COPY INTO` load for that table, scoped to the current session.
</details>

---

### Question 249
A table `FCT_SALES` has 100 million rows. The following query is executed:

```sql
SELECT COUNT(*) FROM FCT_SALES;
```

How did Snowflake fulfill this query?

- A. Query against the result set cache
- B. Query against a virtual warehouse's local disk cache
- C. Query against the most-recently created micro-partition
- D. Query against table metadata (no data scan required)

<details><summary>Show Answer</summary>
Correct Answer: D. Snowflake stores row counts as metadata for each micro-partition, so a simple `COUNT(*)` (with no filters) can be answered entirely from metadata, without scanning any actual data or even requiring a running warehouse.
</details>

---

### Question 250
What happens when a virtual warehouse is resized?

- A. When increasing the size of an active warehouse, all running and queued queries are affected immediately.
- B. When reducing the size of a warehouse, compute resources are removed only once they are no longer being used by any currently executing statement.
- C. The warehouse is suspended while the new compute resources are provisioned, then automatically resumes once provisioning completes.
- D. Users trying to use the warehouse will receive an error message until resizing completes.

<details><summary>Show Answer</summary>
Correct Answer: B. Scaling up adds resources for new queries without disrupting queries already running; scaling down removes resources gracefully, only after in-flight statements finish using them.
</details>

---

### Question 251
What tasks can be completed using the `COPY INTO <table>` command? (Choose two.)

- A. Columns can be renamed.
- B. Columns can be joined with an existing table.
- C. Columns can be reordered.
- D. Columns can be omitted.
- E. Data can be loaded without spinning up a virtual warehouse.

Correct Answer: C, D. Using a column list and `SELECT` transformation in the `COPY INTO `<table>`` statement, you can reorder or omit source columns during the load. A running warehouse (or Snowpipe's serverless compute) is still required to execute the load.
<details><summary>Show Answer</summary>
</details>

---

### Question 252
Which Snowflake layer can be directly configured by users?

- A. Database Storage
- B. Cloud Services
- C. Compute (Query Processing)
- D. Application Services

<details><summary>Show Answer</summary>
Correct Answer: C. Users create, resize, and manage virtual warehouses in the Compute layer. Storage and Cloud Services scale automatically and are not directly configured by customers.
</details>

---

### Question 253
Query compilation occurs in which layer of Snowflake's architecture?

- A. Compute layer
- B. Storage layer
- C. Cloud infrastructure layer
- D. Cloud Services layer

<details><summary>Show Answer</summary>
Correct Answer: D. Query parsing, compilation, and optimization all happen in the Cloud Services layer, before any work is dispatched to a virtual warehouse for execution.
</details>

---

### Question 254
If an X-Small virtual warehouse is made up of one server and a Small warehouse is made up of two servers, how many servers make up a Large warehouse?

- A. 4
- B. 8
- C. 16
- D. 32

<details><summary>Show Answer</summary>
Correct Answer: B. Each warehouse size doubles the compute of the previous size: X-Small=1, Small=2, Medium=4, Large=8, X-Large=16, and so on.
</details>

---

### Question 255
A clustering key was defined on a table but is no longer needed. How can the key be removed?

- A. `ALTER TABLE [table_name] PURGE CLUSTERING KEY`
- B. `ALTER TABLE [table_name] DELETE CLUSTERING`
- C. `ALTER TABLE [table_name] DROP CLUSTERING KEY`
- D. `ALTER TABLE [table_name] REMOVE CLUSTERING KEY`

<details><summary>Show Answer</summary>
Correct Answer: C. `ALTER TABLE ... DROP CLUSTERING KEY` is the correct syntax to remove a defined clustering key (the table itself is unaffected).
</details>

---

### Question 256
What is the purpose of clustering?

- A. To guarantee uniquely identifiable records in the database
- B. To increase scan efficiency in queries by improving partition pruning
- C. To improve performance by creating a separate file for point lookups
- D. To provide data redundancy by duplicating micro-partitions

<details><summary>Show Answer</summary>
Correct Answer: B. Clustering co-locates similar column values within micro-partitions so that queries filtering on the clustering key can prune (skip) irrelevant partitions.
</details>

---

### Question 257
Which statement is true about Multi-Factor Authentication (MFA) in Snowflake?

- A. MFA can be enforced for a given role.
- B. Snowflake users are automatically enrolled in MFA.
- C. Users enroll in MFA by submitting a request to Snowflake Support.
- D. MFA is a natively integrated Snowflake feature.

<details><summary>Show Answer</summary>
Correct Answer: D. Snowflake has native MFA (powered by Duo Security) built directly into the platform. Enrollment is self-service through the user's profile, not automatic and not something Support has to configure.
</details>

---

### Question 258
What data type should be used to store JSON data natively in Snowflake?

- A. JSON
- B. STRING
- C. OBJECT
- D. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: D. VARIANT natively stores semi-structured data such as JSON, Avro, ORC, Parquet, or XML, preserving its structure for querying.
</details>

---

### Question 259
What should be considered when deciding to use a Secure View? (Choose two.)

- A. Details of the query execution plan are hidden from non-owners in the Query Profile.
- B. Once created, there is no way to determine whether a view is secure or not.
- C. Secure views do not take advantage of the same internal optimizations as standard views.
- D. It is not possible to create a secure materialized view.
- E. The view definition of a secure view is always visible to all users via the Information Schema.

<details><summary>Show Answer</summary>
Correct Answer: A, C. Secure views intentionally hide internal query details (like the underlying SQL text and parts of the execution plan) from unauthorized users to protect the view logic, and as a trade-off they skip some query-optimization techniques (like predicate pushdown) that could otherwise leak information about the underlying data.
</details>

---

### Question 260
The Information Schema provides storage information for which of the following objects? (Choose two.)

- A. Users
- B. Databases
- C. Internal Stages
- D. Resource Monitors
- E. Pipes

<details><summary>Show Answer</summary>
Correct Answer: B, C (as sourced from the original question bank). Note: detailed storage metrics for tables/stages are more comprehensively available via `SNOWFLAKE.ACCOUNT_USAGE`, so treat this specific pairing with some caution if you encounter it on an actual exam.
</details>

---

### Question 261
What is a responsibility of Snowflake's virtual warehouses?

- A. Infrastructure management
- B. Metadata management
- C. Query execution
- D. Query parsing and optimization
- E. Management of storage

<details><summary>Show Answer</summary>
Correct Answer: C. Virtual warehouses (the Compute layer) are responsible for executing queries and DML operations. Parsing/optimization and metadata management happen in Cloud Services; storage is managed independently.
</details>

---

### Question 262
Which data type is supported by Snowflake's native data classification feature?

- A. FLOAT
- B. STRING
- C. GEOGRAPHY
- D. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake's automated data classification analyzes STRING-type column data to detect and tag categories like PII (names, emails, etc.).
</details>

---

### Question 263
When unloading data to an external stage, which compression format can be used for Parquet files with the `COPY INTO` command?

- A. BROTLI
- B. GZIP
- C. LZO
- D. ZSTD

<details><summary>Show Answer</summary>
Correct Answer: C. For `TYPE = PARQUET`, the supported `COMPRESSION` values are `AUTO`, `LZO`, `SNAPPY` (the default), or `NONE`. BROTLI, GZIP, and ZSTD are valid for other file types (CSV, JSON, Avro) but not for Parquet.
</details>

---

### Question 264
Which SQL command can be used to verify the privileges that are granted to a role?

- A. `SHOW GRANTS ON ROLE [role_name]`
- B. `SHOW ROLES [role_name]`
- C. `SHOW GRANTS TO ROLE [role_name]`
- D. `GRANTS FOR ROLE [role_name]`

<details><summary>Show Answer</summary>
Correct Answer: C. `SHOW GRANTS TO ROLE <name>` lists the privileges that have been granted to a role.
</details>

---

### Question 265
Which Query Profile result indicates that a warehouse is sized too small for a query?

- A. There are a lot of filter nodes.
- B. Bytes are spilling to local or remote storage.
- C. The percentage of partitions scanned is very high.
- D. The number of partitions scanned equals the total number of partitions.

<details><summary>Show Answer</summary>
Correct Answer: B. When a warehouse doesn't have enough memory for an operation (e.g., a large sort or join), Snowflake spills intermediate results to local disk and then to remote storage — a clear sign the warehouse should be resized larger.
</details>

---

### Question 266
What is the default Time Travel retention period?

- A. 1 day
- B. 7 days
- C. 45 days
- D. 90 days

<details><summary>Show Answer</summary>
Correct Answer: A. The account default for `DATA_RETENTION_TIME_IN_DAYS` is 1 day; Enterprise Edition (and higher) can extend this up to 90 days for permanent objects if explicitly configured.
</details>

---

### Question 267
Which of the following are best-practice recommendations to consider when loading data into Snowflake? (Choose two.)

- A. Load files that are approximately 25 MB or smaller.
- B. Remove all dates and timestamps.
- C. Load files that are approximately 100–250 MB (or larger) compressed.
- D. Avoid using embedded characters, such as commas, for numeric data types.
- E. Remove all semi-structured data types.

<details><summary>Show Answer</summary>
Correct Answer: C, D. Aim for 100–250 MB compressed files for load parallelism, and avoid embedding delimiters like commas inside numeric fields (which breaks parsing).
</details>

---

### Question 268
Which schema contains the `RESOURCE_MONITORS` view?

- A. `SNOWFLAKE.ACCOUNT_USAGE`
- B. `SNOWFLAKE.READER_ACCOUNT_USAGE`
- C. `INFORMATION_SCHEMA`
- D. `SNOWFLAKE.ORGANIZATION_USAGE`

<details><summary>Show Answer</summary>
Correct Answer: A. Resource monitors are account-level objects, and their metadata is surfaced through `SNOWFLAKE.ACCOUNT_USAGE.RESOURCE_MONITORS` — not a per-database `INFORMATION_SCHEMA`.
</details>

---

### Question 269
What is the purpose of enabling Federated Authentication on a Snowflake account?

- A. Disables the ability to use key-pair and basic username/password authentication when connecting.
- B. Allows dual Multi-Factor Authentication (MFA) when connecting to Snowflake.
- C. Forces users to connect through a secure network proxy.
- D. Allows users to connect using secure single sign-on (SSO) through an external identity provider.

<details><summary>Show Answer</summary>
Correct Answer: D. Federated authentication delegates login to an external SAML 2.0 identity provider (e.g., Okta, Azure AD), enabling SSO.
</details>

---

### Question 270
Which Snowflake Partner Ecosystem category is represented at the top of the (referenced) partner diagram?

- A. Business Intelligence
- B. Machine Learning and Data Science
- C. Security and Governance
- D. Data Integration

<details><summary>Show Answer</summary>
Correct Answer: D (as sourced from the original question bank). Note: the diagram referenced in the original source wasn't legible/available in the OCR text, so this answer could not be independently re-verified against an image — treat it with a bit more caution than the rest of this set.
</details>

---

### Question 271
Which object types are protected by Fail-safe? (Choose two.)

- A. Permanent tables
- B. Temporary tables
- C. External tables
- D. Materialized views
- E. Transient tables

<details><summary>Show Answer</summary>
Correct Answer: A, D. Fail-safe applies only to permanent objects (permanent tables and their materialized views). Temporary and transient tables have no Fail-safe, and external tables don't store data within Snowflake at all.
</details>

---

### Question 272
Snowflake's approach to the management of system access combines which of the following? (Choose two.)

- A. Security Assertion Markup Language (SAML)
- B. Role-Based Access Control (RBAC)
- C. Identity Access Management (IAM)
- D. Create, Read, Update, and Delete (CRUD)
- E. Discretionary Access Control (DAC)
- F. Mandatory Access Control (MAC)

<details><summary>Show Answer</summary>
Correct Answer: B, E. Snowflake's access control model combines Role-Based Access Control (privileges assigned to roles, which are assigned to users) with Discretionary Access Control (each object has an owning role that can grant access to it).
</details>

---

### Question 273
According to Snowflake best-practice recommendations, which role should be used to create databases?

- A. ACCOUNTADMIN
- B. SYSADMIN
- C. SECURITYADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: B. SYSADMIN is the recommended role for creating and managing warehouses, databases, and other data objects, keeping ACCOUNTADMIN reserved for account-level administration.
</details>

---

### Question 274
To add or remove search optimization for a table, a user must have which of the following privileges? (Choose two.)

- A. The MODIFY privilege on the table
- B. The OWNERSHIP privilege on the table
- C. The SECURITYADMIN role
- D. The ADD SEARCH OPTIMIZATION privilege on the schema that contains the table
- E. The SELECT privilege on the table

<details><summary>Show Answer</summary>
Correct Answer: B, D. A role needs OWNERSHIP on the table itself, plus the ADD SEARCH OPTIMIZATION privilege (granted by default to the schema owner, or grantable to another role) on the containing schema.
</details>

---

### Question 275
While using a `COPY` command with a `VALIDATION_MODE` parameter, which of the following will return an error?

- A. Statements that insert a duplicate record during a load
- B. Statements that have a specific data type in the source
- C. Statements that have duplicate file names
- D. Statements that transform data during a load

<details><summary>Show Answer</summary>
Correct Answer: D. `VALIDATION_MODE` is not compatible with a `COPY INTO <table>` statement that also performs data transformations (i.e., uses a `SELECT` with column transformations) — this combination returns an error.
</details>

---

### Question 276
When is the result set (query results) cache no longer available? (Choose two.)

- A. When a different warehouse is used to execute the query
- B. When the user executes the `RESULT_SCAN` function
- C. When the underlying data used by the query has changed
- D. When the warehouse used to execute the query is suspended
- E. When it has been 24 hours since the query was last executed

<details><summary>Show Answer</summary>
Correct Answer: C, E. The results cache is invalidated once the underlying data changes, or after 24 hours have passed since the results were last used (each use resets that 24-hour clock, up to a maximum of 31 days from the original execution). It is independent of which warehouse runs the query or whether that warehouse is suspended.
</details>

---

### Question 277
What is the recommended file sizing for data loading using Snowpipe?

- A. A compressed file size greater than 100 MB, and up to 250 MB
- B. A compressed file size greater than 100 GB, and up to 250 GB
- C. A compressed file size greater than 10 MB, and up to 100 MB
- D. A compressed file size greater than 1 GB, and up to 2 GB

<details><summary>Show Answer</summary>
Correct Answer: A. As with bulk loading, Snowflake recommends compressed files of roughly 100–250 MB for Snowpipe to balance load latency and per-file overhead.
</details>

---

### Question 278
Which statements are true concerning Snowflake's underlying cloud infrastructure? (Choose three.)

- A. Snowflake data and services are deployed in a single availability zone within a cloud provider's region.
- B. Snowflake data and services are available only in a single cloud provider and region; use of multiple cloud providers is not supported.
- C. Snowflake can be deployed in a customer's private cloud, using the customer's own compute and storage resources.
- D. Snowflake uses the core compute and storage services of each cloud provider it runs on.
- E. All three layers (storage, compute, and cloud services) are deployed and managed entirely on the selected cloud platform.
- F. Snowflake data and services are deployed across at least three availability zones within a cloud provider's region.

<details><summary>Show Answer</summary>
Correct Answer: D, E, F. Snowflake runs entirely on top of the native compute/storage services of AWS, Azure, or GCP, spans at least three availability zones for resilience, and does not deploy into a customer's own private infrastructure.
</details>

---

### Question 279
A user unloaded a Snowflake table called `mytable` to an internal stage called `mystage`. Which command can be used to view the list of files uploaded to the stage?

- A. `LIST @mytable;`
- B. `LIST TABLE mystage;`
- C. `SHOW STAGE mystage;`
- D. `LIST @mystage;`

<details><summary>Show Answer</summary>
Correct Answer: D. `LIST @mystage;` lists the files present in the named internal stage `mystage`.
</details>

---

### Question 280
What is a best practice after creating a custom role?

- A. Create the custom role using the SYSADMIN role.
- B. Assign the custom role to the SYSADMIN role.
- C. Assign the custom role to the PUBLIC role.
- D. Add `_CUSTOM` to all custom role names.

<details><summary>Show Answer</summary>
Correct Answer: B. Best practice is to grant custom roles up to SYSADMIN in the role hierarchy so system administrators retain full visibility and control over all custom objects.
</details>

---

### Question 281
Which is the minimum required Snowflake edition to use AWS/Azure PrivateLink or Google Cloud Private Service Connect?

- A. Standard
- B. Premium
- C. Enterprise
- D. Business Critical

<details><summary>Show Answer</summary>
Correct Answer: D. Private connectivity (AWS PrivateLink, Azure Private Link, Google Cloud Private Service Connect) requires Business Critical Edition or higher.
</details>

---

### Question 282
Which of the following Query Profile indicators shows that a virtual warehouse is not sized correctly for the query being executed?

- A. Bytes sent over the network
- B. Synchronization time
- C. Initialization time
- D. Remote spillage (bytes spilled to remote storage)

<details><summary>Show Answer</summary>
Correct Answer: D. Spilling to remote storage means the warehouse ran out of local memory/disk for the operation — a strong signal the warehouse should be resized up.
</details>

---

### Question 283
Which of the following Snowflake capabilities are available in all Snowflake editions? (Choose two.)

- A. Encryption key management through Tri-Secret Secure
- B. Automatic encryption of all data
- C. Up to 90 days of data recovery through Time Travel
- D. Object-level access control
- E. Column-level security to apply masking policies to tables and views

<details><summary>Show Answer</summary>
Correct Answer: B, D. Always-on encryption of data at rest/in transit and RBAC-based object-level access control are baseline features of every edition, including Standard. Tri-Secret Secure requires Business Critical, extended Time Travel (beyond 1 day) requires Enterprise+, and masking policies require Enterprise+.
</details>

---

### Question 284
A `PUT` command can be used to stage local files from which Snowflake interface?

- A. SnowSQL (CLI)
- B. Snowflake Classic Console (UI)
- C. Snowsight
- D. .NET driver

<details><summary>Show Answer</summary>
Correct Answer: A. `PUT` requires access to the local file system, so it is executed from a CLI or driver context like SnowSQL — not from the browser-based Snowsight or Classic Console UI, which cannot access your local disk directly.
</details>

---

### Question 285
Which of the following indicate that it may be appropriate to define a clustering key for a table? (Choose two.)

- A. The table contains a column that has very low cardinality.
- B. DML statements being issued against the table are blocked.
- C. The table has a small number of micro-partitions.
- D. Queries on the table are running slower than expected.
- E. The clustering depth for the table is large.

<details><summary>Show Answer</summary>
Correct Answer: D, E. Slower-than-expected query performance combined with a large clustering depth (poor data organization relative to the clustering/filter columns) are the classic signals that clustering would help. Very low cardinality, few partitions, or DML blocking are not indicators for clustering.
</details>

---

### Question 286
Which cache type is used to cache the data output from SQL queries?

- A. Metadata cache
- B. Result (query results) cache
- C. Remote cache
- D. Local disk (warehouse) cache

<details><summary>Show Answer</summary>
Correct Answer: B. The result cache stores the actual output of a previously run query for near-instant retrieval on an identical repeat query, for up to 24 hours (extendable to 31 days with reuse).
</details>

---

### Question 287
Which of the following describes how clustering keys work in Snowflake?

- A. Clustering keys update micro-partitions in place with a full sort, and block DML operations.
- B. Clustering keys sort the designated columns over time, without blocking DML operations.
- C. Clustering keys create a distributed, parallel data structure of pointers to rows and columns.
- D. Clustering keys establish a hashed key on each node of a virtual warehouse to optimize joins at run-time.

<details><summary>Show Answer</summary>
Correct Answer: B. Automatic reclustering incrementally re-sorts micro-partitions in the background over time, and never blocks concurrent DML on the table.
</details>

---

### Question 288
Which of the following operations require the use of a running virtual warehouse? (Choose two.)

- A. Downloading data from an internal stage
- B. Listing files in a stage
- C. Executing a stored procedure
- D. Altering a table's metadata (DDL)
- E. Querying data from a materialized view

<details><summary>Show Answer</summary>
Correct Answer: C, E. Executing SQL inside a stored procedure and querying a materialized view both require compute. Listing/downloading stage files and most metadata-only DDL operations are handled by Cloud Services and don't need an active warehouse.
</details>

---

### Question 289
What is used to limit the credit usage of a virtual warehouse within a Snowflake account?

- A. Load monitor
- B. Resource monitor
- C. Query profile
- D. Warehouse policy

<details><summary>Show Answer</summary>
Correct Answer: B. Resource monitors track credit usage against defined thresholds and can trigger notifications or automatically suspend warehouses when limits are reached.
</details>

---

### Question 290
What are the benefits of the replication feature in Snowflake? (Choose two.)

- A. Disaster recovery
- B. Time Travel
- C. Fail-safe
- D. Database failover and failback
- E. Data security

<details><summary>Show Answer</summary>
Correct Answer: A, D. Cross-region/cross-cloud replication supports disaster recovery scenarios and enables account failover/failback to a secondary account (Business Critical Edition or higher for failover/failback specifically).
</details>

---

### Question 291
Which of the following roles are recommended to create and manage other users and roles? (Choose two.)

- A. SYSADMIN
- B. SECURITYADMIN
- C. PUBLIC
- D. ACCOUNTADMIN
- E. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: B, E. SECURITYADMIN manages grants globally and can create/manage users and roles; USERADMIN is specifically dedicated to creating and managing users and roles.
</details>

---

### Question 292
When can a newly configured virtual warehouse start running SQL queries?

- A. Immediately, while provisioning is still in progress
- B. Only during specific time slots defined by the ACCOUNTADMIN
- C. After warehouse provisioning has completed
- D. After warehouse replication has completed

<details><summary>Show Answer</summary>
Correct Answer: C. A virtual warehouse can accept and run queries as soon as its compute resources finish provisioning.
</details>

---

### Question 293
What action will prevent leveraging of the result set cache?

- A. Removing a column from the query's SELECT list
- B. Stopping the virtual warehouse that the query is running against
- C. The result not being reused within the last 12 hours
- D. Executing the `RESULT_SCAN` table function

<details><summary>Show Answer</summary>
Correct Answer: A. Changing the query text — including removing a column from the SELECT list — produces a different query signature, so it can't reuse a previous result. (Note: the real cache expiry window is 24 hours, not 12, so option C is a deliberately incorrect distractor; stopping the warehouse and using `RESULT_SCAN` don't invalidate the cache.)
</details>

---

### Question 294
Which of the following are benefits of micro-partitioning? (Choose two.)

- A. Micro-partitions cannot overlap in their range of values.
- B. Micro-partitions are immutable objects that support the use of Time Travel.
- C. Micro-partitions can reduce the amount of I/O from object storage to virtual warehouses.
- D. Rows are automatically stored in sorted order within every micro-partition.
- E. Micro-partitions can be defined on a schema-by-schema basis.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Because micro-partitions are immutable, Snowflake can efficiently retain historical versions for Time Travel, and because each partition stores rich metadata, queries can prune irrelevant partitions and reduce I/O. (Partitions can overlap in value ranges, and micro-partitioning is automatic — not something configured per schema.)
</details>

---

### Question 295
Which data type can be used to store geospatial data in Snowflake?

- A. VARIANT
- B. OBJECT
- C. GEOMETRY
- D. GEOGRAPHY

<details><summary>Show Answer</summary>
⚠ Updated: Correct Answer: D (GEOGRAPHY) was the traditional/primary answer, and remains valid — GEOGRAPHY stores spherical (latitude/longitude, WGS 84) geospatial data. However, Snowflake has since also added a GEOMETRY data type for planar/Cartesian geospatial data, so C is now also a technically correct answer to "which data type can be used." If this is a single-select exam question, GEOGRAPHY (D) remains the expected answer.
</details>

---

### Question 296
If all virtual warehouse resources are maximized while processing a query workload, what happens to new queries submitted to the warehouse?

- A. All queries terminate once resources are maximized.
- B. The warehouse scales out automatically.
- C. The warehouse moves to a suspended state.
- D. New queries are queued and executed once capacity is available.

<details><summary>Show Answer</summary>
Correct Answer: D. New queries wait in a queue until sufficient compute capacity frees up (unless the warehouse is a multi-cluster warehouse configured to auto-scale, in which case additional clusters would start instead).
</details>

---

### Question 297
Masking policies can be applied to which of the following Snowflake objects? (Choose two.)

- A. A materialized view
- B. A stored procedure
- C. A table
- D. A stream
- E. A pipe
- F. A function

<details><summary>Show Answer</summary>
Correct Answer: A, C. Masking policies attach to columns on tables, views, and materialized views. They cannot be attached to procedural objects like stored procedures, streams, pipes, or functions.
</details>

---

### Question 298
What actions are supported by Snowflake resource monitors? (Choose two.)

- A. Alert (notify only)
- B. Notify
- C. Notify and suspend
- D. Abort
- E. Suspend immediately

<details><summary>Show Answer</summary>
Correct Answer: B, C. Snowflake resource monitors support three real trigger actions: **Notify**, **Notify & Suspend** (let running queries finish, block new ones), and **Notify & Suspend Immediately** (cancel all running queries too). "Abort" is not an actual resource monitor action.
</details>

---

### Question 299
A user executes the following SQL:

```sql
CREATE TABLE SALES_BKP LIKE SALES;
```

What are the cost implications of this statement?

- A. Processing costs will be generated based on how long the query takes.
- B. Storage costs will be generated based on the size of the data.
- C. No storage cost is incurred, since it relies on metadata only.
- D. The cost of running the virtual warehouse will be charged by the second.

<details><summary>Show Answer</summary>
Correct Answer: C. `CREATE TABLE ... LIKE` copies only the source table's structure (columns, not data), so no data is duplicated and effectively no additional storage cost is incurred.
</details>

---

### Question 300
What is the maximum Time Travel retention available in Snowflake Standard Edition?

- A. 1 day
- B. 7 days
- C. 30 days
- D. 90 days

<details><summary>Show Answer</summary>
Correct Answer: A. Standard Edition supports a maximum Time Travel retention of 1 day. Extending retention up to 90 days requires Enterprise Edition or higher.
</details>

---



====================================================================================================
# snowpro_301-408.md
====================================================================================================

# SnowPro Core (COF-C03) Practice Questions — Batch 301–408

Reconstructed and cleaned from raw OCR. Answers cross-checked against current Snowflake documentation (as of July 2026). Corrections are flagged with **⚠ Updated**. Click "Show Answer" to reveal.

---

### Question 301
What happens when an external or an internal stage is dropped? (Choose two)

- A. When dropping an external stage, the files are not deleted — only the stage object is dropped.
- B. When dropping an external stage, both the stage and the files within it are removed.
- C. When dropping an internal stage, the files are deleted with the stage and are recoverable.
- D. When dropping an internal stage, the files are deleted with the stage and are **not** recoverable.
- E. When dropping an internal stage, only selected files are deleted with the stage and are not recoverable.

<details><summary>Show Answer</summary>
Correct Answer: A, D. External stages only reference external cloud storage — Snowflake never owns or deletes the underlying files. Internal stages physically hold the files in Snowflake-managed storage, so dropping the stage permanently deletes them (no Time Travel/Fail-safe recovery for stage files).
</details>

---

### Question 302
A user has 10 files in a stage containing new customer data. The ingest completes with no errors using `COPY INTO my_table FROM @stage`. The next day the user adds 10 more files so the stage now contains a mix of new customer data and updates to the previous data. The original 10 files were not removed. If the user re-runs the same `COPY INTO` command, what happens?

- A. All data from all files on the stage will be appended to the table.
- B. Only data about new customers from the new files will be appended to the table.
- C. The operation will fail with a `LOAD_UNCERTAIN_FILES` error.
- D. All data from only the newly-added files will be appended to the table.

<details><summary>Show Answer</summary>
Correct Answer: D. By default `COPY INTO` tracks per-file load metadata on the target table and skips files it has already loaded successfully, so only the new files get loaded (no duplication). Use `FORCE = TRUE` to reload everything.
</details>

---

### Question 303
Which parameter can be used to instruct a `COPY` command to verify (validate) data instead of loading it into the target table?

- A. `RETURN_FAILED_ONLY`
- B. `ON_ERROR`
- C. `FORCE`
- D. `VALIDATION_MODE`

<details><summary>Show Answer</summary>
Correct Answer: D. `VALIDATION_MODE` runs the COPY as a dry-run and returns validation results (or errors) without loading data.
</details>

---

### Question 304
Which of the following SQL statements will list the version of the driver/client currently being used?

- A. Execute `SELECT CURRENT_DATABASE()` from the web UI.
- B. Execute `SELECT CURRENT_VERSION()` from SnowSQL.
- C. Execute `SELECT CURRENT_CLIENT()` from an application.
- D. Execute `SELECT CURRENT_SESSION()` from the Python connector.

<details><summary>Show Answer</summary>
Correct Answer: C. `CURRENT_CLIENT()` returns the name and version of the client/driver used to connect to Snowflake (e.g., the JDBC/ODBC/Python connector version). `CURRENT_VERSION()` instead returns the Snowflake service version, not the driver version.
</details>

---

### Question 305
Which Snowflake technique can be used to improve the performance of a query?

- A. Clustering
- B. Indexing
- C. Fragmenting
- D. Using `INDEX_HINTS`

<details><summary>Show Answer</summary>
Correct Answer: A. Snowflake has no traditional indexes — clustering (natural or via an explicit clustering key) is the mechanism that improves micro-partition pruning and query performance.
</details>

---

### Question 306
What happens to the shared objects for users in a consumer account, once a database has been created from a share in that account?

- A. The shared objects are transferred.
- B. The shared objects are copied.
- C. The shared objects become accessible.
- D. The shared objects can be re-shared.

<details><summary>Show Answer</summary>
Correct Answer: C. Creating a database from a share simply exposes read-only access to the provider's objects — nothing is copied or transferred, and by default the consumer cannot re-share.
</details>

---

### Question 307
Using variables in a SnowSQL script is denoted by using which character?

- A. `$`
- B. `@`
- C. `&`
- D. `#`

<details><summary>Show Answer</summary>
Correct Answer: C. SnowSQL variable substitution uses `&variable_name` (with `variable_substitution` enabled). Note this is distinct from session variables referenced in SQL with `$var` via `SET`.
</details>

---

### Question 308
Which commands grant the privilege allowing a role to `SELECT` data from all current tables and any tables that will be created later in a schema? (Choose two)

- A. `GRANT USAGE ON ALL TABLES IN SCHEMA <schema> TO ROLE MYROLE;`
- B. `GRANT USAGE ON FUTURE TABLES IN SCHEMA <schema> TO ROLE MYROLE;`
- C. `GRANT SELECT ON ALL TABLES IN SCHEMA DB.SCHEMA TO ROLE MYROLE;`
- D. `GRANT SELECT ON FUTURE TABLES IN SCHEMA <schema> TO ROLE MYROLE;`
- E. `GRANT SELECT ON ALL TABLES IN DATABASE DB TO ROLE MYROLE;`
- F. `GRANT SELECT ON FUTURE TABLES IN DATABASE DB TO ROLE MYROLE;`

<details><summary>Show Answer</summary>
Correct Answer: C, D. `ON ALL TABLES` grants SELECT on tables that exist right now; `ON FUTURE TABLES` grants it automatically to tables created later in that schema. Both are needed to cover "current and future."
</details>

---

### Question 309
How would a user change which columns are exposed by a view?

- A. Modify the columns in the underlying table.
- B. Use `ALTER VIEW` to change the view's columns.
- C. Recreate the view with the required changes.
- D. Materialize the view to perform the changes.

<details><summary>Show Answer</summary>
Correct Answer: C. `ALTER VIEW` can rename a view, set/unset properties, or manage secure/comment settings — it cannot redefine the view's `SELECT` list or column set. You must `CREATE OR REPLACE VIEW`.
</details>

---

### Question 310
Which statement describes pruning?

- A. The filtering out (disregarding) of micro-partitions that are not needed to satisfy a query.
- B. The return of micro-partition values that overlap with each other to reduce a query's runtime.
- C. A service handled by the Cloud Services layer to optimize caching.
- D. The ability to allow the result of a query to be accessed as if it were a table.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 311
Which SQL command can be used to see the `CREATE` definition of a masking policy?

- A. `SHOW MASKING POLICIES`
- B. `DESCRIBE MASKING POLICY`
- C. `GET_DDL`
- D. `LIST MASKING POLICIES`

<details><summary>Show Answer</summary>
Correct Answer: C. `SELECT GET_DDL('MASKING POLICY', '<name>')` returns the full CREATE statement.
</details>

---

### Question 312
What is the `ACCOUNT_USAGE.METERING_HISTORY` view used for?

- A. Gathering the hourly credit usage for an account.
- B. Compiling an account's average cloud services cost over the previous month.
- C. Summarizing the throughput of Snowpipe costs for an account.
- D. Calculating the funds left on an account's contract.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 313
Query parsing and compilation occurs in which architecture layer of the Snowflake platform?

- A. Cloud services layer
- B. Compute layer
- C. Storage layer
- D. Cloud-agnostic layer (not a real layer)

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 314
Which of the following Snowflake objects can be shared using a secure share? (Choose two)

- A. Materialized views
- B. Sequences
- C. Procedures
- D. Tables
- E. Secure User-Defined Functions (UDFs)

<details><summary>Show Answer</summary>
Correct Answer: D, E. Tables, secure views, and secure UDFs can be shared. Sequences, stored procedures, and (non-secure) materialized views cannot.
</details>

---

### Question 315
What happens to underlying table data when a `CLUSTER BY` clause is added to a Snowflake table?

- A. Data is hashed by the cluster key to facilitate fast searches for common data values.
- B. Micro-partitions are created for common data values to reduce the number of partitions scanned.
- C. Smaller micro-partitions are created for common data values to allow for more parallelism.
- D. Data may be co-located by the cluster key within the micro-partitions to improve pruning performance.

<details><summary>Show Answer</summary>
Correct Answer: D. Clustering doesn't hash or resize micro-partitions — it reorganizes (reclusters) existing data so rows with similar cluster-key values land in the same micro-partitions, improving pruning.
</details>

---

### Question 316
Which conditions must be met to return results from the result cache? (Choose two)

- A. The user has the appropriate privileges on the objects associated with the query.
- B. Micro-partitions have been reclustered since the query was last run.
- C. The new query is run using the same virtual warehouse as the previous query.
- D. The query includes a User-Defined Function.
- E. The query has been run within 24 hours of the previously-run query (and underlying data hasn't changed).

<details><summary>Show Answer</summary>
Correct Answer: A, E. The result cache is warehouse-independent — a different warehouse can still serve a cached result, so C is not required. UDF-containing and reclustered-since-last-run queries generally bypass the cache.
</details>

---

### Question 317
Which statement about billing applies to credits?

- A. Credits are billed per-minute with a 60-minute minimum.
- B. Credits are used to pay for cloud data storage usage.
- C. Credits are consumed based on the number of credits billed for each hour a warehouse runs.
- D. Credits are consumed based on the warehouse size and the time the warehouse is running.

<details><summary>Show Answer</summary>
Correct Answer: D. Storage is billed separately (flat per-TB rate), and compute billing is per-second (60-second minimum), not per-minute — so both B and A are wrong.
</details>

---

### Question 318
A user needs to create a materialized view in schema `MYDB.MYSCHEMA`. Which statements will provide this access?

- A. `GRANT ROLE MYROLE TO USER USER1; GRANT CREATE MATERIALIZED VIEW ON SCHEMA MYDB.MYSCHEMA TO ROLE MYROLE;`
- B–D. Variants that omit the role grant to the user, grant to the wrong securable, or reverse the grant direction.

<details><summary>Show Answer</summary>
Correct Answer: A. The user needs the role assigned to them (`GRANT ROLE ... TO USER ...`) **and** that role needs the `CREATE MATERIALIZED VIEW` privilege on the schema (`GRANT CREATE MATERIALIZED VIEW ON SCHEMA ... TO ROLE ...`). Materialized views also require Enterprise Edition or higher.
</details>

---

### Question 319
What is the purpose of multi-cluster virtual warehouses?

- A. To create separate data warehouses to increase query optimization.
- B. To allow users to choose the type of compute nodes that make up a virtual warehouse cluster.
- C. To eliminate or reduce queuing of concurrent queries.
- D. To allow the warehouse to resize automatically.

<details><summary>Show Answer</summary>
Correct Answer: C. Multi-cluster warehouses scale out (add clusters) for concurrency, unlike warehouse resizing which scales up/down for single-query performance.
</details>

---

### Question 320
Which of the following is a valid source for an external stage when the Snowflake account is hosted on Microsoft Azure?

- A. An FTP server with TLS encryption
- B. An HTTPS server with WebDAV
- C. A Microsoft Azure Blob Storage container
- D. A Windows server file share on Azure

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 321
Which database objects can be shared with the Snowflake secure data sharing feature? (Choose two)

- A. Files
- B. External tables
- C. Functions (secure UDFs)
- D. Sequences
- E. Streams

<details><summary>Show Answer</summary>
Correct Answer: B, C.
</details>

---

### Question 322
Which statements reflect key functionalities of a Snowflake Data Exchange? (Choose two)

- A. If an account is enrolled with a Data Exchange, it loses access to the Snowflake Marketplace.
- B. A Data Exchange allows a group of accounts to share data privately among themselves.
- C. A Data Exchange allows accounts to share data with third-party, non-Snowflake parties.
- D. Data Exchange functionality is available by default in accounts using Enterprise Edition or higher.
- E. Sharing in a Data Exchange is bidirectional — an account can be a provider for some datasets and a consumer for others.

<details><summary>Show Answer</summary>
Correct Answer: B, E.
</details>

---

### Question 323
A Snowflake user executed a query and received the results. Another user executed the same query shortly later; the underlying data had not changed. What will occur?

- A. No virtual warehouse will be used — data will be read from the result cache.
- B. No virtual warehouse will be used — data will be read from the local disk cache.
- C. The default virtual warehouse will be used to read all data.
- D. The virtual warehouse defined at the session level will be used to read all data.

<details><summary>Show Answer</summary>
Correct Answer: A. The result cache lives in the Cloud Services layer and is warehouse-independent (unlike the local disk/data cache, which is tied to a specific running warehouse).
</details>

---

### Question 324
Which feature gives a user control over how data is organized within a micro-partition?

- A. Range Partitioning
- B. Search Optimization Service
- C. Automatic Clustering
- D. Horizontal Partitioning

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 325
Which privilege must be granted to a share to allow secure views the ability to reference data in multiple databases?

- A. `CREATE SHARE` on the database
- B. `SHARE` on the databases and schemas
- C. `SELECT` on the tables used by the secure view
- D. `REFERENCE_USAGE` on the databases

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 326
In which use case does Snowflake apply egress charges?

- A. Data sharing within a specific region
- B. Query result retrieval
- C. Database replication across regions/cloud platforms
- D. Loading data into Snowflake

<details><summary>Show Answer</summary>
Correct Answer: C. Egress fees apply when data crosses a region or cloud-platform boundary — e.g., cross-region/cross-cloud replication or unloading data out to a different cloud region. Sharing within the same region does not incur egress charges.
</details>

---

### Question 327
Which of the following compute resources/features are managed **by Snowflake** (i.e., serverless — you don't provision a warehouse for them)? (Choose two)

- A. Executing a `COPY` command
- B. Updating data (DML)
- C. Snowpipe
- D. `AUTOMATIC_CLUSTERING` (automatic reclustering)
- E. Scaling up a warehouse

<details><summary>Show Answer</summary>
Correct Answer: C, D. Both Snowpipe and automatic reclustering run on Snowflake-managed serverless compute rather than a user-managed virtual warehouse.
</details>

---

### Question 328
A materialized view should be created when which of the following occur? (Choose two)

- A. There is minimal cost associated with running the query.
- B. The query consumes many compute resources every time it runs.
- C. The base table gets updated frequently.
- D. The query is highly optimized and does not consume many compute resources.
- E. The results of the query do not change often and are used frequently.

<details><summary>Show Answer</summary>
Correct Answer: B, E. Frequent base-table updates (C) actually argue *against* a materialized view, since Snowflake has to keep re-maintaining it — a classic exam trap.
</details>

---

### Question 329
What privilege should be granted to allow a role to change permissions for objects in a managed access schema?

- A. Grant the `OWNERSHIP` privilege on the schema.
- B. Grant the `OWNERSHIP` privilege on the database.
- C. Grant the `MANAGE GRANTS` global privilege.
- D. Grant `ALL` privileges on the schema.

<details><summary>Show Answer</summary>
Correct Answer: C. In a managed access schema, only the schema owner or a role with the account-level `MANAGE GRANTS` privilege can grant/revoke privileges on objects in that schema — object owners lose that ability.
</details>

---

### Question 330
What happens when a data provider revokes privileges to a share on an object in their source database?

- A. The object immediately becomes unavailable to all data consumers.
- B. Any additional data arriving after this point in time will not be visible to consumers.
- C. Data consumers stop seeing data updates and become responsible for storage charges for the object.
- D. A static copy of the object at the time the privilege was revoked is created in the consumer's account.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 331
Which command is used to load (upload) local data files into an internal stage?

- A. `LOAD`
- B. `COPY`
- C. `GET`
- D. `PUT`

<details><summary>Show Answer</summary>
Correct Answer: D. `PUT` uploads files from local disk to a stage; `GET` downloads them back down; `COPY INTO <table>` then loads staged files into a table.
</details>

---

### Question 332
What is the MINIMUM Snowflake edition required to use periodic rekeying of micro-partitions?

- A. Enterprise
- B. Business Critical
- C. Standard
- D. Virtual Private Snowflake

<details><summary>Show Answer</summary>
Correct Answer: A. Verified against current documentation — periodic rekeying (`PERIODIC_DATA_REKEYING`) requires Enterprise Edition or higher. (Don't confuse this with Tri-Secret Secure / customer-managed keys, which require Business Critical Edition or higher.)
</details>

---

### Question 333
Which stage type can be altered and dropped?

- A. Database stage (not a real stage type)
- B. External (named) stage
- C. Table stage
- D. User stage

<details><summary>Show Answer</summary>
Correct Answer: B. Only named stages (internal or external) can be created, altered, and dropped with SQL. User stages and table stages are implicit, always exist, and cannot be altered/dropped.
</details>

---

### Question 334
Which Snowflake object enables loading data from files as soon as they are available in a cloud storage location?

- A. Pipe
- B. External stage
- C. Task
- D. Stream

<details><summary>Show Answer</summary>
Correct Answer: A. A pipe is the object that wraps a COPY statement for Snowpipe continuous/event-driven loading.
</details>

---

### Question 335
A user is loading JSON documents composed of a huge array containing multiple records into Snowflake and enables the `STRIP_OUTER_ARRAY` file format option. What does this option do?

- A. It removes the last element of the outer array.
- B. It removes the outer array structure and loads the records into separate table rows.
- C. It strips trailing spaces in the last element of the array and loads records into separate table columns.
- D. It removes NULL elements from the JSON object, enabling the load.

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 336
Which of the following describes how multiple Snowflake accounts in a single organization relate to various cloud providers?

- A. Each Snowflake account can be hosted in a different cloud vendor and region.
- B. Each Snowflake account must be hosted in a different cloud vendor and region.
- C. All accounts must be hosted in the same cloud vendor and region.
- D. Each Snowflake account can be hosted in a different cloud vendor, but must be in the same region.

<details><summary>Show Answer</summary>
Correct Answer: A. An organization can contain accounts spread freely across AWS, Azure, and GCP and across different regions.
</details>

---

### Question 337
If a Snowflake user decides a table should be clustered, what should be used as the cluster key?

- A. The columns queried in the `SELECT` clause.
- B. The columns with very high cardinality.
- C. The columns with many distinct values.
- D. The columns most actively used in `SELECT` filters (`WHERE` clauses).

<details><summary>Show Answer</summary>
Correct Answer: D. Good clustering keys have moderate cardinality and appear frequently in filter predicates — very high-cardinality columns (B, C) actually make poor clustering keys.
</details>

---

### Question 338
What value types can a `VARIANT` column store? (Choose two)

- A. `STRUCT`
- B. `OBJECT`
- C. `BINARY`
- D. `ARRAY`

<details><summary>Show Answer</summary>
Correct Answer: B, D. `VARIANT` can hold semi-structured `OBJECT` and `ARRAY` values (plus scalars) — `STRUCT` isn't a Snowflake data type, and `BINARY` is its own separate type.
</details>

---

### Question 339
A company needs to load multiple terabytes of data for an initial load as part of a Snowflake migration, and it can control the number and size of its CSV extract files. How should Snowflake recommend maximizing load throughput?

- A. Use auto-ingest Snowpipe to load large files in a serverless model.
- B. Produce the largest files possible, reducing the number of files to load.
- C. Produce a larger number of similarly-sized smaller files and process the ingestion with an appropriately-sized (or multi-cluster) virtual warehouse.
- D. Use an ETL tool to issue row-by-row inserts within `BEGIN TRANSACTION`/`COMMIT` blocks.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowflake loads files in parallel across the nodes of a warehouse, so splitting data into many similarly-sized files (Snowflake recommends roughly 100–250 MB compressed) — rather than one giant file — maximizes parallelism and load speed.
</details>

---

### Question 340
For non-materialized views, what column in `INFORMATION_SCHEMA`/`ACCOUNT_USAGE` identifies whether a view is secure or not?

- A. `CHECK_OPTION`
- B. `IS_SECURE`
- C. `IS_UPDATABLE`
- D. `TABLE_NAME`

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 341
The bulk data load history available upon completion of a `COPY` statement is stored where, and for how long?

- A. In the metadata of the target table, for 14 days
- B. In the metadata of the pipe, for 14 days
- C. In the metadata of the target table, for 64 days
- D. In the metadata of the pipe, for 64 days

<details><summary>Show Answer</summary>
Correct Answer: C. Verified against current documentation. Bulk `COPY INTO <table>` load metadata lives on the target table for 64 days; Snowpipe load history instead lives on the pipe object for 14 days (see Question 386).
</details>

---

### Question 342
User `INQUISITIVE_PERSON` has been granted the role `DATA_SCIENCE`. The role `DATA_SCIENCE` has `OWNERSHIP` on schema `MARKETING` of database `ANALYTICS_DW`. Which command will show all privileges granted **on** that schema?

- A. `SHOW GRANTS ON ROLE DATA_SCIENCE`
- B. `SHOW GRANTS ON SCHEMA ANALYTICS_DW.MARKETING`
- C. `SHOW GRANTS TO USER INQUISITIVE_PERSON`
- D. `SHOW GRANTS OF ROLE DATA_SCIENCE`

<details><summary>Show Answer</summary>
Correct Answer: B. `SHOW GRANTS ON <object>` lists privileges granted on that securable; `SHOW GRANTS TO ROLE`/`TO USER` lists privileges *held by* a role/user; `SHOW GRANTS OF ROLE` lists who the role is granted to.
</details>

---

### Question 343
Which of the following is an accurate characteristic of security in Snowflake?

- A. Account and authentication features are only available with Business Critical Edition.
- B. Support for HIPAA and GDPR compliance is available for all Snowflake editions.
- C. Periodic rekeying of encrypted data is available with Enterprise Edition and higher.
- D. Private connectivity to internal stages is allowed in Enterprise Edition and higher.

<details><summary>Show Answer</summary>
Correct Answer: C. HIPAA compliance specifically requires Business Critical Edition (a signed BAA), so B is wrong; private connectivity (PrivateLink) requires Business Critical Edition, so D is wrong too.
</details>

---

### Question 344
Which of the following objects can be shared through secure data sharing?

- A. Masking policy
- B. Stored procedure
- C. Task
- D. External table

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 345
Which of the following are valid semi-structured value types that Snowflake can store/represent? (Choose two)

- A. GeoJSON
- B. Array
- C. XML
- D. Object
- E. BLOB

<details><summary>Show Answer</summary>
Correct Answer: B, D (`ARRAY` and `OBJECT`, the two semi-structured value kinds a `VARIANT` column represents).
⚠ **Note:** this question is heavily OCR-corrupted in the source and its wording doesn't map cleanly to a documented Snowflake concept — the reconstruction above is a best-effort inference (it mirrors Question 338's answer pattern) and carries lower confidence than the others in this set. Verify against your original source if this one shows up on a practice test.
</details>

---

### Question 346
A user is preparing to load data from an external stage. Which practice will provide the MOST efficient loading performance?

- A. Organize files into logical paths (partitioned prefixes).
- B. Store the files on the external stage to ensure caching is maintained.
- C. Use pattern matching (regular expressions) to select files.
- D. Load the data in one large file.

<details><summary>Show Answer</summary>
Correct Answer: A. Path-based organization lets Snowflake load a targeted subset of files and enables concurrent `COPY` statements against different prefixes; regex pattern matching (C) is actually slower than an explicit file list, and one giant file (D) kills parallelism.
</details>

---

### Question 347
What effect does setting `WAIT_FOR_COMPLETION = TRUE` have when running an `ALTER WAREHOUSE` command to change the warehouse size?

- A. The warehouse size does not change until all queries currently running in the warehouse have completed.
- B. The warehouse size does not change until all queries currently queued in the warehouse have completed.
- C. The warehouse size does not change until the warehouse is suspended and restarted.
- D. The command does not return control until the warehouse has finished changing size.

<details><summary>Show Answer</summary>
Correct Answer: D. It's a synchronous-vs-asynchronous switch for the ALTER statement itself, not a delay on when resizing starts.
</details>

---

### Question 348
Which of the following can be used when unloading data from Snowflake? (Choose two)

- A. When unloading semi-structured data, it is recommended to use `FILE_EXTENSION`.
- B. Use the `ENCODING` file format option to change the encoding from the default.
- C. The `OBJECT_CONSTRUCT` function can be used to convert relational data to semi-structured data before unloading.
- D. By using the `SINGLE = TRUE` parameter, a single file up to 5 GB in size can be exported to the storage layer.
- E. Use the `PARSE_JSON` function to ensure structured data is unloaded into the `VARIANT` data type.

<details><summary>Show Answer</summary>
Correct Answer: C, D.
</details>

---

### Question 349
What data is stored in the Snowflake storage layer? (Choose two)

- A. Snowflake parameters
- B. Micro-partitions
- C. Query history
- D. Persisted query results
- E. Standard and secure view results

<details><summary>Show Answer</summary>
Correct Answer: B, C.
</details>

---

### Question 350
A data provider wants to share data with someone who does not have a Snowflake account. The provider creates a reader account, adds a user, creates a database and an X-Small warehouse for querying the data, and grants the `PUBLIC` role `USAGE` on the warehouse/database/schema and `SELECT` on the shared objects. Based on this configuration, what is true of the reader account?

- A. The reader account will automatically use Standard Edition.
- B. The reader account's compute will be billed to the provider account.
- C. The reader account can clone data the provider has shared, but cannot re-share it.
- D. The reader account can create a copy of the shared data using `CREATE TABLE AS SELECT`.

<details><summary>Show Answer</summary>
Correct Answer: B. Reader accounts have no billing relationship of their own — all their compute/storage costs are billed back to the provider account that created them.
</details>

---

### Question 351
Which of the following activities consume virtual warehouse credits? (Choose two)

- A. Caching query results
- B. Running `EXPLAIN` and `SHOW` commands (metadata-only, served by Cloud Services)
- C. Cloning a database (metadata operation)
- D. Running a custom query
- E. Running `COPY` commands

<details><summary>Show Answer</summary>
Correct Answer: D, E.
</details>

---

### Question 352
When loading data into Snowflake, the `COPY` command supports which of the following?

- A. Joins
- B. Filters
- C. Column reordering
- D. Aggregates

<details><summary>Show Answer</summary>
Correct Answer: C. `COPY INTO <table>` supports a limited transformation SELECT — column reordering, casts, and simple expressions — but not joins, filters (`WHERE`), or aggregates.
</details>

---

### Question 353
What is cached during a query on a virtual warehouse?

- A. All columns in a micro-partition
- B. Any columns accessed during the query
- C. Only the columns in the result set of the query
- D. All rows accessed during the query

<details><summary>Show Answer</summary>
Correct Answer: B. The warehouse's local SSD cache stores the raw columnar data that was scanned to answer the query — not just the final result columns.
</details>

---

### Question 354
What is the default character set used when loading CSV files into Snowflake?

- A. UTF-8
- B. UTF-16
- C. ISO-8859-1
- D. ANSI X3.4

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 355
Which of the following describes external functions in Snowflake?

- A. They are a type of User-Defined Function.
- B. They contain their own SQL code.
- C. They call code that is stored inside of Snowflake.
- D. They can return multiple rows for each row received.

<details><summary>Show Answer</summary>
Correct Answer: A. An external function is a UDF whose handler code runs outside Snowflake (e.g., in AWS Lambda/API Gateway) and is invoked over HTTPS — it must return exactly one row per input row.
</details>

---

### Question 356
Which of the following are valid methods for authenticating users into Snowflake? (Choose three)

- A. SCIM (user provisioning, not authentication)
- B. Federated authentication (SSO)
- C. Basic username/password authentication
- D. Key-pair authentication
- E. OAuth
- F. OCSP (certificate revocation checking, not authentication)

<details><summary>Show Answer</summary>
Correct Answer: B, D, E.
</details>

---

### Question 357
A user has a standard multi-cluster warehouse auto-scaling policy in place. Which condition will trigger a cluster to shut down?

- A. After 2–3 consecutive checks, the system determines the load on the **most**-loaded cluster could be redistributed.
- B. After 5–6 consecutive checks, the system determines the load on the **most**-loaded cluster could be redistributed.
- C. After 5–8 consecutive checks, the system determines the load on the **least**-loaded cluster could be redistributed.
- D. After 2–3 consecutive checks, the system determines the load on the **least**-loaded cluster could be redistributed.

<details><summary>Show Answer</summary>
Correct Answer: D. Verified against current documentation — under the Standard scaling policy, Snowflake checks the least-loaded cluster every minute and shuts it down after 2–3 consecutive checks confirm its load can be absorbed elsewhere. (The Economy policy uses 5–6 checks instead.)
</details>

---

### Question 358
What is the minimum Snowflake edition needed for database failover and fail-back between Snowflake accounts, for business continuity and disaster recovery?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake

<details><summary>Show Answer</summary>
Correct Answer: C. Verified — account/database failover and fail-back is a Business Critical Edition (or higher) feature. (Basic database replication without automated failover is available more broadly.)
</details>

---

### Question 359
How would a user execute a series of SQL statements using a single task?

- A. Chain multiple raw SQL statements directly in the task body.
- B. Sequence multiple stored procedure calls directly in the task body (a task supports only one statement).
- C. Wrap the multiple SQL statements inside a single stored procedure, and have the task call that procedure: `CREATE TASK mytask AS CALL my_procedure();`
- D. Create one task per SQL statement and chain them (task1 → task2 → …) using task dependencies.

<details><summary>Show Answer</summary>
Correct Answer: C. A task executes exactly one SQL statement (or one procedure call) per run — a multi-statement stored procedure is the standard way to run a sequence of statements from one task.
</details>

---

### Question 360
How many resource monitors can be assigned at the account level?

<details><summary>Show Answer</summary>
Correct Answer: 1. Verified against current documentation — only a single resource monitor can be set at the account level at any time (though many warehouse-level resource monitors can exist, and a warehouse can be assigned to at most one of them).
</details>

---

### Question 361
Data storage for individual tables can be monitored using which commands/objects? (Choose two)

- A. `SHOW STORAGE FOR TABLE`
- B. `SHOW TABLES`
- C. `INFORMATION_SCHEMA.TABLE_HISTORY`
- D. `INFORMATION_SCHEMA.TABLE_FUNCTION`
- E. `ACCOUNT_USAGE.TABLE_STORAGE_METRICS`

<details><summary>Show Answer</summary>
Correct Answer: B, E. `SHOW TABLES` returns each table's `bytes` (storage) column; `TABLE_STORAGE_METRICS` in `ACCOUNT_USAGE` gives detailed active/Time Travel/Fail-safe/clone storage bytes.
</details>

---

### Question 362
How would a user run a multi-cluster warehouse in maximized mode?

- A. Configure the maximum clusters setting to "Maximum."
- B. Turn on additional clusters manually after starting the warehouse.
- C. Set the minimum clusters and maximum clusters settings to the **same** value.
- D. Set the minimum clusters and maximum clusters settings to **different** values.

<details><summary>Show Answer</summary>
Correct Answer: C. Equal min/max clusters puts the warehouse in Maximized mode, where all clusters start immediately and run continuously; different min/max values put it in Auto-scale mode instead.
</details>

---

### Question 363
What internal stages are available in Snowflake? (Choose three)

- A. Schema stage (not a real stage type)
- B. Named stage
- C. User stage
- D. Stream stage (not a real stage type)
- E. Table stage
- F. Database stage (not a real stage type)

<details><summary>Show Answer</summary>
Correct Answer: B, C, E. Snowflake provides exactly three kinds of internal stage: named, user, and table stages.
</details>

---

### Question 364
Which stages are used with the `PUT` command to upload files from a local file system? (Choose three)

- A. Schema stage
- B. User stage
- C. Database stage
- D. Table stage
- E. External named stage
- F. Internal named stage

<details><summary>Show Answer</summary>
Correct Answer: B, D, F. `PUT` only works against *internal* stages (user, table, or internal named) — it cannot push files to an external stage, since Snowflake doesn't manage the credentials/API of external cloud storage the same way.
</details>

---

### Question 365
Which data type can store more than one type of data structure?

- A. JSON (a format, not a Snowflake data type)
- B. BINARY
- C. VARCHAR
- D. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 366
User-level network policies can be created and applied by which of the following roles? (Choose two)

- A. `ROLEADMIN` (not a default system role)
- B. `ACCOUNTADMIN`
- C. `SYSADMIN`
- D. `SECURITYADMIN`
- E. `USERADMIN`

<details><summary>Show Answer</summary>
Correct Answer: B, D. Network policies fall under `SECURITYADMIN`'s security-management scope, and `ACCOUNTADMIN` inherits everything `SECURITYADMIN` can do.
</details>

---

### Question 367
What SQL command would be used to view all roles that have been granted to `USER1`?

- A. `SHOW GRANTS TO USER1;` (invalid syntax)
- B. `SHOW GRANTS TO USER USER1;`
- C. `DESCRIBE USER USER1;`
- D. `SHOW GRANTS ON USER USER1;`

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 368
Which `ACCOUNT_USAGE` views are used to evaluate the details of dynamic data masking? (Choose two)

- A. `ROLES`
- B. `POLICY_REFERENCES`
- C. `QUERY_HISTORY`
- D. `RESOURCE_MONITORS`
- E. `MASKING_POLICIES`

<details><summary>Show Answer</summary>
Correct Answer: B, E. `MASKING_POLICIES` shows the defined policies; `POLICY_REFERENCES` shows what objects/columns each policy is actually attached to.
</details>

---

### Question 369
Which of the following are considerations when using a directory table when working with unstructured data? (Choose two)

- A. A directory table is a separate database object.
- B. Directory tables store data file metadata.
- C. A directory table will be automatically added to a stage.
- D. Directory tables do not have their own grantable privileges.
- E. Directory table data cannot be refreshed manually.

<details><summary>Show Answer</summary>
Correct Answer: B, D. A directory table isn't a standalone object — it's an implicit metadata layer attached to a stage (must be explicitly enabled via `DIRECTORY = (ENABLE = TRUE)`), and it inherits its privileges from the stage rather than having its own grantable privileges.
</details>

---

### Question 370
The first user assigned to a new account, using `ACCOUNTADMIN`, should create at least one additional user with which administrative privilege?

- A. `USERADMIN`
- B. `PUBLIC`
- C. `ORGADMIN`
- D. `SYSADMIN`

<details><summary>Show Answer</summary>
Correct Answer: A. Best practice is to avoid daily-driving `ACCOUNTADMIN` — create a `USERADMIN` user to handle ongoing user/role management instead.
</details>

---

### Question 371
Which statement describes how Snowflake supports reader accounts?

- A. A reader account can consume data from the provider account that created it and combine it with its own data.
- B. A consumer needs to become a licensed Snowflake customer, since data sharing is only supported between Snowflake accounts.
- C. Users in a reader account can query data shared with the account and can create their own tasks.
- D. The `SHOW MANAGED ACCOUNTS` command will list all reader accounts that have been created for an account.

<details><summary>Show Answer</summary>
Correct Answer: D. Reader accounts (a type of "managed account") cannot load their own data or combine it with shared data — they exist purely to query what's been shared with them.
</details>

---

### Question 372
Can a data provider with an Azure account in Central Canada share data with a data consumer on AWS in Australia?

- A. The provider in Azure Central Canada can create a direct share to AWS Asia Pacific, if both are in the same organization.
- B. The consumer and provider can form a Data Exchange within the same organization to share across regions/clouds.
- C. The provider can use the "Get Data" workflow in Snowflake Marketplace to bridge Azure Central Canada and AWS Asia Pacific.
- D. The provider must replicate the database to a secondary account in AWS Asia Pacific (within the same organization), then share from that secondary account.

<details><summary>Show Answer</summary>
Correct Answer: D. Direct secure shares only work between accounts on the same cloud platform and in the same region — crossing cloud/region boundaries requires replicating the database to an account on the target platform/region first.
</details>

---

### Question 373
Which Snowflake objects can be shared with other Snowflake accounts? (Choose three)

- A. Schemas
- B. Roles
- C. Secure Views
- D. Stored Procedures
- E. Tables
- F. Functions (Secure UDFs)

<details><summary>Show Answer</summary>
Correct Answer: C, E, F.
</details>

---

### Question 374
Which Snowflake feature will allow small volumes of data to continuously load into Snowflake, incrementally making it available for analysis?

- A. `COPY INTO`
- B. `CREATE PIPE` (Snowpipe)
- C. `INSERT INTO`
- D. `TABLE STREAM`

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 375
Which partner specializes in data catalog solutions in the Snowflake ecosystem?

- A. Alation
- B. DataRobot
- C. dbt
- D. Tableau

<details><summary>Show Answer</summary>
Correct Answer: A. Alation is a data-catalog/governance partner; DataRobot is ML/AutoML, dbt is transformation, and Tableau is BI/visualization.
</details>

---

### Question 376
Which of the following can be executed/called by Snowpipe?

- A. A User-Defined Function
- B. A stored procedure
- C. A single `COPY INTO <table>` statement
- D. A single `INSERT INTO` statement

<details><summary>Show Answer</summary>
Correct Answer: C. A pipe wraps exactly one `COPY INTO <table>` statement.
</details>

---

### Question 377
Which Snowflake objects will incur both storage and compute charges? (Choose two)

- A. Materialized view
- B. Sequence
- C. View
- D. Transient table
- E. A table using Automatic Clustering

<details><summary>Show Answer</summary>
Correct Answer: A, E. Materialized views incur storage plus background serverless compute to stay in sync with the base table; a clustered table incurs storage plus serverless compute for automatic reclustering. Plain views and sequences store no data of their own, and a transient table only incurs storage (its query compute is no different from any other table).
</details>

---

### Question 378
Which file formats does Snowflake support for loading semi-structured data? (Choose three)

- A. CSV
- B. JSON
- C. PDF
- D. Avro
- E. Parquet
- F. JPEG

<details><summary>Show Answer</summary>
Correct Answer: B, D, E. (Snowflake also supports ORC and XML for semi-structured loading, but those weren't offered as options here.)
</details>

---

### Question 379
Which of the following statements about data sharing are true? (Choose two)

- A. New objects created by a data provider are automatically shared with existing consumers and reader accounts.
- B. All database objects can be included in a shared database.
- C. Reader accounts are created by data providers.
- D. Shared databases are read-only.
- E. Reader accounts are charged for their own warehouse usage.

<details><summary>Show Answer</summary>
Correct Answer: C, D.
</details>

---

### Question 380
Credit charges for Snowflake virtual warehouses are based on which of the following? (Choose two)

- A. The number of queries executed
- B. The number of active clusters assigned to the warehouse
- C. The size of the virtual warehouse
- D. The length of time the warehouse is running
- E. The duration of the queries executed

<details><summary>Show Answer</summary>
Correct Answer: C, D.
</details>

---

### Question 381
Which of the following are handled by the Cloud Services layer of the Snowflake architecture? (Choose two)

- A. Data loading (compute layer)
- B. Query execution (compute layer)
- C. Time Travel data (storage layer)
- D. Security
- E. Authentication and access control

<details><summary>Show Answer</summary>
Correct Answer: D, E. Cloud Services handles authentication, infrastructure/metadata management, security, query parsing/optimization, and orchestration — not the actual data loading, query execution, or storage of Time Travel data.
</details>

---

### Question 382
What is a responsibility of Snowflake's virtual warehouses?

- A. Infrastructure management
- B. Metadata management
- C. Query execution
- D. Query parsing and optimization
- E. Permanent storage of micro-partitions

<details><summary>Show Answer</summary>
Correct Answer: C. Warehouses (Compute layer) execute queries; parsing/optimization/metadata/infrastructure management belong to the Cloud Services layer, and permanent storage belongs to the Storage layer.
</details>

---

### Question 383
What features does Snowflake Time Travel enable?

- A. Querying data-related objects that were created within the past 365 days.
- B. Restoring data-related objects that have been deleted within the past 90 days.
- C. Conducting point-in-time historical analysis.
- D. Analyzing data usage/manipulation over all periods of time (unlimited).

<details><summary>Show Answer</summary>
Correct Answer: C. Time Travel's retention window tops out at 90 days (Enterprise Edition+, on permanent objects), not 365 days, and it doesn't cover "all periods of time" — B and D overstate the retention window/scope.
</details>

---

### Question 384
Which of the following statements describes a schema in Snowflake?

- A. A logical grouping of objects that belongs to a single database.
- B. A grouping of objects that belongs to multiple databases.
- C. A named Snowflake object that includes all the information required to share a database.
- D. A uniquely identified Snowflake account within a business entity.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 385
What is the recommended compressed file size range for continuous data loads using Snowpipe?

- A. 1–16 MB
- B. 16–24 MB
- C. 50–100 MB
- D. 100–250 MB

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 386
How long is Snowpipe data load history retained?

- A. As configured in the `CREATE PIPE` settings
- B. Until the pipe is dropped
- C. 64 days
- D. 14 days

<details><summary>Show Answer</summary>
Correct Answer: D. Verified against current documentation — this is stored in the pipe's own metadata for 14 days, unlike bulk-load history (target table metadata, 64 days — see Question 341).
</details>

---

### Question 387
Snowflake users self-enrolling in the default Multi-Factor Authentication (MFA) service need to install which application on their devices to connect with MFA?

- A. Okta Verify
- B. Duo Mobile
- C. Microsoft Authenticator
- D. Google Authenticator

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake's native MFA is powered by the Duo Security service, so the Duo Mobile app is what's required (though it also supports SMS/phone-call fallback through Duo).
</details>

---

### Question 388
Which URL type allows users to access unstructured data without authenticating into Snowflake or passing an authorization token?

- A. Pre-signed URL
- B. Scoped URL
- C. Signed URL (not a Snowflake term)
- D. File URL

<details><summary>Show Answer</summary>
Correct Answer: A. A pre-signed URL is temporary and self-contained — no Snowflake session or token is needed. A scoped URL (B) still requires an active Snowflake session/token to resolve, and a file URL (D) requires both a role with the READ privilege on the stage and a valid access token.
</details>

---

### Question 389
Where would a Snowflake user find information about query activity from 90 days ago?

- A. `ACCOUNT_USAGE.QUERY_HISTORY` view
- B. `INFORMATION_SCHEMA.QUERY_HISTORY` view
- C. The Snowsight "Query History" page (UI)
- D. `INFORMATION_SCHEMA.QUERY_HISTORY` table function

<details><summary>Show Answer</summary>
Correct Answer: A. `INFORMATION_SCHEMA`'s query history views/functions only cover roughly the last 7 days–6 months depending on the function, with tighter limits; `ACCOUNT_USAGE.QUERY_HISTORY` retains history for 365 days, which is what's needed to reach back 90 days reliably.
</details>

---

### Question 390
A marketing co-worker has requested the ability to change a warehouse's size on their Medium virtual warehouse, `MKTG_WH`. Which statement will accommodate this?

- A. `ALLOW RESIZE ON WAREHOUSE MKTG_WH TO USER MKTG_LEAD;` (not valid SQL)
- B. `GRANT MODIFY ON WAREHOUSE MKTG_WH TO ROLE MARKETING;`
- C. `GRANT USAGE ON WAREHOUSE MKTG_WH TO USER MKTG_LEAD;`
- D. `GRANT OPERATE ON WAREHOUSE MKTG_WH TO ROLE MARKETING;`

<details><summary>Show Answer</summary>
Correct Answer: B.
⚠ **Updated:** the source material's marked answer for this question was illegible/ambiguous in the raw OCR, so this is presented as freshly verified rather than corrected. This is also a classic exam trap: `OPERATE` only lets you start/stop/suspend/resume a warehouse — **resizing a warehouse's properties (including `WAREHOUSE_SIZE`) requires the `MODIFY` privilege**, not `OPERATE`.
</details>

---

### Question 391
Which of the following commands **cannot** be used within a reader account?

- A. `CREATE SHARE`
- B. `ALTER WAREHOUSE`
- C. `CREATE ROLE`
- D. `SHOW SCHEMAS`
- E. `DESCRIBE TABLE`

<details><summary>Show Answer</summary>
Correct Answer: A. Reader accounts can only consume shared data — they have no data of their own to share, so they can't create outbound shares.
</details>

---

### Question 392
Which table function helps convert semi-structured data into a relational representation?

- A. `CHECK_JSON`
- B. `TO_JSON`
- C. `FLATTEN`
- D. `PARSE_JSON`

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 393
Which query statistics help determine whether efficient pruning is occurring? (Choose two)

- A. Bytes sent over the network
- B. Percentage scanned from cache
- C. Partitions total
- D. Bytes spilled to local storage
- E. Partitions scanned

<details><summary>Show Answer</summary>
Correct Answer: C, E. Comparing "partitions scanned" to "partitions total" (both shown in the query profile) tells you how effective pruning was for that query.
</details>

---

### Question 394
What are the default Time Travel and Fail-safe retention periods for transient tables?

- A. Time Travel — 0 days, Fail-safe — 1 day
- B. Time Travel — 0 days, Fail-safe — 0 days
- C. Time Travel — 1 day, Fail-safe — 0 days
- D. Transient tables are retained in neither Fail-safe nor Time Travel.

<details><summary>Show Answer</summary>
Correct Answer: C. Transient tables get the standard default of 1 day of Time Travel (configurable 0–1 day) but, unlike permanent tables, they get **no** Fail-safe period at all.
</details>

---

### Question 395
Which command is used to unload data from a Snowflake table into a file in a stage?

- A. `COPY INTO`
- B. `GET`
- C. `WRITE`
- D. `EXTRACT INTO`

<details><summary>Show Answer</summary>
Correct Answer: A. `COPY INTO <location>` (the same command family, just pointed at a stage instead of a table) unloads data.
</details>

---

### Question 396
What are advantages clones have over tables created with a `CREATE TABLE AS SELECT` statement? (Choose two)

- A. The clone always stays in sync with the original table.
- B. The clone has better query performance.
- C. The clone is created almost instantly.
- D. The clone will have Time Travel history from the original table.
- E. The clone saves space by not duplicating storage.

<details><summary>Show Answer</summary>
Correct Answer: C, E. Zero-copy cloning is a metadata-only operation (instant, no storage duplication at creation time — storage is only consumed as the clone and original diverge). It is a point-in-time snapshot, though, so A and D are wrong — a clone does *not* stay in sync with later changes, and it does not inherit the original's historical Time Travel data.
</details>

---

### Question 397
How often are the Account and Table master keys automatically rotated by Snowflake?

- A. 30 days
- B. 60 days
- C. 90 days
- D. 365 days

<details><summary>Show Answer</summary>
Correct Answer: A. Verified against current documentation — Snowflake-managed keys are automatically rotated once they're more than 30 days old. (Don't confuse this with **periodic rekeying**, an optional feature that re-encrypts data with a brand-new key once a retired key has been inactive for a full year.)
</details>

---

### Question 398
Which privilege is required for a role to be able to resume a suspended warehouse if auto-resume is not enabled?

- A. `USAGE`
- B. `OPERATE`
- C. `MONITOR`
- D. `MODIFY`

<details><summary>Show Answer</summary>
Correct Answer: B. Note `OPERATE` implicitly includes `USAGE`, but on its own `USAGE` cannot start/resume a warehouse.
</details>

---

### Question 399
Which statement MOST accurately describes clustering in Snowflake?

- A. The `ACCOUNTADMIN` must define the clustering methodology for each Snowflake table.
- B. Clustering is the way data is grouped together and stored within Snowflake micro-partitions.
- C. The clustering key must be included in the `COPY` command when loading data into Snowflake.
- D. Clustering can be disabled within a Snowflake account.

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 400
Which of the following practices are recommended when creating a user in Snowflake? (Choose two)

- A. Configure the user to be initially disabled.
- B. Force an immediate password change on first login.
- C. Set a default role for the user.
- D. Set the number of minutes to unlock the account to 15 minutes.
- E. Set the user's access to expire within a specified timeframe.

<details><summary>Show Answer</summary>
Correct Answer: B, C.
</details>

---

### Question 401
Network policies can be applied to which of the following objects? (Choose two)

- A. Roles
- B. Databases
- C. Warehouses
- D. Users
- E. Accounts

<details><summary>Show Answer</summary>
Correct Answer: D, E. A network policy can be set at the account level (applies to everyone) or attached to individual users to override the account-level policy.
</details>

---

### Question 402
Where is Snowflake metadata stored?

- A. Within the data files
- B. In the virtual warehouse layer
- C. In the Cloud Services layer
- D. In the remote storage layer

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 403
What columns are returned when performing a `FLATTEN` operation on semi-structured data? (Choose two)

- A. `KEY`
- B. `NODE`
- C. `VALUE`
- D. `LEVEL`
- E. `ROOT`

<details><summary>Show Answer</summary>
Correct Answer: A, C. (`FLATTEN` actually returns `SEQ`, `KEY`, `PATH`, `INDEX`, `VALUE`, and `THIS` — of the options offered here, `KEY` and `VALUE` are the real ones.)
</details>

---

### Question 404
Which of the following Snowflake features provide continuous data protection? (Choose two)

- A. Internal stages
- B. Backups (not a Snowflake concept — protection is built in)
- C. Time Travel
- D. Zero-copy clones
- E. Fail-safe

<details><summary>Show Answer</summary>
Correct Answer: C, E. Time Travel (user-recoverable) and Fail-safe (Snowflake-recoverable, non-configurable) together make up Snowflake's Continuous Data Protection lifecycle.
</details>

---

### Question 405
A developer is granted ownership of a table that has a masking policy applied. The developer's role is not able to see the masked data. Will the developer be able to modify the table to read the masked data?

- A. Yes, because a table owner has full control and can unset masking policies.
- B. Yes, because masking policies only apply to cloned tables.
- C. No, because masking policies must always reference specific access roles.
- D. No, because ownership of a table does not include the ability to change masking policies.

<details><summary>Show Answer</summary>
Correct Answer: D. Managing masking policies (`APPLY MASKING POLICY`) is a separate, governance-level privilege — table `OWNERSHIP` does not automatically grant it. This is by design, so table owners can't casually bypass column-level security.
</details>

---

### Question 406
How should a virtual warehouse be configured to ensure that additional clusters resume with the least possible delay?

- A. Set the warehouse to a size larger than generally needed.
- B. Configure Auto-scale mode with a wide min/max cluster range.
- C. Use the Standard warehouse scaling policy.
- D. Use the Economy warehouse scaling policy.

<details><summary>Show Answer</summary>
Correct Answer: C. Of the two scaling policies, Standard is the responsiveness-first option — it starts a new cluster immediately on queuing (with a fixed ~20-second stagger between clusters), whereas Economy deliberately waits to confirm ~6 minutes of sustained demand before adding a cluster. (For literally zero delay, Maximized mode — equal min/max clusters, all running continuously — is the strongest option, but it isn't one of the choices offered here.)
</details>

---

### Question 407
During periods of warehouse contention, which parameter controls the maximum length of time a warehouse will hold a query for processing before canceling it?

- A. `STATEMENT_TIMEOUT_IN_SECONDS`
- B. `STATEMENT_QUEUED_TIMEOUT_IN_SECONDS`
- C. `LOCK_TIMEOUT`
- D. `QUERY_TIMEOUT_IN_SECONDS`

<details><summary>Show Answer</summary>
Correct Answer: B. This specifically governs how long a query can sit *queued* on a busy warehouse before Snowflake cancels it, distinct from `STATEMENT_TIMEOUT_IN_SECONDS`, which limits total execution time once a query is actually running.
</details>

---

### Question 408
Files have been uploaded to a Snowflake internal stage. The files now need to be deleted. Which SQL command should be used?

- A. `PURGE` (not a standalone command — it's a COPY option)
- B. `MODIFY`
- C. `REMOVE`
- D. `DELETE`

<details><summary>Show Answer</summary>
Correct Answer: C. `REMOVE` (or its alias `RM`) deletes files from a stage. `DELETE` removes *rows from a table*, not stage files.
</details>

---

## Summary of documentation-verified corrections/confirmations

| # | Topic | Verified answer |
|---|---|---|
| 332 | Min. edition for periodic rekeying | Enterprise |
| 341 | Bulk `COPY` load history location/retention | Target table metadata, 64 days |
| 357 | Standard scaling policy cluster shutdown | 2–3 checks, least-loaded cluster |
| 358 | Min. edition for account failover/fail-back | Business Critical |
| 360 | Resource monitors allowed at account level | 1 |
| 386 | Snowpipe load history location/retention | Pipe metadata, 14 days |
| 387 | Native MFA app | Duo Mobile (Duo Security service) |
| 390 | Privilege to resize a warehouse | `MODIFY` (not `OPERATE`) |
| 397 | Account/table master key rotation interval | 30 days |



====================================================================================================
# SnowPro_401-500.md
====================================================================================================

# SnowPro Core Practice Questions (401–500)

*Formatted for self-study. Answers are hidden in collapsible blocks — click "Show Answer" to reveal. Answers were cross-checked against current Snowflake documentation (as of July 2026); any corrections are flagged with ⚠ Updated.*

---

### Question 401
Network policies can be applied to which of the following objects? (Choose two.)
- A. Roles
- B. Databases
- C. Warehouses
- D. Users
- E. Accounts

<details><summary>Show Answer</summary>
Correct Answer: D, E. Network policies restrict IP-based access and can be applied at the account level or to individual users.
</details>

---

### Question 402
Where is Snowflake metadata stored?
- A. Within the data files
- B. In the virtual warehouse layer
- C. In the cloud services layer
- D. In the remote storage

<details><summary>Show Answer</summary>
Correct Answer: C. The cloud services layer manages metadata, query optimization, security, and coordination across the platform.
</details>

---

### Question 403
What columns are returned when performing a FLATTEN command on semi-structured data? (Choose two.)
- A. KEY
- B. NODE
- C. VALUE
- D. LEVEL
- E. ROOT

<details><summary>Show Answer</summary>
Correct Answer: A, C. FLATTEN returns SEQ, KEY, PATH, INDEX, VALUE, THIS as columns; KEY and VALUE are among the standard output columns.
</details>

---

### Question 404
Which of the following Snowflake features provide continuous data protection? (Choose two.)
- A. Internal stages
- B. Backups
- C. Time Travel
- D. Zero-copy clones
- E. Fail-safe

<details><summary>Show Answer</summary>
Correct Answer: C, E. Time Travel and Fail-safe together form Snowflake's Continuous Data Protection (CDP) lifecycle.
</details>

---

### Question 405
A developer is granted ownership of a table that has a masking policy applied. The developer's role is not able to see the masked data. Will the developer be able to modify the table to read the masked data?
- A. Yes, because a table owner has control and can unset masking policies.
- B. Yes, because masking policies only apply to cloned tables.
- C. No, because masking policies must always reference specific access roles.
- D. No, because ownership of a table does not include the ability to change masking policies.

<details><summary>Show Answer</summary>
Correct Answer: D. Managing masking policies requires a separate privilege (e.g., APPLY MASKING POLICY); table ownership alone does not grant this.
</details>

---

### Question 406
How should a virtual warehouse be configured if a user wants to ensure that additional multi-clusters are resumed with no delay?
- A. Set the warehouse to a size larger than generally needed
- B. Set the minimum and maximum clusters to autoscale
- C. Use the standard warehouse scaling policy
- D. Use the economy warehouse scaling policy

<details><summary>Show Answer</summary>
Correct Answer: C. The Standard scaling policy favors starting additional clusters immediately to minimize queuing, unlike Economy, which waits to conserve credits.
</details>

---

### Question 407
During periods of warehouse contention, which parameter controls the maximum length of time a warehouse will hold a query for processing?
- A. STATEMENT_TIMEOUT_IN_SECONDS
- B. STATEMENT_QUEUED_TIMEOUT_IN_SECONDS
- C. MAX_CONCURRENCY_LEVEL
- D. MAX_STATEMENT_TIME

<details><summary>Show Answer</summary>
Correct Answer: B. STATEMENT_QUEUED_TIMEOUT_IN_SECONDS controls how long a query can sit in the queue before it is canceled.
</details>

---

### Question 408
Files have been uploaded to a Snowflake internal stage. The files now need to be deleted. Which SQL command should be used to delete the files?
- A. PURGE
- B. MODIFY
- C. REMOVE
- D. DELETE

<details><summary>Show Answer</summary>
Correct Answer: C. REMOVE deletes files from an internal or external stage.
</details>

---

### Question 409
In a Snowflake role hierarchy, what is the top-level role?
- A. SYSADMIN
- B. ORGADMIN
- C. ACCOUNTADMIN
- D. SECURITYADMIN

<details><summary>Show Answer</summary>
Correct Answer: C. ACCOUNTADMIN sits at the top of the default account-level role hierarchy (ORGADMIN operates at the organization level, above individual accounts).
</details>

---

### Question 410
By default, which Snowflake role is required to create a share?
- A. ORGADMIN
- B. SECURITYADMIN
- C. SHAREADMIN
- D. ACCOUNTADMIN

<details><summary>Show Answer</summary>
Correct Answer: D. Only ACCOUNTADMIN (or a role explicitly granted the CREATE SHARE privilege) can create outbound shares by default.
</details>

---

### Question 411
What happens to historical data when the retention period for an object ends?
- A. The data is cloned into a historical object.
- B. The data moves to Fail-safe.
- C. Time Travel on the historical data is dropped.
- D. The object containing the historical data is dropped.

<details><summary>Show Answer</summary>
Correct Answer: B. Once the Time Travel retention period expires, historical data enters the 7-day Fail-safe period (for permanent tables).
</details>

---

### Question 412
A company's security audit requires generating a report listing all Snowflake logins (e.g., date and user) within the last 90 days. Which of the following statements will return the required information?
- A. SELECT LOGIN_NAME FROM ACCOUNT_USAGE.USERS;
- B. SELECT EVENT_TIMESTAMP, USER_NAME FROM table(information_schema.login_history());
- C. SELECT EVENT_TIMESTAMP, USER_NAME FROM ACCOUNT_USAGE.QUERY_HISTORY;
- D. SELECT EVENT_TIMESTAMP, USER_NAME FROM ACCOUNT_USAGE.LOGIN_HISTORY;

<details><summary>Show Answer</summary>
Correct Answer: D. ACCOUNT_USAGE.LOGIN_HISTORY retains data for 365 days, covering the required 90-day window; INFORMATION_SCHEMA.LOGIN_HISTORY() only covers the last 7 days.
</details>

---

### Question 413
What are common issues found by using the Query Profile? (Choose two.)
- A. Identifying queries that will likely run very slowly before executing them
- B. Locating queries that consume a high amount of credits
- C. Identifying logical issues with the queries
- D. Identifying inefficient micro-partition pruning
- E. Spilling to local or remote disk

<details><summary>Show Answer</summary>
Correct Answer: D, E. Query Profile is used post-execution to diagnose issues like poor pruning and memory spillage to disk.
</details>

---

### Question 414
The Snowflake Search Optimization Service supports improved performance of which kind of queries?
- A. Queries against large tables where frequent updates occur
- B. Queries against tables larger than 1 TB
- C. Selective point lookup queries
- D. Queries against a subset of columns in a table

<details><summary>Show Answer</summary>
Correct Answer: C. Search Optimization Service is designed to speed up highly selective point lookup queries on large tables.
</details>

---

### Question 415
Which file formats are supported for unloading data from Snowflake? (Choose two.)
- A. AVRO
- B. JSON
- C. ORC
- D. XML
- E. Delimited (CSV, TSV, etc.)

<details><summary>Show Answer</summary>
Correct Answer: B, E. Snowflake supports unloading to delimited (CSV/TSV) and JSON formats (Parquet is also supported for unload; AVRO, ORC, and XML are load-only formats).
</details>

---

### Question 416
Which Snowflake tool would be BEST to troubleshoot network connectivity?
- A. snowCLI
- B. SnowUI
- C. snowsql
- D. snowcd

<details><summary>Show Answer</summary>
Correct Answer: D. SnowCD (Snowflake Connectivity Diagnostic Tool) tests and troubleshoots network connectivity to Snowflake.
</details>

---

### Question 417
Increasing the size of a virtual warehouse from an X-Small to an X-Large is an example of which of the following?
- A. Right sizing
- B. Concurrent scaling
- C. Scaling out
- D. Scaling up

<details><summary>Show Answer</summary>
Correct Answer: D. Increasing a single warehouse's size is "scaling up"; adding more clusters (multi-cluster) is "scaling out."
</details>

---

### Question 418
What are ways to create and manage data shares in Snowflake? (Choose two.)
- A. Through the Snowflake web interface
- B. Through the Data Marketplace parameter
- C. Through SQL commands
- D. Through the Reader Account interface
- E. Using the CREATE SHARE AS SELECT FROM TABLE command

<details><summary>Show Answer</summary>
Correct Answer: A, C. Shares can be managed via Snowsight or via SQL (CREATE SHARE, GRANT ... TO SHARE, ALTER SHARE, etc.).
</details>

---

### Question 419
What is a characteristic of data micro-partitioning in Snowflake?
- A. Micro-partitioning may introduce data skew.
- B. Micro-partitioning requires the definition of a partitioning schema.
- C. Micro-partitioning happens automatically when the data is loaded.
- D. Micro-partitioning can be disabled within a Snowflake account.

<details><summary>Show Answer</summary>
Correct Answer: C. Micro-partitioning is automatic and transparent — Snowflake handles it without any manual partitioning scheme.
</details>

---

### Question 420
Users with the ACCOUNTADMIN role can perform which of the following commands on existing users?
- A. Can SHOW users, DESCRIBE a given user, or ALTER or DROP a user
- B. Can DEFINE users, DESCRIBE a given user, or ALTER or DELETE a user
- C. Can SHOW users, INDEX a given user, or ALTER or DELETE a user
- D. Can SHOW users, DEFINE a given user or ALTER, DROP, or MODIFY a user

<details><summary>Show Answer</summary>
Correct Answer: A. The valid DDL/DCL verbs for user objects are SHOW, DESCRIBE, ALTER, and DROP.
</details>

---

### Question 421
According to Snowflake best practice recommendations, which system-defined roles should be used to create custom roles? (Choose two.)
- A. ACCOUNTADMIN
- B. SYSADMIN
- C. SECURITYADMIN
- D. USERADMIN
- E. ORGADMIN

<details><summary>Show Answer</summary>
Correct Answer: C, D. SECURITYADMIN (or its child USERADMIN) should be used to create and manage roles, keeping role administration separate from system/object administration.
</details>

---

### Question 422
What services are provided by the cloud services layer in Snowflake? (Choose two.)
- A. Metadata management
- B. Object authorization
- C. Authentication
- D. Query execution
- E. Result caching

<details><summary>Show Answer</summary>
Correct Answer: A, C. The cloud services layer handles authentication, metadata management, infrastructure management, access control, and query parsing/optimization. (Query execution happens in the compute layer; result caching is a byproduct stored via the cloud services layer, but the clearest fits here are metadata and authentication.)
</details>

---

### Question 423
Which of the following commands are valid options for the VALIDATION_MODE parameter within the Snowflake COPY INTO command? (Choose two.)
- A. RETURN_ROWS
- B. TRUE
- C. RETURN_ERRORS
- D. FALSE

<details><summary>Show Answer</summary>
Correct Answer: A, C. Valid VALIDATION_MODE values include RETURN_n_ROWS, RETURN_ERRORS, and RETURN_ALL_ERRORS.
</details>

---

### Question 424
Snowflake virtual warehouses are part of which layer of the Snowflake architecture?
- A. Compute layer
- B. Storage layer
- C. Database layer
- D. Cloud services layer

<details><summary>Show Answer</summary>
Correct Answer: A. Virtual warehouses make up the compute (query processing) layer.
</details>

---

### Question 425
Which of the following are characteristics of schemas used in Snowflake? (Choose two.)
- A. A schema may contain one or more databases.
- B. A database may contain one or more schemas.
- C. A schema represents a logical grouping of database objects.
- D. Each schema is contained within a virtual warehouse.
- E. A table can span more than one schema.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Databases contain one or more schemas, and each schema logically groups objects like tables, views, and procedures.
</details>

---

### Question 426
Which objects can be used to reduce data storage costs for short-lived tables? (Choose two.)
- A. Provisional tables
- B. Temporary tables
- C. Transient tables
- D. Permanent tables
- E. Lookup tables

<details><summary>Show Answer</summary>
Correct Answer: B, C. Temporary and transient tables skip Fail-safe (and in the case of temporary tables, are session-scoped), reducing storage costs versus permanent tables.
</details>

---

### Question 427
A user has unloaded data from Snowflake to a stage. Which SQL command should be used to validate which data was loaded into the stage?
- A. LIST @file_stage
- B. SHOW
- C. VIEW
- D. VERIFY

<details><summary>Show Answer</summary>
Correct Answer: A. LIST (or the `ls` shortcut) displays the files present in a stage.
</details>

---

### Question 428
What are benefits of using the ACCESS_HISTORY view in the SNOWFLAKE database? (Choose two.)
- A. Identification of unused data
- B. Identification of which roles have been used
- C. Tracking of network policy usage
- D. Highlighting of row access policy usage
- E. Identification of who has read data

<details><summary>Show Answer</summary>
Correct Answer: A, E. ACCESS_HISTORY tracks read/write activity on objects and columns, helping identify unused data and who accessed specific data.
</details>

---

### Question 429
Which of the following view types are available in Snowflake? (Choose two.)
- A. Layered view
- B. Secure view
- C. External view
- D. Embedded view
- E. Materialized view

<details><summary>Show Answer</summary>
Correct Answer: B, E. Snowflake supports standard (non-materialized), secure, and materialized views.
</details>

---

### Question 430
Which of the following statements describes a benefit of Snowflake's separation of compute and storage? (Choose two.)
- A. Growth of storage and compute are tightly coupled.
- B. Storage expands without the requirement to add more compute.
- C. Compute can be scaled up or down without the requirement to add more storage.
- D. Compute and storage can be scaled together.
- E. Use of storage avoids disk spilling.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Snowflake's architecture decouples compute and storage, so each can scale independently.
</details>

---

### Question 431
Which of the following languages can be used to implement Snowflake User-Defined Functions (UDFs)? (Choose two.)
- A. Ruby
- B. JavaScript
- C. SQL
- D. PERL

<details><summary>Show Answer</summary>
Correct Answer: B, C. Snowflake UDFs support SQL, JavaScript, Java, Python, and Scala (Ruby and PERL are not supported).
</details>

---

### Question 432
What is the default compression type when unloading data from Snowflake?
- A. Brotli
- B. bzip2
- C. Zstandard
- D. gzip

<details><summary>Show Answer</summary>
Correct Answer: D. gzip is the default compression for unloaded files.
</details>

---

### Question 433
Which statement describes when a virtual warehouse can be resized?
- A. A resize will affect running, queued, and past queries.
- B. A resize can only be completed when the warehouse is in an auto-resume status.
- C. A resize must be completed when the warehouse is suspended.
- D. A resize can be completed at any time.

<details><summary>Show Answer</summary>
Correct Answer: D. A warehouse can be resized at any time, including while running; currently executing statements are unaffected, and new resources apply to queued and future statements.
</details>

---

### Question 434
What is the compressed size limit for semi-structured data loaded into a VARIANT data type using the COPY command?
- A. 8 MB
- B. 16 MB
- C. 32 MB
- D. 64 MB

<details><summary>Show Answer</summary>
Correct Answer: B. The maximum compressed size for a VARIANT value is 16 MB.
</details>

---

### Question 435
User A cloned a schema and overwrote a schema that User B was working on. User B no longer has access to their version of the tables. However, this all occurred within the Time Travel retention period defined at the database level. How should the missing tables be restored?
- A. Use an UNDROP TABLE statement
- B. Use a CREATE TABLE AS SELECT statement
- C. Rename the cloned schema and use an UNDROP SCHEMA statement.
- D. Contact Snowflake Support to retrieve the data from Fail-safe.

<details><summary>Show Answer</summary>
Correct Answer: C. Since the original schema was overwritten (not individually dropped tables), the new schema must be renamed out of the way, then UNDROP SCHEMA restores the original.
</details>

---

### Question 436
How does Snowflake recommend handling the bulk loading of data batches from files already available in cloud storage?
- A. Use Snowpipe
- B. Use the INSERT command
- C. Use an external table
- D. Use the COPY command

<details><summary>Show Answer</summary>
Correct Answer: D. COPY INTO is the recommended method for bulk-loading existing batches of files (Snowpipe is for continuous, event-driven loading).
</details>

---

### Question 437
What is Snowflake's general guideline for files used to load data?
- A. Files can be loaded directly into a table.
- B. Any delimiter is supported; the default is a semicolon.
- C. Electronic Data Interchange (EDI) is one of the supported formats.
- D. For delimited files, the default character set is UTF-8.

<details><summary>Show Answer</summary>
Correct Answer: D. UTF-8 is the default character set for delimited files (files must first be staged, not loaded directly; the default delimiter is a comma, not a semicolon; EDI is not a supported format).
</details>

---

### Question 438
How does a Snowflake user execute an anonymous block of code?
- A. The user must run the CALL command to execute the block.
- B. The statements that define the block must also execute the block.
- C. The SUBMIT command must run immediately after the block is defined.
- D. The block must be saved to a worksheet and executed using a connector.

<details><summary>Show Answer</summary>
Correct Answer: B. An anonymous block (BEGIN…END) is executed as soon as it is submitted — the defining statement is also the execution.
</details>

---

### Question 439
When unloading data from Snowflake, the user executes a COPY INTO [location] command into an internal stage. What additional command is required to load the file onto the local file system?
- A. GET
- B. LIST
- C. PUT
- D. REMOVE

<details><summary>Show Answer</summary>
Correct Answer: A. GET downloads files from an internal stage to the local file system (PUT does the reverse — uploading local files to a stage).
</details>

---

### Question 440
A Snowflake user has a query that is running for a long time. When viewing the query profiler, it indicates that a lot of data is spilling to disk. What is causing this to happen?
- A. The result cache is almost full and is unable to hold the results.
- B. The Cloud Storage staging area is not sufficient to hold the data.
- C. Clustering has not been applied to the table so the table is not optimized.
- D. The warehouse memory is not sufficient to hold the intermediate query results.

<details><summary>Show Answer</summary>
Correct Answer: D. Spilling occurs when a warehouse's available memory (and then local disk) is insufficient for intermediate results, indicating the warehouse may need to be resized larger.
</details>

---

### Question 441
What is the MOST efficient file format for loading data in Snowflake?
- A. CSV (Unzipped)
- B. Parquet
- C. CSV (Gzipped)
- D. ORC

<details><summary>Show Answer</summary>
Correct Answer: C. Compressed (gzipped) delimited files are generally the most efficient for the load process, since compression reduces transfer size while remaining splittable for parallel loading.
</details>

---

### Question 442
Which chart type does Snowsight support to visualize worksheet data?
- A. Box plot
- B. Bubble chart
- C. Pie chart
- D. Scatter plot

<details><summary>Show Answer</summary>
Correct Answer: D. Snowsight's chart builder supports scatter plots among its chart types (along with line, bar, and area charts).
</details>

---

### Question 443
Which result shows efficient pruning?
- A. Partitions scanned is greater than partitions total.
- B. Partitions scanned is less than partitions total.
- C. Partitions scanned is equal to the partitions total.
- D. Partitions scanned is greater than or equal to the partitions total.

<details><summary>Show Answer</summary>
Correct Answer: B. Efficient pruning means fewer partitions are scanned than exist in total, since irrelevant partitions are skipped.
</details>

---

### Question 444
Which clustering indicator will show if a large table in Snowflake will benefit from explicitly defining a clustering key?
- A. Percentage
- B. Depth
- C. Ratio
- D. Total partition count

<details><summary>Show Answer</summary>
Correct Answer: B. Average clustering depth is the key indicator — a higher depth suggests the table would benefit from a defined clustering key.
</details>

---

### Question 445
Which file format is MOST performant in Snowflake for data loading?
- A. Parquet
- B. CSV
- C. ORC
- D. JSON

<details><summary>Show Answer</summary>
Correct Answer: B. Delimited flat files (CSV) load fastest because Snowflake can split and parallelize them efficiently across compute resources; columnar formats like Parquet/ORC are better suited for query performance after loading.
</details>

---

### Question 446
What is to be expected when sharing worksheets in Snowsight?
- A. Worksheets can be shared with users that are internal or external to any organization.
- B. To run a shared worksheet a user must be granted the role used in the worksheet session context.
- C. Snowflake allows users to view and refresh results but not to edit shared worksheets.
- D. Snowsight offers different sharing permissions at the worksheet, folder, and dashboard level.

<details><summary>Show Answer</summary>
Correct Answer: B. A recipient needs the appropriate role granted to them in order to successfully run a worksheet shared with them (sharing is limited to users within the same account, and both view/edit access levels can be granted).
</details>

---

### Question 447
Which Snowflake objects track DML changes made to tables, like inserts, updates, and deletes?
- A. Pipes
- B. Streams
- C. Tasks
- D. Procedures

<details><summary>Show Answer</summary>
Correct Answer: B. Streams provide change data capture (CDC) by tracking DML changes on a source table.
</details>

---

### Question 448
Which table type is automatically deleted after a session is closed and has no Fail-safe or Time Travel cost?
- A. Temporary
- B. Transient
- C. Permanent
- D. External

<details><summary>Show Answer</summary>
Correct Answer: A. Temporary tables exist only for the session and have no Fail-safe period (Time Travel is limited to 0 or 1 day).
</details>

---

### Question 449
Which constraint type is enforced in Snowflake from the ANSI SQL standard?
- A. UNIQUE
- B. PRIMARY KEY
- C. FOREIGN KEY
- D. NOT NULL

<details><summary>Show Answer</summary>
Correct Answer: D. Snowflake supports UNIQUE, PRIMARY KEY, and FOREIGN KEY constraints, but they are informational only and not enforced. NOT NULL is the only constraint type that is actually enforced.
</details>

---

### Question 450
Which function or view is used to profile warehouse credit usage?
- A. WAREHOUSE_CREDIT_USAGE
- B. QUERY_HISTORY
- C. ACCOUNT_USAGE
- D. WAREHOUSE_METERING_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: D. WAREHOUSE_METERING_HISTORY (in ACCOUNT_USAGE or via a table function) reports credit usage per warehouse over time.
</details>

---

### Question 451
What is a characteristic of the Snowflake query profiler?
- A. It can provide statistics on a maximum number of queries per week.
- B. It provides a graphic representation of the main components of the query processing.
- C. It provides detailed statistics about which queries are using the greatest number of compute resources.
- D. It can be used by third-party software using the query profiler API.

<details><summary>Show Answer</summary>
Correct Answer: B. Query Profile provides a visual, graphical breakdown of each query's execution plan and processing steps.
</details>

---

### Question 452
A Snowflake user wants to share transactional data with retail suppliers. However, some of the suppliers do not use Snowflake. According to best practice, what should the user do? (Choose two.)
- A. Provide each non-Snowflake supplier with their own reader account.
- B. Deploy a single account to be shared by all of the non-Snowflake suppliers.
- C. Create an ETL pipeline that uses select and inserts statements from the source to the target supplier accounts.
- D. Use a data share for suppliers in the same cloud region and a replicated proxy share for other cloud deployments.
- E. Unload the shared transactional data to an External Stage and use Cloud Storage utilities to reload the suppliers' systems.

<details><summary>Show Answer</summary>
Correct Answer: A, D. Non-Snowflake consumers should each get their own reader account, and shares should be used directly within the same region/cloud, replicating as needed for cross-region/cloud consumers.
</details>

---

### Question 453
Which statement about data sharing is true?
- A. Accounts can share with other accounts regardless of their Snowflake edition, without requiring help from Snowflake Support.
- B. Data sharing can cross regions, but not cloud providers.
- C. The Data Consumer can only see objects in the Data Provider's source database that have been explicitly added to the share.
- D. A Data Provider can only share with other Snowflake customers.

<details><summary>Show Answer</summary>
Correct Answer: C. Consumers can only access the specific objects a provider has explicitly granted into the share — nothing else in the source database is visible.
</details>

---

### Question 454
Which command is used to load files into an internal stage within Snowflake?
- A. PUT
- B. COPY INTO
- C. TRANSFER
- D. INSERT

<details><summary>Show Answer</summary>
Correct Answer: A. PUT uploads local files to an internal stage (COPY INTO then loads staged files into a table).
</details>

---

### Question 455
Which object type is granted permissions for reading a table?
- A. User
- B. Role
- C. Attribute
- D. Schema

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake uses RBAC — privileges are granted to roles, and roles are granted to users, not the other way around.
</details>

---

### Question 456
What is the default value in the Snowflake Web Interface (UI) for auto suspending a Virtual Warehouse?
- A. 1 minute
- B. 5 minutes
- C. 10 minutes
- D. 15 minutes

<details><summary>Show Answer</summary>
Correct Answer: C. The Snowsight default for AUTO_SUSPEND when creating a new warehouse is 10 minutes (600 seconds).
</details>

---

### Question 457
Several users are using the same virtual warehouse. The users report that the queries are running slowly, and that many queries are being queued. What is the recommended way to resolve this issue?
- A. Reduce the warehouse STATEMENT_TIMEOUT_IN_SECONDS parameter.
- B. Reduce the warehouse AUTO_SUSPEND parameter.
- C. Increase the warehouse MAX_CONCURRENCY_LEVEL parameter.
- D. Increase the warehouse MAX_CLUSTER_COUNT parameter.

<details><summary>Show Answer</summary>
Correct Answer: D. Enabling/increasing multi-cluster scaling (MAX_CLUSTER_COUNT) allows additional clusters to spin up automatically to absorb concurrent load and reduce queuing.
</details>

---

### Question 458
Which data types are valid in Snowflake? (Choose two.)
- A. BLOB
- B. Geography
- C. XML
- D. CLOB
- E. Variant

<details><summary>Show Answer</summary>
Correct Answer: B, E. GEOGRAPHY (and GEOMETRY) and VARIANT are valid Snowflake data types; BLOB, CLOB, and XML are not standalone Snowflake data types (XML-formatted data is stored as VARIANT).
</details>

---

### Question 459
What happens when the size of a virtual warehouse is changed?
- A. Queries that are running on the current warehouse are not impacted.
- B. Queries that are running on the current warehouse configuration are aborted and have to be resubmitted by the user.
- C. Queries that are running on the current warehouse configuration are aborted and are automatically resubmitted.
- D. Queries that are running on the current warehouse configuration are moved to the new configuration and finished.

<details><summary>Show Answer</summary>
Correct Answer: A. Resizing does not affect currently executing statements; new resources only apply to queued and future statements.
</details>

---

### Question 460
How often are encryption keys automatically rotated by Snowflake?
- A. 30 Days
- B. 60 Days
- C. 90 Days
- D. 365 Days

<details><summary>Show Answer</summary>
Correct Answer: A. Snowflake-managed keys (Account Master Keys, Table Master Keys, etc.) are automatically rotated every 30 days. Verified current as of July 2026.
</details>

---

### Question 461
As a best practice, all custom roles should be granted to which system-defined role?
- A. ACCOUNTADMIN
- B. ORGADMIN
- C. SECURITYADMIN
- D. SYSADMIN

<details><summary>Show Answer</summary>
Correct Answer: D. Best practice is to grant custom (functional) roles up to SYSADMIN, keeping object/warehouse administration separate from account-level administration.
</details>

---

### Question 462
Which Snowflake object can be accessed in the FROM clause of a query, returning a set of rows having one or more columns?
- A. A User-Defined Table Function
- B. A Scalar User-Defined Function (UDF)
- C. A Stored procedure
- D. A task

<details><summary>Show Answer</summary>
Correct Answer: A. A User-Defined Table Function (UDTF) returns a set of rows and can be referenced in a FROM clause (a scalar UDF returns only a single value).
</details>

---

### Question 463
How are micro-partitions typically generated in Snowflake?
- A. Automatically
- B. ORDER BY
- C. PARTITION BY
- D. GROUP BY

<details><summary>Show Answer</summary>
Correct Answer: A. Micro-partitioning is fully automatic based on the natural ingestion order of data — no manual partitioning syntax is required.
</details>

---

### Question 464
What does Snowflake recommend regarding database object ownership? (Choose two.)
- A. Create objects with ACCOUNTADMIN and do not reassign ownership.
- B. Create objects with SYSADMIN.
- C. Create with SECURITYADMIN to ease granting of privileges later.
- D. Create objects with a custom role and grant this role to SYSADMIN.
- E. Use only managed access schemas for objects owned by ACCOUNTADMIN.

<details><summary>Show Answer</summary>
Correct Answer: B, D. Snowflake recommends creating objects using SYSADMIN or a custom role that is itself granted to SYSADMIN — keeping ACCOUNTADMIN reserved for account-level administration only.
</details>

---

### Question 465
Other than ownership, what privileges does a user need to view and modify resource monitors in Snowflake? (Choose two.)
- A. ALTER
- B. MONITOR
- C. MODIFY
- D. CREATE
- E. DROP

<details><summary>Show Answer</summary>
Correct Answer: B, C. MONITOR allows viewing a resource monitor's details, while MODIFY allows changing its configuration.
</details>

---

### Question 466
What technique does Snowflake recommend for determining which virtual warehouse size to select?
- A. Always start with an X-Small and increase the size if the query does not complete in 2 minutes.
- B. Experiment by running the same queries against warehouses of different sizes.
- C. Use the default size Snowflake chooses.
- D. Use X-Large or above for tables larger than 1 GB.

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake recommends empirically testing the same query workload on different warehouse sizes to find the best fit.
</details>

---

### Question 467
Which command should be used when loading many flat files into a single table?
- A. PUT
- B. INSERT
- C. COPY INTO
- D. MERGE

<details><summary>Show Answer</summary>
Correct Answer: C. COPY INTO is the standard bulk-loading command for moving staged flat files into a table.
</details>

---

### Question 468
How can a Snowflake user share data with another user who does not have a Snowflake account?
- A. Share the data by implementing User-Defined Functions (UDFs).
- B. Create a reader account and create a share of the data.
- C. Grant the READER privilege to the database that is going to be shared.
- D. Move the Snowflake account to a region where data sharing is enabled.

<details><summary>Show Answer</summary>
Correct Answer: B. A reader account lets a provider extend Snowflake access to a consumer who does not have their own Snowflake account.
</details>

---

### Question 469
Which semi-structured data formats can be loaded into Snowflake with a COPY command? (Choose two.)
- A. CSV
- B. EDI
- C. HTML
- D. ORC
- E. XML

<details><summary>Show Answer</summary>
Correct Answer: D, E. Supported semi-structured formats for COPY INTO include JSON, Avro, ORC, Parquet, and XML (CSV is structured, not semi-structured; EDI and HTML are not supported).
</details>

---

### Question 470
Which statements reflect valid commands using secondary roles? (Choose two.)
- A. USE SECONDARY ROLES RESUME
- B. USE SECONDARY ROLES SUSPEND
- C. USE SECONDARY ROLES ALL
- D. USE SECONDARY ROLES ADD [Role Name]
- E. USE SECONDARY ROLES NONE

<details><summary>Show Answer</summary>
Correct Answer: C, E. USE SECONDARY ROLES only accepts ALL or NONE as valid arguments — you cannot add individual roles to the secondary roles list.
</details>

---

### Question 471
How long is a query visible in the Query History page in the Snowflake Web Interface (UI)?
- A. 60 minutes
- B. 24 hours
- C. 14 days
- D. 30 days

<details><summary>Show Answer</summary>
Correct Answer: C. The Snowsight Query History page displays queries executed over the last 14 days. Verified current as of July 2026.
</details>

---

### Question 472
Two users share a virtual warehouse. When one of the users loads data, the other one experiences performance issues while querying data. How does Snowflake recommend resolving this issue?
- A. Scale up the existing warehouse.
- B. Create separate warehouses for each user.
- C. Create separate warehouses for each workload.
- D. Stop loading and querying data at the same time.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowflake recommends isolating different workload types (e.g., loading vs. querying) onto separate warehouses to avoid resource contention.
</details>

---

### Question 473
What is a feature of a stored procedure in Snowflake?
- A. They can be created as secure and hide the underlying metadata from all users.
- B. They can only access tables from a single database.
- C. They can contain a single statement.
- D. They can be created to run with a caller's rights or an owner's rights.

<details><summary>Show Answer</summary>
Correct Answer: D. Stored procedures can be defined with EXECUTE AS CALLER or EXECUTE AS OWNER, controlling whose privileges are used at runtime.
</details>

---

### Question 474
Which view will return users who have queried a table?
- A. SNOWFLAKE.ACCOUNT_USAGE.COLUMNS
- B. SNOWFLAKE.ACCOUNT_USAGE.VIEWS
- C. SNOWFLAKE.ACCOUNT_USAGE.ACCESS_HISTORY
- D. SNOWFLAKE.ACCOUNT_USAGE.OBJECT_DEPENDENCIES

<details><summary>Show Answer</summary>
Correct Answer: C. ACCESS_HISTORY records which users read from or wrote to specific tables and columns.
</details>

---

### Question 475
Why do Snowflake's virtual warehouses have scaling policies?
- A. To help save storage costs
- B. To help increase the performance of serverless computing features
- C. To help control the credits consumed by a multi-cluster warehouse running in autoscale mode
- D. To help control the credits consumed by a multi-cluster warehouse running in maximized mode

<details><summary>Show Answer</summary>
Correct Answer: C. Scaling policies (Standard vs. Economy) govern how aggressively a multi-cluster warehouse in Auto-scale mode starts/stops additional clusters, balancing performance against credit consumption.
</details>

---

### Question 476
Where can a Snowflake user find the query history in Snowsight?
- A. Admin
- B. Activity
- C. Compute
- D. Data

<details><summary>Show Answer</summary>
Correct Answer: B. ⚠ Updated: In current Snowsight navigation, Query History is found under the **Monitoring** menu rather than "Activity" (the "Activity" label was used in an earlier version of Snowsight's navigation). Of the given options, "Activity" remains the closest legacy match, but be aware the current UI labels this section "Monitoring."
</details>

---

### Question 477
What is SnowSQL?
- A. Snowflake's new user interface where users can visualize data into charts and dashboards.
- B. Snowflake's proprietary extension of the ANSI SQL standard, including built-in keywords and system functions.
- C. Snowflake's command line client built on the Python Connector which is used to connect to Snowflake and execute SQL.
- D. Snowflake's library that provides a programming interface for processing data on Snowflake without moving it to the system where the application code resides.

<details><summary>Show Answer</summary>
Correct Answer: C. SnowSQL is the command-line client, built on the Python Connector, used to execute SQL and perform DDL/DML operations against Snowflake.
</details>

---

### Question 478
The following SQL statements have been executed:
`CREATE SEQUENCE seq_01;`
`SELECT seq_01.nextval;`
`SELECT seq_01.nextval;`
What will be the output of the last select statement?
- A. 0
- B. 1
- C. 2
- D. 3

<details><summary>Show Answer</summary>
Correct Answer: C. By default, a new sequence starts at 1 and increments by 1, so the first NEXTVAL call returns 1 and the second returns 2.
</details>

---

### Question 479
Which statement is true of Cloning?
- A. It increases storage costs as cloning a table requires storing its data twice.
- B. A cloned table includes the load history of the original.
- C. It is licensed as an additional Snowflake feature.
- D. All micro-partitions between the original and cloned tables are fully shared.

<details><summary>Show Answer</summary>
Correct Answer: D. Zero-copy cloning shares the same underlying micro-partitions initially; storage costs are only incurred once data diverges (no additional cost at clone time, and it is a native, unlicensed feature).
</details>

---

### Question 480
A Snowflake user has been granted the CREATE DATA EXCHANGE LISTING privilege with their role. Which tasks can this user now perform on the Data Exchange? (Choose two.)
- A. Rename listings
- B. Delete provider profiles
- C. Modify listing properties
- D. Modify incoming listing access requests
- E. Submit listings

<details><summary>Show Answer</summary>
Correct Answer: C, E. This privilege allows a user to create/submit new listings and modify listing properties.
</details>

---

### Question 481
Which parameter prevents streams on tables from becoming stale?
- A. MAX_DATA_EXTENSION_TIME_IN_DAYS
- B. DATA_RETENTION_TIME_IN_DAYS
- C. LOCK_TIMEOUT
- D. STALE_AFTER

<details><summary>Show Answer</summary>
Correct Answer: A. MAX_DATA_EXTENSION_TIME_IN_DAYS extends a table's data retention period as needed to keep dependent streams from becoming stale.
</details>

---

### Question 482
If a virtual warehouse runs for 30 seconds after it is provisioned, how many seconds will the customer be billed for?
- A. 30 seconds
- B. 60 seconds
- C. 121 seconds
- D. 1 hour

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake bills a 60-second minimum each time a warehouse starts, then per-second thereafter. Verified current as of July 2026.
</details>

---

### Question 483
When should a stored procedure be created with caller's rights?
- A. When the caller needs to be prevented from viewing the source code of the stored procedure
- B. When the caller needs to run a statement that could not execute outside of the stored procedure
- C. When the stored procedure needs to run with the privileges of the role that called the stored procedure
- D. When the stored procedure needs to operate on objects that the caller does not have privileges on

<details><summary>Show Answer</summary>
Correct Answer: C. Caller's rights procedures execute using the privileges of the role that called them, rather than the owner's privileges.
</details>

---

### Question 484
What JavaScript delimiters are available in Snowflake stored procedures? (Choose two.)
- A. Double quote ("")
- B. Single quote ('')
- C. Forward slash (//)
- D. Double backslash (\)
- E. Double dollar sign ($$)

<details><summary>Show Answer</summary>
Correct Answer: B, E. A JavaScript procedure body can be delimited with single quotes or double dollar signs.
</details>

---

### Question 485
What type of function can be used to estimate the approximate number of distinct values from a table that has trillions of rows?
- A. MD5
- B. Window
- C. External
- D. HyperLogLog (HLL)

<details><summary>Show Answer</summary>
Correct Answer: D. HyperLogLog functions (e.g., APPROX_COUNT_DISTINCT) provide fast, memory-efficient approximate distinct counts on very large datasets.
</details>

---

### Question 486
Which Data Definition Language (DDL) commands are supported by Snowflake to manage tags? (Choose two.)
- A. ALTER TAG
- B. DESCRIBE TAG
- C. CREATE TAG
- D. GRANT [privilege] TO TAG
- E. DROP TAG

<details><summary>Show Answer</summary>
Correct Answer: A, C. CREATE TAG and ALTER TAG are core DDL commands for managing tags (Snowflake also supports DROP TAG and SHOW TAGS, but of the listed options A and C are the intended pair).
</details>

---

### Question 487
What Snowflake objects can be added to a share? (Choose two.)
- A. Internal Stages
- B. Tables
- C. Stored procedures
- D. Users
- E. Secure Views

<details><summary>Show Answer</summary>
Correct Answer: B, E. Shares can include tables, secure views, and secure UDFs — internal stages, stored procedures, and users cannot be shared.
</details>

---

### Question 488
A Query Profile shows a UnionAll operator with an extra Aggregate operator on top. What does this signify?
- A. Exploding joins
- B. Inefficient pruning
- C. UNION without ALL
- D. Queries that are too large to fit in memory

<details><summary>Show Answer</summary>
Correct Answer: C. When a UNION (without ALL) is used, Snowflake performs a UnionAll followed by an Aggregate operator to deduplicate the results.
</details>

---

### Question 489
Which data governance control has Snowflake embedded in the application?
- A. Row access policies
- B. Credit computation
- C. Data storage
- D. Role-based access control

<details><summary>Show Answer</summary>
Correct Answer: A. Row access policies are a native Snowflake data governance feature controlling which rows a user can see.
</details>

---

### Question 490
What actions does the use of the PUT command do automatically? (Choose two.)
- A. It creates a file format object.
- B. It uses the last stage created.
- C. It compresses all files using GZIP.
- D. It encrypts the file data.
- E. It creates an empty target table.

<details><summary>Show Answer</summary>
Correct Answer: C, D. By default, PUT automatically compresses files with GZIP and encrypts them before uploading to a stage (both behaviors can be overridden with parameters).
</details>

---

### Question 491
Which command should a Snowflake user execute to load data into a table?
- A. COPY INTO mytable purge_mode = TRUE;
- B. COPY INTO mytable FROM @stage;
- C. COPY INTO mytable file_format = (format_name);
- D. COPY INTO my_table validation_mode = RETURN_ERRORS;

<details><summary>Show Answer</summary>
Correct Answer: B. COPY INTO mytable FROM @stage is valid, complete syntax for loading data (the other options reference invalid parameter names or are missing the required FROM clause).
</details>

---

### Question 492
Which function returns the URL of a stage using the stage name as the input?
- A. GET_STAGE_URL
- B. GENERATE_PRESIGNED_URL
- C. GET_STAGE_LOCATION
- D. GET_STAGE_FILE_URL

<details><summary>Show Answer</summary>
Correct Answer: C. GET_STAGE_LOCATION returns the cloud storage URL for a given stage.
</details>

---

### Question 493
Which is the MAXIMUM number of clusters that can be provisioned with a multi-cluster virtual warehouse?
- A. 1
- B. 5
- C. 10
- D. 100

<details><summary>Show Answer</summary>
Correct Answer: C. A multi-cluster warehouse supports a maximum of 10 clusters. Verified current as of July 2026.
</details>

---

### Question 494
Which Snowflake table supports unstructured data?
- A. Directory
- B. Transient
- C. Temporary
- D. Permanent

<details><summary>Show Answer</summary>
Correct Answer: A. ⚠ Updated: This question's framing is slightly outdated. Snowflake does not have a distinct "Directory table" *table type* — a directory table is metadata associated with an internal/external **stage** (enabled via `DIRECTORY = (ENABLE = TRUE)`) that catalogs unstructured files, not a standalone table type alongside Transient/Temporary/Permanent. Of the listed options, "Directory" is still the intended answer since it is the mechanism Snowflake uses to track and query unstructured files, but it is technically a stage property/table, not a table storage type.
</details>

---

### Question 495
When unloading data, which file format preserves the data values for floating-point number columns?
- A. CSV
- B. XML
- C. JSON
- D. Parquet

<details><summary>Show Answer</summary>
Correct Answer: D. Parquet preserves native floating-point precision, whereas CSV/JSON convert values to text representations that can lose precision.
</details>

---

### Question 496
Which virtual warehouse privilege is required to view a load-monitoring chart?
- A. MONITOR
- B. MODIFY
- C. OPERATE
- D. USAGE

<details><summary>Show Answer</summary>
Correct Answer: A. MONITOR privilege on a warehouse allows viewing its metrics, including load-monitoring charts.
</details>

---

### Question 497
Which use case will always cause an exploding join in Snowflake?
- A. A query that has more than 10 left outer joins.
- B. A query that is using a UNION without an ALL.
- C. A query that has not specified join criteria for tables.
- D. A query that has requested too many columns of data.

<details><summary>Show Answer</summary>
Correct Answer: C. Missing join criteria produces a cartesian product, causing row counts to explode.
</details>

---

### Question 498
How many resource monitors can be applied to a single virtual warehouse?
- A. Zero
- B. One
- C. Eight
- D. Unlimited

<details><summary>Show Answer</summary>
Correct Answer: B. A given warehouse can be assigned to only one resource monitor at a time (though one resource monitor can cover multiple warehouses).
</details>

---

### Question 499
What are the main differences between the account usage views and the information schema views? (Choose two.)
- A. No active warehouse is needed to query account usage views but one is needed to query information schema views.
- B. Account usage views do not contain data about tables but information schema views do.
- C. Account usage views contain dropped objects, information schema views do not.
- D. Data retention for account usage views is 1 year but is 7 days to 6 months for information schema views, depending on the view.
- E. Information schema views are read-only but account usage views are not.

<details><summary>Show Answer</summary>
Correct Answer: C, D. ACCOUNT_USAGE retains data for 365 days and includes dropped objects, while INFORMATION_SCHEMA has shorter, view-dependent retention (typically 7 days to 6 months) and excludes dropped objects.
</details>

---

### Question 500
Which file function generates a URL with access to a file on a stage without the need for authentication and authorization?
- A. BUILD_STAGE_FILE_URL
- B. GET_STAGE_LOCATION
- C. GET_PRESIGNED_URL
- D. BUILD_SCOPED_FILE_URL

<details><summary>Show Answer</summary>
Correct Answer: C. GET_PRESIGNED_URL generates a temporary URL that grants access to a staged file without requiring the requester to separately authenticate to Snowflake.
</details>

---



====================================================================================================
# SnowPro_501-600.md
====================================================================================================

# SnowPro Core Practice Questions (501–600)

---

### Question 501
Which view can be used to determine if a table has frequent row updates or deletes?

- A. TABLES
- B. TABLE_STORAGE_METRICS
- C. DATABASE_USAGE
- D. STORAGE_USAGE

<details><summary>Show Answer</summary>
Correct Answer: B. TABLE_STORAGE_METRICS reports row counts, deleted rows, and other storage details that reveal update/delete activity.
</details>

---

### Question 502
How does the Snowflake search optimization service improve query performance?

- A. It improves the performance of range searches.
- B. It defines different clustering keys on the same source table.
- C. It improves the performance of all queries running against a given table.
- D. It improves the performance of equality point lookup searches.

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 503
How is unstructured data retrieved from data storage?

- A. SQL functions like the GET command can be used to copy the unstructured data to a location on the client.
- B. SQL functions can be used to create different types of URLs pointing to the unstructured data. These URLs can be used to download the data to a client.
- C. SQL functions can be used to retrieve the data from the query results cache. When the query results are output to a client, the unstructured data will be output to the client as files.
- D. SQL functions can call on different web extensions designed to display different types of files as a web page. The web extensions will allow the files to be downloaded to the client.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 504
What is the recommended way to obtain a cloned table with the same grants as the source table?

- A. Clone the table with the COPY GRANTS command.
- B. Use an ALTER TABLE command to copy the grants.
- C. Clone the schema then drop the unwanted tables.
- D. Create a script to extract grants and apply them to the cloned table.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 505
What common query issues can be identified using the Query Profile? (Choose two.)

- A. Data Classification
- B. Exploding joins
- C. Unions
- D. Inefficient pruning
- E. Data masking

<details><summary>Show Answer</summary>
Correct Answer: B, D
</details>

---

### Question 506
What is used to extract the content of PDF files stored in Snowflake Stages?

- A. FLATTEN function
- B. Window function
- C. HyperLogLog (HLL) function
- D. Java User-Defined Function (UDF)

<details><summary>Show Answer</summary>
Correct Answer: D (a Java UDF using a library such as Apache PDFBox is the traditional approach).

**⚠ Updated:** Snowflake now offers a native, no-code option: the Cortex **AI_PARSE_DOCUMENT** function (formerly PARSE_DOCUMENT), which extracts text and layout from PDF, DOCX, and other document types directly from a stage using SQL — no custom UDF required. The Java UDF approach in option D is still valid and is likely the exam's intended answer, but current Snowflake documentation now recommends AI_PARSE_DOCUMENT for this task.
</details>

---

### Question 507
What is used to extract the content of PDF files stored in Snowflake stages?

- A. FLATTEN function
- B. Window function
- C. HyperLogLog (HLL) function
- D. Java User-Defined Function (UDF)

<details><summary>Show Answer</summary>
Correct Answer: D (duplicate of Question 506 — see note above about AI_PARSE_DOCUMENT).
</details>

---

### Question 508
What happens when a database is cloned?

- A. It does not retain privileges granted on the source.
- B. It replicates all granted privileges on the corresponding source objects.
- C. It replicates all granted privileges on the corresponding child objects.
- D. It replicates all granted privileges on the corresponding child schema objects.

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 509
What does a Query Profile provide in Snowflake?

- A. A multi-step query that displays each processing step in the same panel.
- B. A pre-computed data set derived from a query specification and stored for later use.
- C. A graphical representation of the main components of the processing plan for a query.
- D. A collapsible panel in the operator tree pane that lists nodes by execution time in descending order for a query.

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 510
When executing a COPY INTO command, performance can be negatively affected by using which optional parameter on a large number of files?

- A. FILE_FORMAT
- B. PATTERN
- C. VALIDATION_MODE
- D. FILES

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 511
Which URL type should be used to get a permanent URL to a file in a stage?

- A. File URL
- B. Pre-signed URL
- C. Saved URL
- D. Scoped URL

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 512
Which operation will produce an error in Snowflake?

- A. Inserting duplicate values into a PRIMARY KEY column
- B. Inserting a NULL into a column with a NOT NULL constraint
- C. Inserting duplicate values into a column with a UNIQUE constraint
- D. Inserting a value to a FOREIGN KEY column that does not match a value in the column referenced

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake does not enforce PRIMARY KEY, UNIQUE, or FOREIGN KEY constraints by default (they are informational only); NOT NULL is the only one enforced.
</details>

---

### Question 513
How are URLs that access unstructured data in external stages retrieved?

- A. Using the navigation menu
- B. By querying a directory table
- C. By creating an external function
- D. By using the INFORMATION_SCHEMA

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 514
What is the Snowflake multi-clustering feature for virtual warehouses used for?

- A. To improve the data unloading process to the cloud
- B. To improve data loading from very large data sets
- C. To improve concurrency for users and queries
- D. To speed up slow or stalled queries

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 515
Which features could be used to improve the performance of queries that return a small subset of rows from a large table? (Choose two.)

- A. Search optimization service
- B. Automatic clustering
- C. Row access policies
- D. Multi-cluster warehouses
- E. Secure views

<details><summary>Show Answer</summary>
Correct Answer: A, B
</details>

---

### Question 516
Which command would return an empty sample?

- A. select * from testtable sample
- B. select * from testtable sample (0);
- C. select * from testtable sample (null);
- D. select * from testtable sample (none);

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 517
Which Snowflake function should be used to unload relational data to JSON?

- A. TO_JSON()
- B. OBJECT_CONSTRUCT()
- C. PARSE_JSON()
- D. JSON_EXTRACT()

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 518
Floating point values are truncated when unloaded to which file format?

- A. ORC
- B. CSV
- C. Avro
- D. Parquet

<details><summary>Show Answer</summary>
Correct Answer: B. Floating-point columns unloaded to CSV (or JSON) are truncated to approximately (15,9) precision; Parquet is not affected.
</details>

---

### Question 519
Which levels can apply network policies? (Choose two.)

- A. Account
- B. Database
- C. Role
- D. Schema
- E. User

<details><summary>Show Answer</summary>
Correct Answer: A, E
</details>

---

### Question 520
What causes objects in a data Share to become unavailable to a consumer account?

- A. The parameter in the consumer account is set to 0.
- B. The consumer account runs the GRANT IMPORTED PRIVILEGES command on the data share every 24 hours.
- C. The objects in the data share are being deleted and the grant pattern is not re-applied.
- D. The consumer account acquires the data share through a private data exchange.

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 521
How can an administrator view updates (for example, SCIM API requests) sent to Snowflake by the identity provider?

- A. ACCESS_HISTORY
- B. LOAD_HISTORY
- C. QUERY_HISTORY
- D. REST_EVENT_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: D. The REST_EVENT_HISTORY table function (in INFORMATION_SCHEMA) returns SCIM REST API requests made to Snowflake over a specified time interval.
</details>

---

### Question 522
A Snowflake user is writing a User-Defined Function (UDF) with some unqualified object names. How will those object names be resolved during execution?

- A. Snowflake will resolve them according to the SEARCH_PATH parameter.
- B. Snowflake will only check the schema the UDF belongs to.
- C. Snowflake will first check the current schema, and then the schema the previous query used.
- D. Snowflake will first check the current schema, and then the PUBLIC schema of the current database.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 523
Why should a user select the economy scaling policy for a multi-cluster warehouse?

- A. To prevent/minimize query queuing.
- B. To increase performance of the clusters.
- C. To reduce queuing for concurrent user queries.
- D. To conserve credits by keeping running clusters fully loaded.

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 524
What MINIMUM privilege is required on the external Stage for any role in the GET REST API to access unstructured data files using a file URL?

- A. READ
- B. OWNERSHIP
- C. USAGE
- D. WRITE

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 525
Which view in SNOWFLAKE.ACCOUNT_USAGE shows from which IP address a user connected to Snowflake?

- A. ACCESS_HISTORY
- B. LOGIN_HISTORY
- C. SESSIONS
- D. QUERY_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 526
Snowflake Partner Connect is limited to users with a verified email address and which role?

- A. SYSADMIN
- B. SECURITYADMIN
- C. ACCOUNTADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 527
What unit of storage supports efficient query processing in Snowflake?

- A. Blobs
- B. JSON
- C. Block Storage
- D. Micro-partitions

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 528
What is the difference between a stored procedure and a User-Defined Function (UDF)?

- A. Stored procedures can perform database operations while UDFs cannot.
- B. Returning a value is required in a stored procedure while returning values in a UDF is optional.
- C. Values returned by a stored procedure can be used directly in a SQL statement while the values returned by a UDF cannot.
- D. Multiple stored procedures can be called as part of a single executable statement while a single SQL statement can only call one UDF.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 529
Which URL type does Snowflake recommend to use when providing unstructured data to other accounts through a Share?

- A. File URL
- B. Pre-signed URL
- C. Scoped URL
- D. Direct URL

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 530
What is the MAXIMUM Time Travel retention period for a transient table?

- A. 0 days
- B. 1 day
- C. 7 days
- D. 90 days

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 531
What is the advantage of using a reader account?

- A. It can be used by a client that does not have a Snowflake account.
- B. It is read-only and prevents the shared data from being updated by the provider.
- C. It can be connected to a Snowflake account in a different region.
- D. It provides limited access to the data share and is therefore cheaper for the data provider.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 532
What command is used to export or unload data from Snowflake?

- A. PUT @mystage
- B. GET @mystage
- C. COPY INTO @myStage
- D. INSERT INTO @mystage

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 533
A Snowflake user wants to share data with someone who does not have a Snowflake account. How can the Snowflake user share the data?

- A. Use the Snowflake Marketplace.
- B. Create a reader account.
- C. Create a consumer account.
- D. Use a Snowflake share.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 534
A user wants to add additional privileges to the system-defined roles for their virtual warehouse. How does Snowflake recommend they accomplish this?

- A. Grant the additional privileges to a custom role, then grant the custom role to the system role.
- B. Grant the additional privileges directly to the ACCOUNTADMIN role.
- C. Grant the additional privileges directly to the SYSADMIN role.
- D. Grant the additional privileges directly to the ORGADMIN role.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 535
How does Snowflake store a table's underlying data? (Choose two.)

- A. Columnar file format
- B. Micro-partitions
- C. Text file format
- D. Uncompressed
- E. User-defined partitions

<details><summary>Show Answer</summary>
Correct Answer: A, B
</details>

---

### Question 536
What is the MAXIMUM number of days a Snowflake-managed encryption key can be used before it gets automatically rotated?

- A. 1 day
- B. 14 days
- C. 30 days
- D. 120 days

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 537
Which user object property requires contacting Snowflake Support in order to set a value for it?

- A. DISABLED
- B. DEFAULT_ROLE
- C. MINS_TO_BYPASS_MFA
- D. PASSWORD

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 538
How does Snowflake handle the bulk unloading of data into single or multiple files?

- A. It assigns each unloaded data file a unique name.
- B. It uses the PUT command to download the data by default.
- C. It uses COPY INTO for bulk unloading where the default option is SINGLE = TRUE.
- D. It uses COPY INTO [location] to copy the data from a table into one or more files in an external stage.

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 539
What information is included in the display in the Query Profile? (Choose two.)

- A. Index hints used in query
- B. Credit usage details
- C. Clustering keys details
- D. Details and statistics for the overall query
- E. Graphical representation of the query processing plan

<details><summary>Show Answer</summary>
Correct Answer: D, E
</details>

---

### Question 540
A Snowflake user wants to optimize performance for a query that queries only a small number of rows in a table. The rows require significant processing. The data in the table changes frequently. What should the user do?

- A. Add a clustering key to the table.
- B. Add the search optimization service to the table.
- C. Create a materialized view based on the query.
- D. Enable the query acceleration service for the virtual warehouse.

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 541
When using the ALLOW_CLIENT_MFA_CACHING parameter, how long is a cached Multi-Factor Authentication (MFA) token valid for?

- A. 1 hour
- B. 2 hours
- C. 4 hours
- D. 8 hours

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 542
When unloading data, which file formats are supported by the COPY INTO [location] command? (Choose two.)

- A. Avro
- B. JSON
- C. ORC
- D. Parquet
- E. XML

<details><summary>Show Answer</summary>
Correct Answer: B, D. Unloading supports CSV, JSON, and Parquet only — Avro, ORC, and XML are supported for loading but not unloading.
</details>

---

### Question 543
A JSON object is loaded into a column named `data` using a Snowflake variant datatype. The root node of the object is `BIKE`. The child attribute for this node is `BIKEID`. Which statement will allow the user to access BIKEID?

- A. select data_BIKE_ID
- B. select data.BIKE.BIKEID
- C. select data:BIKE.BIKEID
- D. select data::BIKEID

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 544
A custom role owns multiple tables. If this role is dropped from the system, who becomes the owner of these tables?

- A. ACCOUNTADMIN
- B. SYSADMIN
- C. Tables become standalone or orphaned
- D. The role that dropped the custom role.

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 545
Which function produces a lateral view of a VARIANT column?

- A. GET_PATH
- B. FLATTEN
- C. GET
- D. PARSE_JSON

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 546
Snowflake strongly recommends that all users with what type of role be required to use Multi-Factor Authentication (MFA)?

- A. USERADMIN
- B. ACCOUNTADMIN
- C. SECURITYADMIN
- D. SYSADMIN

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 547
What does it mean when the SAMPLE function uses the Bernoulli sampling method?

- A. The data is based on sampling every row with a specific probability.
- B. The data is based on sampling of the entire source data as a block.
- C. The data is based on sampling blocks of the source data.
- D. The data is based on sampling exactly 1000 rows of the source data.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 548
What are characteristics of Snowflake network policies? (Choose two.)

- A. They can be set for any Snowflake Edition.
- B. They can be applied directly to roles.
- C. They restrict or enable specific IP addresses.
- D. They are activated using ALTER DATABASE SQL commands.
- E. They can only be managed using the ORGADMIN role.

<details><summary>Show Answer</summary>
Correct Answer: A, C
</details>

---

### Question 549
Which function should be used to find the query ID of the second query executed in a current session?

- A. SELECT LAST_QUERY_ID()
- B. SELECT QUERY_ID
- C. SELECT LAST_QUERY_ID(-2)
- D. SELECT LAST_QUERY_ID(2)

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 550
How is the hierarchy of database objects organized in Snowflake?

- A. A database consists of one or more schemas. A schema contains tables and views.
- B. A schema consists of one or more databases. A database contains tables and views.
- C. A schema consists of one or more databases. A database contains tables, views, and warehouses.
- D. A database consists of one or more schemas and warehouses. A schema contains tables and views.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 551
Which role can execute the SHOW ORGANIZATION ACCOUNTS command successfully?

- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. ORGADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 552
Which data types in Snowflake are synonymous for FLOAT? (Choose two.)

- A. DECIMAL
- B. DOUBLE
- C. NUMBER
- D. NUMERIC
- E. REAL

<details><summary>Show Answer</summary>
Correct Answer: B, E. FLOAT, FLOAT4, FLOAT8, DOUBLE, DOUBLE PRECISION, and REAL are all synonymous and implemented as 64-bit double-precision floating point in Snowflake.
</details>

---

### Question 553
What ensures that a user with the role SECURITYADMIN can activate a network policy for an individual user?

- A. A role that has been granted the EXECUTE TASK privilege
- B. A role that has been granted the global ATTACH POLICY privilege
- C. Ownership privilege on only the role that created the network policy
- D. Ownership privilege on both the user and the network policy

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 554
Which function can be combined with the COPY command to unload a relational table into a JSON file?

- A. FLATTEN
- B. LISTAGG
- C. OBJECT_CONSTRUCT
- D. PARSE_JSON

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 555
A user needs to MINIMIZE the cost of large tables that are used to store transitory data. The data does not need to be protected against failures because the data can be reconstructed outside of Snowflake. What table type should be used?

- A. Permanent
- B. Transient
- C. Temporary
- D. External

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 556
While loading data from a JSON file, what enables the removal of the outer array structure from the file and loads the records into separate table rows?

- A. FLATTEN
- B. ARRAY_CONSTRUCT
- C. STRIP_OUTER_ARRAY = TRUE
- D. PURGE_ARRAY = TRUE

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 557
Which functions can be used to share unstructured data through a secure view? (Choose two.)

- A. BUILD_SCOPED_FILE_URL
- B. GET_PRESIGNED_URL
- C. BUILD_STAGE_FILE_URL
- D. SYSTEM$AUTHORIZE_PRIVATELINK

<details><summary>Show Answer</summary>
Correct Answer: A, B
</details>

---

### Question 558
Which function will return a row for each object in a VARIANT, OBJECT, or ARRAY column?

- A. CAST
- B. FLATTEN
- C. GET
- D. PARSE_JSON

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 559
What is the MINIMUM size of a table for which Snowflake recommends considering adding a clustering key?

- A. 1 Kilobyte (KB)
- B. 1 Megabyte (MB)
- C. 1 Gigabyte (GB)
- D. 1 Terabyte (TB)

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 560
Using the ALLOWED_VALUES tag property, what is the MAXIMUM number of possible string values for a single tag?

- A. 10
- B. 50
- C. 100
- D. 300

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 561
Which Snowflake table type is only visible to the user who creates it, can have the same name as permanent tables in the same schema, and is dropped at the end of the session?

- A. Temporary
- B. Local
- C. User
- D. Transient

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 562
What is a characteristic of a role in Snowflake?

- A. Roles cannot be granted to other roles.
- B. System-defined roles can be dropped.
- C. Privileges granted to system roles by Snowflake can be revoked.
- D. Privileges on securable objects can be granted to a role.

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 563
What command would a user execute to load unstructured data files into a Snowflake internal stage?

- A. PUT
- B. GET
- C. LIST
- D. COPY INTO

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 564
How do managed access schemas help with data governance?

- A. They log all operations and enable fine-grained auditing.
- B. They provide centralized privilege management with the schema owner.
- C. They enforce identical privileges across all tables and views in a schema.
- D. They require the use of masking and row access policies across every table and view in the schema.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 565
What is the default period of time the Warehouse Activity section provides a graph of Snowsight activity?

- A. 2 hours
- B. 1 week
- C. 14 days (2 weeks)
- D. 1 month

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 566
A Snowflake user wants to unload data from a relational table sized 5 GB using CSV. The extract needs to be as performant as possible. What should they do?

- A. Use Parquet as the unload file format, using Parquet's default compression feature.
- B. Use a regular expression in the stage of the COPY command to restrict parsing time.
- C. Increase the default file size to 5 GB and set SINGLE = true to produce a single file.
- D. Leave the default max file size to 16 MB to take advantage of parallel operations.

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 567
How is the MANAGE GRANTS privilege applied?

- A. Globally
- B. At the database level
- C. At the schema level
- D. At the table level

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 568
What is required for a query execution to be served from the result cache?

- A. The query logic is the same.
- B. The exact SQL text is the same.
- C. The SQL profile is the same.
- D. The virtual warehouse is the same.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 569
Which Snowflake URL type is used by directory tables?

- A. File URL
- B. Pre-signed URL
- C. Scoped URL
- D. Virtual-hosted style

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 570
At which point is data encrypted when using a PUT command?

- A. When it reaches the virtual warehouse
- B. When it gets micro-partitioned
- C. Client-side before it is sent from the user's machine
- D. After it reaches the internal stage

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 571
Which privileges are required for a user to restore a dropped object using UNDROP? (Choose two.)

- A. UPDATE
- B. OWNERSHIP on the object
- C. MODIFY
- D. USAGE
- E. CREATE on the schema

<details><summary>Show Answer</summary>
Correct Answer: B, E
</details>

---

### Question 572
For a virtual warehouse, which parameters are used to calculate the number of credits billed? (Choose two.)

- A. Cache size
- B. Warehouse Size
- C. Number of clusters running
- D. Volume of data processed
- E. Number of queries executed

<details><summary>Show Answer</summary>
Correct Answer: B, C
</details>

---

### Question 573
What happens when the values for both an allowed list and a blocked list are used in a network policy?

- A. Snowflake ignores the first list.
- B. Snowflake applies the blocked list first.
- C. Snowflake applies the allowed list first.
- D. Snowflake throws an error.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 574
What does the orange bar on an operator represent when reviewing the Query Profile?

- A. A percentage of progress of the operator's completion.
- B. The fraction of time that this operator consumed within the query step.
- C. The cost of the operator in terms of the virtual warehouse CPU utilization.
- D. The fraction of data scanned from cache versus remote disk for the operator.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 575
When unloading data from Snowflake, what is the default max file size of each file?

- A. 16 MB
- B. 32 MB
- C. 5 GB
- D. Unlimited

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 576
What is the abbreviated form to get a list of all the files in the user stage?

- A. LIST
- B. LS @~;
- C. LS @usr;
- D. SHOW

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 577
Which features make up Snowflake's column-level security? (Choose two.)

- A. Continuous Data Protection (CDP)
- B. Dynamic Data Masking
- C. External Tokenization
- D. Key pair authentication
- E. Row access policies

<details><summary>Show Answer</summary>
Correct Answer: B, C
</details>

---

### Question 578
Which languages are supported for writing Snowflake UDFs? (Choose two.)

- A. JavaScript
- B. Python
- C. C++
- D. PHP
- E. TypeScript

<details><summary>Show Answer</summary>
Correct Answer: A, B. Snowflake also supports SQL, Java, and Scala for UDFs, but among these options only JavaScript and Python are valid.
</details>

---

### Question 579
What is the MAXIMUM number of days that Snowflake resets the 24-hour retention period for a query result every time the result is used?

- A. 1 day
- B. 14 days
- C. 31 days
- D. 60 days

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 580
There are 300 concurrent users on a production Snowflake account using a single cluster virtual warehouse. The queries are small, but the queuing is high. What is causing this to occur?

- A. The single cluster warehouse is queuing the queries because it cannot process 300 concurrent requests, increasing the overall query execution time.
- B. The warehouse parameter STATEMENT_QUEUED_TIMEOUT_IN_SECONDS is set too low.
- C. The application is not using the latest native ODBC driver.
- D. The queries are not taking advantage of the data cache.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 581
Which Snowflake edition offers the highest level of security for organizations that have the strictest requirements?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: D
</details>

---

### Question 582
What is the MAXIMUM size limit for a record of a VARIANT data type?

- A. 8 MB
- B. 16 MB
- C. 32 MB
- D. 128 MB

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 583
What criteria does Snowflake use to determine the current role when initiating a session? (Choose two.)

- A. If a role was specified as part of the connection and that role has been granted to the Snowflake user, the specified role becomes the current role.
- B. If no role was specified as part of the connection and a default role has been defined for the Snowflake user, that role becomes the current role.
- C. If no role was specified as part of the connection and a default role has not been set for the Snowflake user, the session will not be initiated and the login will fail.
- D. If a role was specified as part of the connection and that role has not been granted to the Snowflake user, it will be ignored and the default role will become the active role.
- E. If a role was specified as part of the connection and that role has not been granted to the Snowflake user, the role is automatically granted and it becomes the current role.

<details><summary>Show Answer</summary>
Correct Answer: A, B
</details>

---

### Question 584
What command should be used to move data from a Snowflake database table into one or more files in an external stage?

- A. GET
- B. COPY INTO
- C. PUT
- D. EXPORT

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 585
How does a Snowflake user reference a directory table created on stage `mystage` in a SQL query?

- A. SELECT * FROM DIRECTORY
- B. SELECT * FROM DIRECTORY(@mystage)
- C. SELECT * FROM TO_TABLE(DIRECTORY @mystage)
- D. SELECT * TABLE(@mystage DIRECTORY)

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 586
Why would a Snowflake user create a secure view instead of a standard view?

- A. The Secure View is only available to end users with the corresponding SECURE_ACCESS property.
- B. End users are unable to see the view definition, and internal optimizations differ with a secure view to protect underlying data.
- C. In a secure view, the underlying data is a separate storage layer with encryption.
- D. Secure views support additional functionality that is not supported for standard views, such as column masking and row level access.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 587
Which command parameter can be added to the COPY command to make it load all files, whether or not the load status of the files is known?

- A. FORCE = TRUE
- B. FORCE = FALSE
- C. PURGE = TRUE
- D. PURGE = FALSE

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 588
How can a Snowflake user improve long-running query performance?

- A. Reduce the virtual warehouse size.
- B. Cluster the underlying table being queried.
- C. Disable the result cache.
- D. Add ORDER BY to the query.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---

### Question 589
Which Snowflake feature allows administrators to identify unused data that may be archived or deleted?

- A. Access History
- B. Data classification
- C. Dynamic Data Masking
- D. Object tagging

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 590
Which SQL commands should be used to write a recursive query if the number of levels is unknown? (Choose two.)

- A. CONNECT BY
- B. LISTAGG
- C. MATCH RECOGNIZE
- D. QUALIFY
- E. WITH RECURSIVE

<details><summary>Show Answer</summary>
Correct Answer: A, E
</details>

---

### Question 591
What information is stored in the ACCESS_HISTORY view?

- A. History of the files that have been loaded into Snowflake.
- B. Names and owners of the roles that are currently enabled in the session.
- C. Query details such as the objects read/modified and the user who executed the query.
- D. Details around the privileges that have been granted for all objects in an account.

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 592
What privilege does a user need in order to receive or request data from the Snowflake Marketplace?

- A. CREATE DATA EXCHANGE LISTING
- B. CREATE SHARE
- C. IMPORT SHARE
- D. IMPORTED PRIVILEGES

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 593
Which Snowflake database object can be shared with other accounts?

- A. Tasks
- B. Pipes
- C. Secure User-Defined Functions (UDFs)
- D. Stored Procedures

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 594
Which identity providers are valid type values for federated authentication on the security integration parameter? (Choose two.)

- A. Identity Access Management (IAM)
- B. Microsoft Active Directory Federation Services (AD FS)
- C. OAuth
- D. Okta
- E. PingFederate

<details><summary>Show Answer</summary>
Correct Answer: B, D
</details>

---

### Question 595
A Snowflake user wants to share data using my_share with account 12345. Which command should be used?

- A. grant usage on account 12345 to share my_share;
- B. grant select on share my_share to account 12345;
- C. alter share my_share add accounts = 12345;
- D. alter account 12345 add share my_share;

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 596
What role is required to use Partner Connect?

- A. ACCOUNTADMIN
- B. ORGADMIN
- C. SECURITYADMIN
- D. SYSADMIN

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 597
How can a Snowflake user configure a virtual warehouse to support over 100 users if their company has Enterprise Edition?

- A. Add additional warehouses and configure them as a pool.
- B. Set the auto-scale to 100.
- C. Use a multi-cluster warehouse.
- D. Use a larger warehouse.

<details><summary>Show Answer</summary>
Correct Answer: C
</details>

---

### Question 598
How is table data compressed in Snowflake?

- A. Each column is compressed as it is stored in a micro-partition.
- B. Each micro-partition is compressed as it is written into cloud storage using GZIP.
- C. The micro-partitions are stored in compressed Cloud Storage and the Cloud Storage handles it.
- D. The text data in a micro-partition is compressed with GZIP but other types are not compressed.

<details><summary>Show Answer</summary>
Correct Answer: A
</details>

---

### Question 599
What will be the output of the below query against the table name gold_data?

`select * from gold_data tablesample (100);`

- A. It will return an empty sample.
- B. It will return a 100 row sample.
- C. It will return the entire table.
- D. It will produce an error message.

<details><summary>Show Answer</summary>
Correct Answer: C. Without the ROWS keyword, the number is interpreted as a percentage probability (Bernoulli sampling); 100% probability returns (statistically) the entire table.
</details>

---

### Question 600
A Snowflake query took 40 minutes to run. The results indicate that 'Bytes spilled to local storage' was a large number. What is the issue and how can it be resolved?

- A. The warehouse is too large. Decrease the size of the warehouse to reduce the spillage.
- B. The warehouse is too small. Increase the size of the warehouse to reduce the spillage.
- C. The Snowflake console has timed-out. Contact Snowflake Support.
- D. The warehouse consists of a single cluster. Use a multi-cluster warehouse to reduce the spillage.

<details><summary>Show Answer</summary>
Correct Answer: B
</details>

---



====================================================================================================
# snowpro_601-700.md
====================================================================================================

# SnowPro Core Practice Questions (601–700)

---

### Question 601
What is the MOST efficient way to load streaming data into Snowflake?

- A. Use the COPY command.
- B. Use Snowpipe.
- C. Use the Data Wizard.
- D. Use tasks and streams.

<details><summary>Show Answer</summary>
Correct Answer: B. Snowpipe enables continuous, micro-batch loading of streaming data via file-based ingestion.

⚠ **Updated:** As of current documentation, Snowflake also offers **Snowpipe Streaming**, which writes rows directly to Snowflake tables without staging files first, offering lower latency and lower cost than classic Snowpipe for row-level streaming use cases. For a file-based streaming scenario (the classic exam framing), Snowpipe (B) remains the best answer among the listed options, but be aware Snowpipe Streaming is the more modern/efficient choice when ingesting rows directly from a streaming source (e.g., Kafka).
</details>

---

### Question 602
Which COPY INTO statement accurately describes how to unload data from a Snowflake table?

- A. The default value for the SINGLE option is set to FALSE.
- B. By default, COPY INTO [location] statements do not separate table data into a set of files.
- C. The OBJECT_CONSTRUCT function can be combined with the COPY command to convert the rows in a relational table to a single VARIANT column.
- D. If the COMPRESSION option is set to TRUE, a file's name can be specified with the appropriate file extension so that the output file can be compressed.

<details><summary>Show Answer</summary>
Correct Answer: C. OBJECT_CONSTRUCT converts relational rows into a single VARIANT column for unloading (e.g., to JSON).
</details>

---

### Question 603
What command is used to download data from a Snowflake stage?

- A. PUT
- B. INSERT
- C. GET
- D. COPY

<details><summary>Show Answer</summary>
Correct Answer: C. GET downloads files from a stage to a local file system; PUT uploads files to a stage.
</details>

---

### Question 604
By default, which role has privileges to create tables and views in an account?

- A. PUBLIC
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: C. SYSADMIN has privileges to create warehouses, databases, and other objects in an account by default.
</details>

---

### Question 605
What does Snowflake recommend as a best practice for using secure views?

- A. Use sequence-generated values.
- B. Programmatically reveal the identifiers.
- C. Use Secure views solely for convenience.
- D. Do not expose the sequence-generated column(s).

<details><summary>Show Answer</summary>
Correct Answer: D. Exposing sequence-generated columns in a secure view can allow users to infer information about the underlying table (e.g., row counts, insert order).
</details>

---

### Question 606
What is the Fail-safe period for a transient table in the Snowflake Enterprise edition and higher?

- A. 0 days
- B. 1 day
- C. 7 days
- D. 14 days

<details><summary>Show Answer</summary>
Correct Answer: A. Transient tables (and temporary tables) have no Fail-safe period.
</details>

---

### Question 607
How does a Snowflake user enable Multi-Factor Authentication (MFA)?

- A. The user must enroll themselves through the web interface.
- B. The user must submit their encrypted private key to Snowflake.
- C. The user must sign up with Duo Mobile to use the service.
- D. The user must configure Snowflake to use Single Sign-On (SSO).

<details><summary>Show Answer</summary>
Correct Answer: A. Users self-enroll in MFA through Snowsight/the web interface; Snowflake's MFA is powered by Duo Security under the hood.
</details>

---

### Question 608
What allows a user to limit the number of credits consumed within a Snowflake account?

- A. Tracking account usage
- B. Creating resource monitors
- C. Automatic virtual warehouse scaling
- D. Automatic clustering

<details><summary>Show Answer</summary>
Correct Answer: B. Resource monitors track and can suspend warehouses/accounts once defined credit thresholds are reached.
</details>

---

### Question 609
Which statement accurately describes Snowflake's architecture?

- A. It utilizes local data for all compute nodes in the platform.
- B. It is a blend of shared-disk and shared-everything database architectures.
- C. It is a hybrid of traditional shared-disk and shared-nothing database architectures.
- D. It reorganizes loaded data into internal optimized, compressed, and row-based format.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowflake combines a shared-disk model (centralized storage accessible from all nodes) with a shared-nothing model (MPP compute per virtual warehouse). Note: data is stored in **columnar**, not row-based, format — which makes D doubly wrong.
</details>

---

### Question 610
Which Snowflake SQL command is used to get a subset of rows randomly from a table?

- A. GENERATOR
- B. LATERAL
- C. PIVOT
- D. SAMPLE

<details><summary>Show Answer</summary>
Correct Answer: D. SAMPLE (or TABLESAMPLE) returns a random subset of rows.
</details>

---

### Question 611
Which statement accurately describes how a virtual warehouse functions?

- A. Increasing the size of a virtual warehouse will always improve data loading performance.
- B. Each virtual warehouse is an independent compute cluster that shares compute resources with other warehouses.
- C. Each virtual warehouse is a compute cluster composed of multiple compute nodes allocated by Snowflake from a cloud provider.
- D. All virtual warehouses share the same compute resources so performance degradation of one warehouse can significantly affect all the other warehouses.

<details><summary>Show Answer</summary>
Correct Answer: C. Warehouses are independent MPP compute clusters; they do not share compute resources with one another (contradicts B and D).
</details>

---

### Question 612
Which Snowflake object can be used to record DML changes made to a table?

- A. Snowpipe
- B. Stage
- C. Stream
- D. Task

<details><summary>Show Answer</summary>
Correct Answer: C. A Stream tracks change data capture (CDC) information — inserts, updates, deletes — for a table.
</details>

---

### Question 613
Which statistic displayed in a Query Profile is specific to external functions?

- A. Bytes written
- B. Total invocations
- C. Partitions scanned
- D. Bytes sent over the network

<details><summary>Show Answer</summary>
Correct Answer: B. "Total invocations" (or "External function calls") is specific to nodes involving external function execution.
</details>

---

### Question 614
If there is queueing in the virtual warehouse load monitoring chart, what should a Snowflake user do?

- A. Decrease the warehouse size.
- B. Decrease the maximum cluster count parameter.
- C. Change the settings to add additional clusters.
- D. Start a separate warehouse and move queued queries there.

<details><summary>Show Answer</summary>
Correct Answer: C. Increasing the maximum cluster count on a multi-cluster warehouse allows Snowflake to spin up additional clusters to absorb concurrent query load and reduce queueing.
</details>

---

### Question 615
Which command is used to generate a zero-copy 'snapshot' of any table, schema, or database?

- A. ALTER
- B. CREATE CLONE
- C. COPY
- D. CREATE REPLICATION GROUP

<details><summary>Show Answer</summary>
Correct Answer: B. Cloning (`CREATE ... CLONE`) creates a zero-copy snapshot of a table, schema, or database.
</details>

---

### Question 616
How long is the load history stored in the metadata of the pipe in Snowpipe?

- A. 2 days
- B. 7 days
- C. 14 days
- D. 64 days

<details><summary>Show Answer</summary>
Correct Answer: C. Snowpipe load history is maintained in pipe metadata for 14 days.
</details>

---

### Question 617
What are the key characteristics of ACCOUNT_USAGE views? (Choose two.)

- A. There is no data latency.
- B. The data latency can vary from 45 minutes to 3 hours.
- C. The historical data is not retained.
- D. The historical data can be retained from 7 days to 6 months.
- E. Records for dropped objects are included in each view.

<details><summary>Show Answer</summary>
Correct Answer: B, E. ACCOUNT_USAGE views have latency (varies by view) and include dropped objects, unlike INFORMATION_SCHEMA views.

⚠ **Updated:** Historical data in ACCOUNT_USAGE views is actually retained for **up to 365 days (1 year)**, not "7 days to 6 months" (D), so D remains incorrect for a different, more precise reason than originally stated. Latency for most views is documented as up to roughly 2 hours currently, though some views still cite ranges similar to 45 minutes–3 hours — this can vary by specific view, so treat exact latency numbers as approximate and check the specific view's documentation if precision matters.
</details>

---

### Question 618
How does a scoped URL expire?

- A. When the data cache clears.
- B. When the persisted query result period ends.
- C. The encoded URL access is permanent.
- D. The length of time is specified in the expiration_time argument.

<details><summary>Show Answer</summary>
Correct Answer: B. A scoped URL is valid only for the duration that the query results persist (typically 24 hours).
</details>

---

### Question 619
What are the available Snowflake scaling modes for configuring multi-cluster virtual warehouses? (Choose two.)

- A. Auto-Scale
- B. Economy
- C. Maximized
- D. Scale-Out
- E. Standard

<details><summary>Show Answer</summary>
Correct Answer: A, C. Multi-cluster warehouses run in either **Maximized** mode (min = max clusters, all running) or **Auto-scale** mode (min < max, clusters start/stop based on load). Note: "Standard" and "Economy" are **scaling policies** that govern *when* auto-scale adds/removes clusters — a related but distinct concept from scaling *mode*.
</details>

---

### Question 620
Which loop type iterates until a condition is true?

- A. FOR
- B. LOOP
- C. REPEAT
- D. WHILE

<details><summary>Show Answer</summary>
Correct Answer: C. REPEAT...UNTIL executes until a condition becomes true; WHILE executes while a condition remains true.
</details>

---

### Question 621
Which property needs to be added to the ALTER WAREHOUSE command to verify the additional compute resources for a virtual warehouse have been fully provisioned?

- A. AUTO_RESUME
- B. WAIT_FOR_COMPLETION
- C. RESOURCE_MONITOR
- D. SCALING_POLICY

<details><summary>Show Answer</summary>
Correct Answer: B. WAIT_FOR_COMPLETION makes the ALTER WAREHOUSE statement block until resizing completes.
</details>

---

### Question 622
How is enhanced authentication achieved in Snowflake? (Choose two.)

- A. Snowflake-managed keys
- B. Object level access control
- C. Password hashing
- D. Multi-Factor Authentication (MFA)
- E. Federated authentication and Single Sign-on (SSO)

<details><summary>Show Answer</summary>
Correct Answer: D, E. MFA and Federated authentication/SSO are Snowflake's enhanced authentication mechanisms beyond basic username/password.
</details>

---

### Question 623
What are the native data types that Snowflake provides to store semi-structured data? (Choose two.)

- A. ARRAY
- B. JSON
- C. ORC
- D. Parquet
- E. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: A, E. ARRAY, OBJECT, and VARIANT are Snowflake's native semi-structured data types. JSON, ORC, and Parquet are file formats, not column data types.
</details>

---

### Question 624
How long is the Fail-safe period for recovering historical data from permanent tables?

- A. 1 day
- B. 3 days
- C. 7 days
- D. 14 days

<details><summary>Show Answer</summary>
Correct Answer: C. Permanent tables have a standard 7-day Fail-safe period.
</details>

---

### Question 625
What does the average_overlaps in the output of SYSTEM$CLUSTERING_INFORMATION refer to?

- A. The average number of micro-partitions in Time Travel
- B. The average number of partitions physically stored in the same location
- C. The average number of micro-partitions which contain overlapping value ranges
- D. The average number of micro-partitions in the table associated with cloned objects

<details><summary>Show Answer</summary>
Correct Answer: C. average_overlaps measures how many micro-partitions overlap in value range with a given micro-partition — a key clustering health metric.
</details>

---

### Question 626
If queries start to queue in a multi-cluster virtual warehouse, an additional compute cluster starts immediately under what setting?

- A. Auto-scale mode
- B. Maximized mode
- C. Economy scaling policy
- D. Standard scaling policy

<details><summary>Show Answer</summary>
Correct Answer: D. The Standard scaling policy favors starting additional clusters quickly to minimize queuing (at the cost of credit efficiency), whereas Economy favors conserving credits and may allow some queuing.
</details>

---

### Question 627
When floating-point number columns are unloaded to CSV or JSON files, Snowflake truncates the values to approximately what?

- A. (12,2)
- B. (10,4)
- C. (14,8)
- D. (15,9)

<details><summary>Show Answer</summary>
Correct Answer: D. Floating-point values are truncated to approximately 15 digits of precision, 9 after the decimal point, when unloaded to CSV/JSON.
</details>

---

### Question 628
By definition, a secure view is exposed only to users with what privilege?

- A. IMPORT SHARE
- B. OWNERSHIP
- C. REFERENCES
- D. USAGE

<details><summary>Show Answer</summary>
Correct Answer: B. Only the OWNERSHIP role/privilege context can see the secure view's definition and details; other users cannot.
</details>

---

### Question 629
What happens when a user exits Snowsight during a session where a query is running?

- A. Snowflake executes the query during the same session immediately.
- B. Snowflake cancels any queries submitted during this session that are still running.
- C. Snowflake will cancel any queries submitted during this session after 24 hours.
- D. Snowflake will continue to execute and complete upon the next login.

<details><summary>Show Answer</summary>
Correct Answer: D. Closing the browser/UI does not cancel a running query — Snowflake continues executing it server-side.
</details>

---

### Question 630
Which native data types are used for storing semi-structured data in Snowflake? (Choose two.)

- A. NUMBER
- B. OBJECT
- C. STRING
- D. VARCHAR
- E. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: B, E. OBJECT and VARIANT are native semi-structured types (along with ARRAY).
</details>

---

### Question 631
Which columns are available in the output of a Snowflake directory table? (Choose two.)

- A. CATALOG_NAME
- B. FILE_NAME
- C. LAST_MODIFIED
- D. RELATIVE_PATH
- E. STAGE_NAME

<details><summary>Show Answer</summary>
Correct Answer: C, D. A directory table's output includes columns such as RELATIVE_PATH, SIZE, LAST_MODIFIED, MD5, ETAG, and FILE_URL.
</details>

---

### Question 632
What is used to diagnose and troubleshoot network connections to Snowflake?

- A. SnowCD
- B. Snowpark
- C. Snowsight
- D. SnowSQL

<details><summary>Show Answer</summary>
Correct Answer: A. SnowCD (Snowflake Connectivity Diagnostic Tool) tests and diagnoses network connectivity to Snowflake.
</details>

---

### Question 633
Which Snowflake object records Data Manipulation Language (DML) changes so that actions can be taken using the changed data?

- A. Pipe
- B. Stream
- C. Task
- D. View

<details><summary>Show Answer</summary>
Correct Answer: B. Streams record DML changes (CDC) for downstream processing, often paired with Tasks.
</details>

---

### Question 634
By default, the COPY INTO [location] statement will separate table data into a set of output files to take advantage of which Snowflake feature?

- A. Query acceleration
- B. Query plan caching
- C. Parallel processing
- D. Time Travel

<details><summary>Show Answer</summary>
Correct Answer: C. Splitting unloaded data into multiple files enables parallel operations across warehouse nodes.
</details>

---

### Question 635
Which command can be used to view the allowed and blocked IP list of a network policy?

- A. ALTER NETWORK POLICY
- B. CREATE NETWORK POLICY
- C. DESCRIBE NETWORK POLICY
- D. SHOW NETWORK POLICIES

<details><summary>Show Answer</summary>
Correct Answer: C. DESCRIBE NETWORK POLICY shows the allowed/blocked IP lists for a specific policy; SHOW NETWORK POLICIES only lists policy names/metadata.
</details>

---

### Question 636
Which file functions are nondeterministic? (Choose two.)

- A. BUILD_SCOPED_FILE_URL
- B. GET_STAGE_LOCATION
- C. GET_PRESIGNED_URL
- D. BUILD_STAGE_FILE_URL

<details><summary>Show Answer</summary>
Correct Answer: A, C. BUILD_SCOPED_FILE_URL and GET_PRESIGNED_URL generate URLs that vary between calls (e.g., due to expiration/token), making them nondeterministic.
</details>

---

### Question 637
How can a Snowflake user optimize query performance? (Choose two.)

- A. Create a view.
- B. Cluster a table.
- C. Enable the search optimization service.
- D. Enable Time Travel.
- E. Index a table.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Clustering and the search optimization service are the two primary performance-tuning levers listed here. (Snowflake has no traditional indexes, so E is invalid.)
</details>

---

### Question 638
What is the MINIMUM role required to set the value for the DATA_RETENTION_TIME_IN_DAYS account parameter?

- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. ORGADMIN

<details><summary>Show Answer</summary>
Correct Answer: A. Account-level parameters such as DATA_RETENTION_TIME_IN_DAYS require ACCOUNTADMIN (though it can be set at lower object levels, like a table, by users with appropriate object privileges).
</details>

---

### Question 639
Which file format will keep floating-point numbers from being truncated when data is unloaded?

- A. CSV
- B. JSON
- C. ORC
- D. Parquet

<details><summary>Show Answer</summary>
Correct Answer: D. Parquet preserves full floating-point precision; CSV/JSON truncate to ~(15,9).
</details>

---

### Question 640
A user has semi-structured data to load into Snowflake but is not sure what types of operations will need to be performed on the data. Based on this situation, what type of column does Snowflake recommend be used?

- A. ARRAY
- B. OBJECT
- C. STRING
- D. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: D. VARIANT is the flexible, general-purpose type recommended when future query patterns are unknown.
</details>

---

### Question 641
Which feature helps evaluate virtual warehouse performance impacted by queuing?

- A. Resource monitor
- B. Query history
- C. Load monitoring chart
- D. Task history

<details><summary>Show Answer</summary>
Correct Answer: C. The warehouse load monitoring chart visualizes queued vs. running queries over time.
</details>

---

### Question 642
Which Snowflake object can be created to be temporary?

- A. Role
- B. Stage
- C. User
- D. Storage integration

<details><summary>Show Answer</summary>
Correct Answer: B. Stages (along with tables) support the TEMPORARY object type; roles, users, and storage integrations do not.
</details>

---

### Question 643
Which stream type can be used for tracking the records in external tables?

- A. Append-only
- B. External
- C. Insert-only
- D. Standard

<details><summary>Show Answer</summary>
Correct Answer: C. Insert-only streams are used to track new records added to external tables (external tables don't support standard/append-only streams).
</details>

---

### Question 644
What is the recommended approach for unloading data to a cloud storage location from Snowflake?

- A. Use a third-party tool to unload the data to cloud storage.
- B. Unload the data directly to the cloud storage location.
- C. Unload the data to a local system, then upload it to cloud storage.
- D. Unload the data to a user stage, then upload the data to cloud storage.

<details><summary>Show Answer</summary>
Correct Answer: B. Unloading directly to an external stage/cloud location is the recommended, most efficient path.
</details>

---

### Question 645
Which command is used to unload files from an internal or external stage to a local file system?

- A. COPY INTO
- B. GET
- C. PUT
- D. TRANSFER

<details><summary>Show Answer</summary>
Correct Answer: B. GET downloads staged files to a local file system.
</details>

---

### Question 646
A tabular User Defined Function (UDF) is defined by specifying a return clause that contains which keyword?

- A. ROW_NUMBER
- B. TABLE
- C. TABULAR
- D. VALUES

<details><summary>Show Answer</summary>
Correct Answer: B. A tabular (table-valued) UDF uses `RETURNS TABLE (...)`.
</details>

---

### Question 647
Which SQL statement will require a virtual warehouse to run?

- A. SELECT COUNT(*) FROM TBL_EMPLOYEE;
- B. ALTER TABLE TBL_EMPLOYEE ADD COLUMN EMP_REGION VARCHAR(20);
- C. INSERT INTO TBL_EMPLOYEE (EMP_ID, EMP_NAME, EMP_SALARY, DEPT) VALUES(1, 'Adam', 20000, 'Finance');
- D. CREATE OR REPLACE TABLE TBL_EMPLOYEE (EMP_ID NUMBER);

<details><summary>Show Answer</summary>
Correct Answer: C. INSERT requires compute to write data. DDL (ALTER, CREATE) is metadata-only, and simple aggregate queries like COUNT(*) can sometimes be resolved from metadata without a running warehouse.
</details>

---

### Question 648
Which REST API endpoint can be used with unstructured data?

- A. insertReport
- B. PUT
- C. GET
- D. loadHistoryScan

<details><summary>Show Answer</summary>
Correct Answer: C. The GET endpoint is used to retrieve unstructured files via presigned/scoped URLs.
</details>

---

### Question 649
Which query contains a Snowflake hosted file URL in a directory table for a stage named bronzestage?

- A. list @bronzestage;
- B. select * from directory(@bronzestage);
- C. select metadata$filename from @bronzestage;
- D. select * from @bronzestage;

<details><summary>Show Answer</summary>
Correct Answer: B. Querying `directory(@stage_name)` returns the directory table, which includes the FILE_URL column.
</details>

---

### Question 650
Which feature is integrated to support Multi-Factor Authentication (MFA) at Snowflake?

- A. Authy
- B. Duo Security
- C. OneLogin
- D. RSA SecurID Access

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake's native MFA is powered by Duo Security.
</details>

---

### Question 651
In which Snowflake layer does Snowflake reorganize data into its internal optimized, compressed, columnar format?

- A. Cloud Services
- B. Database Storage
- C. Query Processing
- D. Metadata Management

<details><summary>Show Answer</summary>
Correct Answer: B. The Database Storage layer handles reorganizing and storing data in Snowflake's proprietary columnar format.
</details>

---

### Question 652
When can user session variables be accessed in a Snowflake scripting procedure?

- A. When the procedure is defined as STRICT.
- B. When the procedure is defined to execute as CALLER.
- C. When the procedure is defined to execute as OWNER.
- D. When the procedure is defined with an argument that has the same name and type as the session variable.

<details><summary>Show Answer</summary>
Correct Answer: B. Stored procedures executed with `EXECUTE AS CALLER` run in the caller's session context, so they can access the caller's session variables.
</details>

---

### Question 653
What computer languages can be selected when creating User-Defined Functions (UDFs) using the Snowpark API?

- A. Swift
- B. JavaScript
- C. Java, Scala, Python
- D. C++

<details><summary>Show Answer</summary>
Correct Answer: C. Snowpark supports Java, Scala, and Python for UDFs (JavaScript UDFs exist but are a separate, non-Snowpark mechanism).
</details>

---

### Question 654
A user needs to ingest 1 GB of data that is available in an external stage using a COPY INTO command. How can this be done with MAXIMUM performance and the LEAST cost?

- A. Ingest the data in a compressed format as a single file.
- B. Ingest the data in an uncompressed format as a single file.
- C. Split the file into smaller files of 100-250 MB each, compress and ingest each of the smaller files.
- D. Split the file into smaller files of 100-250 MB each and ingest each of the smaller files in an uncompressed format.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowflake's file-sizing best practice is 100–250 MB compressed files to maximize parallel loading efficiency while minimizing storage/network cost.
</details>

---

### Question 655
A Snowflake user has two tables that contain numeric values and is trying to find which values are present in both tables. Which set operator should be used?

- A. INTERSECT
- B. MERGE
- C. MINUS
- D. UNION

<details><summary>Show Answer</summary>
Correct Answer: A. INTERSECT returns only rows/values present in both result sets.
</details>

---

### Question 656
A view is defined on a permanent table. A temporary table with the same name is created in the same schema as the referenced table. What will a query from the view return?

- A. The data from the permanent table.
- B. The data from the temporary table.
- C. An error stating that the view could not be compiled.
- D. An error stating that the referenced object could not be uniquely identified.

<details><summary>Show Answer</summary>
Correct Answer: A. A view's reference is bound at creation time to the permanent table; a same-named temporary table created later does not override that binding for the view.
</details>

---

### Question 657
Which file function generates a Snowflake-hosted file URL to a staged file using the stage name and relative file path as inputs?

- A. BUILD_STAGE_FILE_URL
- B. GET_ABSOLUTE_PATH
- C. GENERATE_PRESIGNED_URL
- D. BUILD_SCOPED_FILE_URL

<details><summary>Show Answer</summary>
Correct Answer: A. BUILD_STAGE_FILE_URL generates a permanent Snowflake-hosted URL from a stage name and relative path.
</details>

---

### Question 658
Which service or feature in Snowflake is used to improve the performance of certain types of lookup and analytical queries that use an extensive set of WHERE conditions?

- A. Data classification
- B. Query acceleration service
- C. Search optimization service
- D. Tagging

<details><summary>Show Answer</summary>
Correct Answer: C. The search optimization service speeds up selective point lookups and queries with many varied WHERE clause predicates.
</details>

---

### Question 659
What is the name of the SnowSQL file that can store connection information?

- A. history
- B. config
- C. snowsql.cnf
- D. credentials

<details><summary>Show Answer</summary>
Correct Answer: B. The `config` file stores SnowSQL connection parameters and named connections.
</details>

---

### Question 660
How do secure views compare to non-secure views in Snowflake?

- A. Secure views are slower compared to non-secure views.
- B. Non-secure views are preferred over secure views when sharing data.
- C. Secure views are similar to materialized views in that they are the most performant.
- D. End users are unable to see the view definition, and internal optimizations differ to protect underlying data.

<details><summary>Show Answer</summary>
Correct Answer: D. Secure views hide the definition from unauthorized users and forgo certain query-optimizer disclosures (which can slightly reduce performance) to protect underlying data.
</details>

---

### Question 661
Which type of join will list all rows in the specified table, even if those rows have no match in the other table?

- A. Cross join
- B. Inner join
- C. Natural join
- D. Outer join

<details><summary>Show Answer</summary>
Correct Answer: D. An outer join (left/right/full) preserves unmatched rows from one or both tables.
</details>

---

### Question 662
When unloading data to an external stage, what is the MAXIMUM file size supported per file?

- A. 1 GB
- B. 5 GB
- C. 16 MB
- D. 250 MB

<details><summary>Show Answer</summary>
Correct Answer: B. 5 GB is the documented maximum unloaded file size for external stages (S3, GCS, Azure). This is confirmed in current Snowflake documentation.
</details>

---

### Question 663
How long does Snowflake retain information in the ACCESS_HISTORY view?

- A. 14 days
- B. 28 days
- C. 90 days
- D. 365 days

<details><summary>Show Answer</summary>
Correct Answer: D. ACCESS_HISTORY (an ACCOUNT_USAGE view) retains up to 365 days of history, consistent with other ACCOUNT_USAGE views.
</details>

---

### Question 664
Which encryption type will enable client-side encryption for a directory table?

- A. AWS_CSE
- B. SNOWFLAKE_SSE
- C. SNOWFLAKE_FULL
- D. CLIENT_SIDE_ENCRYPTION

<details><summary>Show Answer</summary>
Correct Answer: A. AWS_CSE (client-side encryption) is required for directory tables on client-side-encrypted external stages; server-side encryption (SNOWFLAKE_SSE) is not supported for directory tables on external stages in the same way.
</details>

---

### Question 665
If file format options are specified in multiple locations, the load operation selects which option FIRST to apply in order of precedence?

- A. Table definition
- B. Stage definition
- C. Session level
- D. COPY INTO TABLE statement

<details><summary>Show Answer</summary>
Correct Answer: D. Options specified directly in the COPY INTO &lt;table&gt; statement take the highest precedence, overriding stage- and table-level defaults.
</details>

---

### Question 666
A complex SQL query involving eight tables with joins is taking a while to execute. The Query Profile shows that all partitions are being scanned. What is causing the query performance issue?

- A. Pruning is not being performed efficiently.
- B. A massive volume of data is being fetched, with many joins applied.
- C. Incorrect joins are being used, leading to scanning and pulling too many records.
- D. The columns in the micro-partitions need granular ordering based on the dataset.

<details><summary>Show Answer</summary>
Correct Answer: A. When all micro-partitions are scanned instead of a pruned subset, it indicates partition pruning isn't effective — usually due to poor clustering relative to the query's filter predicates.
</details>

---

### Question 667
What does the search optimization service support?

- A. External tables
- B. Materialized views
- C. Equality searches, casts on table columns (except for fixed-point numbers cast to strings), and IN predicates.
- D. Subqueries that return multiple rows

<details><summary>Show Answer</summary>
Correct Answer: C. Search optimization accelerates equality/IN lookups and most column casts (with documented exceptions like fixed-point-to-string casts).
</details>

---

### Question 668
Which table type is no longer available after the close of the session and therefore has no Fail-safe or Time Travel option?

- A. Permanent
- B. External
- C. Temporary
- D. Transient

<details><summary>Show Answer</summary>
Correct Answer: C. Temporary tables exist only for the session and are dropped automatically at session end, with no Fail-safe and Time Travel limited to that session's lifetime.
</details>

---

### Question 669
How many network policies can be assigned to an account or specific user at a time?

- A. One
- B. Two
- C. Five
- D. Unlimited

<details><summary>Show Answer</summary>
Correct Answer: A. Only one network policy can be active at a time for an account or a given user.
</details>

---

### Question 670
What is a characteristic of a tag associated with a masking policy?

- A. A tag can be dropped after a masking policy is assigned.
- B. A tag can have only one masking policy for each data type.
- C. A tag can have multiple masking policies for each data type.
- D. A tag can have multiple masking policies with varying data types.

<details><summary>Show Answer</summary>
Correct Answer: B. A single tag can be associated with only one masking policy per data type (though it can have different masking policies for different data types).
</details>

---

### Question 671
Which clients does Snowflake support Multi-Factor Authentication (MFA) token caching for? (Choose two.)

- A. Go driver
- B. Node.js driver
- C. ODBC driver
- D. Python connector
- E. Spark connector

<details><summary>Show Answer</summary>
Correct Answer: C, D. MFA token caching is documented as supported for the ODBC driver and Python connector (among other specific drivers), reducing repeated MFA prompts.
</details>

---

### Question 672
What is the Snowflake recommended Parquet file size when querying from external tables to optimize the number of parallel scanning operations?

- A. 1-16 MB
- B. 16-128 MB
- C. 100-250 MB
- D. 256-512 MB

<details><summary>Show Answer</summary>
Correct Answer: D. For external tables/Parquet, Snowflake recommends larger files (in the low hundreds of MB range) to balance parallelism and file overhead — larger than the general 100–250 MB rule of thumb used for standard staged loads.
</details>

---

### Question 673
Which data types can be used in a Snowflake table that holds semi-structured data? (Choose two.)

- A. ARRAY
- B. BINARY
- C. INTEGER
- D. VARIANT
- E. VARCHAR

<details><summary>Show Answer</summary>
Correct Answer: A, D. ARRAY and VARIANT are semi-structured data types.
</details>

---

### Question 674
Which constraint is actively enforced in Snowflake?

- A. FOREIGN KEY
- B. NOT NULL
- C. PRIMARY KEY
- D. UNIQUE KEY

<details><summary>Show Answer</summary>
Correct Answer: B. NOT NULL is the only constraint type actively enforced. PRIMARY KEY, UNIQUE, and FOREIGN KEY are supported for metadata/documentation and query optimization purposes but are not enforced.
</details>

---

### Question 675
Which pages are included in the Activity area of Snowsight? (Choose two.)

- A. Contacts
- B. Sharing settings
- C. Copy History
- D. Query History
- E. Automatic Clustering History

<details><summary>Show Answer</summary>
Correct Answer: C, D. The Activity area in Snowsight includes Query History and Copy History pages.
</details>

---

### Question 676
When should a user consider disabling auto-suspend for a virtual warehouse? (Choose two.)

- A. When users will be using compute at different times throughout a 24/7 period
- B. When managing a steady workload
- C. When the compute must be available with no delay or lag time
- D. When the user does not want to have to manually turn on the warehouse each time it is needed
- E. When the warehouse is shared between different teams

<details><summary>Show Answer</summary>
Correct Answer: B, C. Disabling auto-suspend makes sense for steady, continuous workloads or when zero warehouse resume latency is required — the credit cost tradeoff is acceptable in these cases.
</details>

---

### Question 677
What can a Snowflake user do in the Activity section in Snowsight?

- A. Create dashboards.
- B. Write and run SQL queries.
- C. Explore databases and objects.
- D. Monitor query performance and history.

<details><summary>Show Answer</summary>
Correct Answer: D. The Activity section is for monitoring query performance, query history, and copy history.
</details>

---

### Question 678
How does Snowflake reorganize data when it is loaded? (Choose two.)

- A. Binary
- B. Columnar format
- C. Compressed format
- D. Raw format
- E. Zipped format

<details><summary>Show Answer</summary>
Correct Answer: B, C. Loaded data is reorganized into a compressed, columnar internal format.
</details>

---

### Question 679
Which operations are handled in the Cloud Services layer of Snowflake? (Choose two.)

- A. Security and Authentication
- B. Data Storage
- C. Data visualization
- D. Query computation
- E. Metadata management

<details><summary>Show Answer</summary>
Correct Answer: A, E. The Cloud Services layer handles authentication, infrastructure management, metadata, access control, and query optimization/parsing (not the actual storage or compute execution).
</details>

---

### Question 680
At which point is data encrypted when using a PUT command?

- A. When it reaches the virtual warehouse
- B. When it gets micro-partitioned
- C. Client-side before it is sent from the user's machine
- D. After it reaches the internal stage

<details><summary>Show Answer</summary>
Correct Answer: C. PUT encrypts data client-side (128-bit or 256-bit AES) before uploading it to the stage.
</details>

---

### Question 681
What type of columns does Snowflake recommend to be used as clustering keys? (Choose two.)

- A. A VARIANT column
- B. A column with very low cardinality
- C. A column with very high cardinality
- D. A column that is most actively used in selective filters
- E. A column that is most actively used in join predicates

<details><summary>Show Answer</summary>
Correct Answer: D, E. Clustering keys should be columns frequently used in WHERE filters or JOIN predicates — and ideally with moderate (not extremely low or high) cardinality, though the best answer choices here focus on usage pattern rather than cardinality extremes.
</details>

---

### Question 682
Which objects together comprise a namespace in Snowflake? (Choose two.)

- A. Account
- B. Database
- C. Schema
- D. Table
- E. Virtual warehouse

<details><summary>Show Answer</summary>
Correct Answer: B, C. A namespace in Snowflake is composed of a database and schema (e.g., `db.schema.object`).
</details>

---

### Question 683
What statistical information in a Query Profile indicates that the query is too large to fit in memory? (Choose two.)

- A. Bytes spilled to local disk cache
- B. Bytes spilled to local storage
- C. Bytes spilled to remote cache
- D. Bytes spilled to remote storage
- E. Bytes spilled to remote metastore

<details><summary>Show Answer</summary>
Correct Answer: B, D. "Bytes spilled to local storage" and "Bytes spilled to remote storage" indicate the warehouse ran out of memory and had to spill intermediate results to disk (local) or cloud storage (remote, which is slower and more costly).
</details>

---

### Question 684
How do Snowflake data providers share data that resides in different databases?

- A. External tables
- B. Secure views
- C. Materialized views
- D. User-Defined Functions

<details><summary>Show Answer</summary>
Correct Answer: B. Secure views can reference objects across databases and are the standard mechanism for cross-database data sharing.
</details>

---

### Question 685
What operations can be performed while loading a simple CSV file into a Snowflake table using the COPY INTO command? (Choose two.)

- A. Performing aggregate calculations
- B. Reordering the columns
- C. Grouping by operations
- D. Converting the datatypes
- E. Selecting the first few rows

<details><summary>Show Answer</summary>
Correct Answer: B, D. During a COPY INTO load, you can reorder columns and convert data types; aggregate/group-by transformations are not supported during COPY INTO load transformations.
</details>

---

### Question 686
Which commands support a multiple-statement request to run and update Snowflake data? (Choose two.)

- A. CALL
- B. COMMIT
- C. GET
- D. ROLLBACK
- E. EXPLAIN

<details><summary>Show Answer</summary>
Correct Answer: B, D. COMMIT and ROLLBACK are transaction control commands used to finalize or undo multi-statement transactions.
</details>

---

### Question 687
Why should a Snowflake user implement a secure view? (Choose two.)

- A. To store unstructured data
- B. To increase query performance
- C. To limit access to sensitive data
- D. To optimize query concurrency and queuing
- E. To hide view definition and details from unauthorized users

<details><summary>Show Answer</summary>
Correct Answer: C, E. Secure views restrict access to sensitive underlying data and hide the view's definition from unauthorized users.
</details>

---

### Question 688
At what levels can a resource monitor be configured? (Choose two.)

- A. Account
- B. Database
- C. Organization
- D. Schema
- E. Virtual warehouse

<details><summary>Show Answer</summary>
Correct Answer: A, E. Resource monitors can be set at the account level or assigned to specific virtual warehouses.
</details>

---

### Question 689
What activities can be monitored by a user directly from Snowsight's Activity tab without using the Account_Usage views? (Choose two.)

- A. Login history
- B. Query history
- C. Copy history
- D. Event usage history
- E. Virtual warehouse metering history

<details><summary>Show Answer</summary>
Correct Answer: B, C. Query History and Copy History are directly available in the Snowsight Activity tab.
</details>

---

### Question 690
What can a Snowflake user do with the information included in the details section of a Query Profile?

- A. Determine the total duration of the query execution.
- B. Determine the role of the user who ran the query.
- C. Determine the source system that the queried table is from.
- D. Determine if the query was on structured or semi-structured data.

<details><summary>Show Answer</summary>
Correct Answer: A. The Query Profile details panel shows execution time/duration statistics, among other performance metrics.
</details>

---

### Question 691
How can a Snowflake user access a JSON object, given the following table? (Choose two.)

`{ "id": "1234", "customer": { "name": "user" } }`

- A. src:customer.name
- B. src:customer.name::string
- C. src['customer']['name']
- D. src.customer.name

<details><summary>Show Answer</summary>
Correct Answer: B, C. Colon notation (`src:customer.name`) requires an explicit cast (`::string`) to return a usable string type, and bracket notation (`src['customer']['name']`) is a valid alternative path syntax.
</details>

---

### Question 692
Which term is used to describe information about disk usage for operations where intermediate results cannot be accommodated in a Snowflake virtual warehouse memory?

- A. Pruning
- B. Spilling
- C. Join explosion
- D. Queueing

<details><summary>Show Answer</summary>
Correct Answer: B. "Spilling" describes when intermediate query results exceed available memory and must be written to local or remote disk.
</details>

---

### Question 693
There are two Snowflake accounts in the same cloud provider region: one is production and the other is non-production. How can data be easily transferred from the production account to the non-production account?

- A. Clone the data from the production account to the non-production account.
- B. Create a data share from the production to the non-production account.
- C. Create a subscription in the production account and have it publish to the non-production account.
- D. Create a reader account using the production account and link the reader account to the non-production account.

<details><summary>Show Answer</summary>
Correct Answer: B. Secure Data Sharing lets a provider account share data with a consumer account in the same region without copying/moving data. (Note: cross-account cloning is not directly possible — cloning only works within the same account, so A is invalid, reinforcing B as correct.)
</details>

---

### Question 694
A user is unloading data to a Stage using this command:

```sql
COPY INTO @message
FROM (SELECT object_construct('id', 1, 'first_name', 'Snowflake', 'last_name', 'User', 'city', 'Bozeman'))
file_format = (type = json)
```

What will the output file in the stage be?

- A. A single compressed JSON file with a single VARIANT column.
- B. Multiple compressed JSON files with a single VARIANT column.
- C. A single uncompressed JSON file with multiple VARIANT columns.
- D. Multiple uncompressed JSON files with multiple VARIANT columns.

<details><summary>Show Answer</summary>
Correct Answer: A. OBJECT_CONSTRUCT produces a single VARIANT column per row, and by default COPY INTO unloads data compressed (gzip) — for this small single-row query, this results in one compressed file.
</details>

---

### Question 695
A JSON file that contains lots of dates needs to be loaded into Snowflake. The user wants to ensure optimal performance while querying the data. How can this be achieved?

- A. Flatten the data and store it in structured data types in a flattened table. Query the table.
- B. Store the data in a table with a VARIANT data type. Query the table.
- C. Store the data in a table with a VARIANT data type and include indexing while loading the table. Query the table.
- D. Store the data in an external stage and create views on top of it. Query the views.

<details><summary>Show Answer</summary>
Correct Answer: A. Flattening semi-structured data into structured columns (rather than leaving it all in VARIANT) generally yields better query performance, since structured columns benefit more fully from pruning, clustering, and type-specific optimizations. (Snowflake has no user-managed indexing, so C is invalid.)
</details>

---

### Question 696
When referring to User-Defined Function (UDF) names in Snowflake, what does the term "overloading" mean?

- A. There are multiple SQL UDFs with the same names and the same number of arguments.
- B. There are multiple SQL UDFs with the same names and the same number of argument types.
- C. There are multiple SQL UDFs with the same names but with a different number of arguments or argument types.
- D. There are multiple SQL UDFs with different names but the same number of arguments or argument types.

<details><summary>Show Answer</summary>
Correct Answer: C. Overloading means multiple UDFs share a name but differ in argument count or argument types, allowing Snowflake to resolve which one to call based on the call signature.
</details>

---

### Question 697
Which key governance feature in Snowflake allows users to identify data objects that contain sensitive data and their related objects?

- A. Object tagging
- B. Data classification
- C. Row access policy
- D. Column-level security

<details><summary>Show Answer</summary>
Correct Answer: B. Data classification automatically analyzes and tags columns that may contain sensitive/PII data, helping identify related objects.
</details>

---

### Question 698
What can a Snowflake user do in the Admin area of Snowsight?

- A. Analyze query processing plans.
- B. Write queries and execute them.
- C. Provide an overview of the listings in the Snowflake Marketplace.
- D. Explore billing, usage, warehouses, resource monitors, users, and roles.

<details><summary>Show Answer</summary>
Correct Answer: D. The Admin area covers account administration: billing/usage, warehouses, resource monitors, users, and roles.
</details>

---

### Question 699
Which function generates a Snowflake hosted file URL to a staged file using the stage name and relative file path as inputs?

- A. GET_STAGE_URL
- B. BUILD_STAGE_FILE_URL
- C. GET_PRESIGNED_URL
- D. BUILD_SCOPED_FILE_URL

<details><summary>Show Answer</summary>
Correct Answer: B. BUILD_STAGE_FILE_URL builds a permanent Snowflake-hosted file URL from a stage name and relative path (duplicate concept to Question 657).
</details>

---

### Question 700
What is the purpose of using the OBJECT_CONSTRUCT function with the COPY INTO command?

- A. Reorder the columns in a relational table and then unload the data into a file.
- B. Convert the rows in a relational table to a single VARIANT column and then unload the rows into a file.
- C. Reorder the data columns according to a target table definition and then unload the rows into the table.
- D. Convert the rows in a source file to a single VARIANT column and then load the rows from the file to a variant table.

<details><summary>Show Answer</summary>
Correct Answer: B. OBJECT_CONSTRUCT is used during unload to collapse relational row data into a single VARIANT (JSON-like) column before writing it to a file.
</details>

---



====================================================================================================
# snowpro_701_800.md
====================================================================================================

# SnowPro Core Practice Questions (701–800)

*Cleaned, reformatted, and cross-checked against Snowflake documentation (as of July 2026). Answers are hidden in collapsible blocks — click "Show Answer" to reveal.*

---

### Question 701
Which URL provides access to files in Snowflake without authorization?

- A. File URL
- B. Scoped URL
- C. Pre-signed URL
- D. Scoped file URL

<details><summary>Show Answer</summary>
Correct Answer: C. A pre-signed URL embeds a temporary access token, so the holder can retrieve the file without separately authenticating to Snowflake.
</details>

---

### Question 702
What type of NULL values are supported in semi-structured data? (Choose two.)

- A. JSON NULL
- B. XML NULL
- C. ORC NULL
- D. Parquet NULL
- E. SQL NULL

<details><summary>Show Answer</summary>
Correct Answer: A, E. Snowflake distinguishes between a JSON NULL (a stored value meaning "no value") and a SQL NULL (the absence of a value).
</details>

---

### Question 703
What are characteristics of transient tables in Snowflake? (Choose two.)

- A. Transient tables have a Fail-safe period of 7 days.
- B. Transient tables can be cloned to permanent tables.
- C. Transient tables persist until they are explicitly dropped.
- D. Transient tables can be altered to make them permanent tables.
- E. Transient tables have Time Travel retention periods of 0 or 1 day.

<details><summary>Show Answer</summary>
Correct Answer: C, E. Transient tables have no Fail-safe period (ruling out A) and persist like permanent tables until dropped, with a Time Travel window of 0 or 1 day.
</details>

---

### Question 704
The INFORMATION_SCHEMA included in each database contains which objects? (Choose two.)

- A. Views for all the objects contained in the database
- B. Views for all the objects contained in the Snowflake account
- C. Views for historical and usage data across the Snowflake account
- D. Table functions for historical and usage data in the Snowflake account
- E. Table functions for account-level objects, such as roles, virtual warehouses, and databases

<details><summary>Show Answer</summary>
Correct Answer: A, D. INFORMATION_SCHEMA scopes views to the current database's objects, plus table functions that expose historical/usage data at the account level.
</details>

---

### Question 705
The use of which technique or tool will improve Snowflake query performance on very large tables?

- A. Clustering keys
- B. Multi-clustering
- C. Materialized views
- D. Search optimization service

<details><summary>Show Answer</summary>
Correct Answer: A. Defining a clustering key co-locates related rows in micro-partitions, improving pruning on very large tables.
</details>

---

### Question 706
Which Snowflake layer is associated with virtual warehouses?

- A. Cloud services
- B. Query processing
- C. Elastic memory
- D. Database storage

<details><summary>Show Answer</summary>
Correct Answer: B. Virtual warehouses make up the query processing (compute) layer of Snowflake's architecture.
</details>

---

### Question 707
Which MINIMUM set of privileges is required to temporarily bypass an active network policy by configuring the user object property?

- A. Only while in the ACCOUNTADMIN role
- B. Only while in the SECURITYADMIN role
- C. Only the role with the OWNERSHIP privilege on the network policy
- D. Only Snowflake Support can set the value of this property

<details><summary>Show Answer</summary>
Correct Answer: D. The `MINS_TO_BYPASS_NETWORK_POLICY` user property can only be set by contacting Snowflake Support — no account-side role, including ACCOUNTADMIN, can set it directly. This remains accurate per current documentation.
</details>

---

### Question 708
What authentication method does the Kafka connector use within Snowflake?

- A. Key pair authentication
- B. Multi-Factor Authentication (MFA)
- C. OAuth
- D. Username and password

<details><summary>Show Answer</summary>
Correct Answer: A. The Kafka connector authenticates using key pair authentication.
</details>

---

### Question 709
What is the purpose of the Snowflake SPLIT_TO_TABLE function?

- A. To count the number of characters in a string
- B. To split a string into an array of sub-strings
- C. To split a string and flatten the results into rows
- D. To split a string and flatten the results into columns

<details><summary>Show Answer</summary>
Correct Answer: C. SPLIT_TO_TABLE splits an input string on a delimiter and returns each piece as a separate output row.
</details>

---

### Question 710
What feature of Snowflake Continuous Data Protection can be used for maintenance of historical data?

- A. Access control
- B. Fail-safe
- C. Network policies
- D. Time Travel

<details><summary>Show Answer</summary>
Correct Answer: D. Time Travel lets users query, clone, or restore historical versions of data within a configurable retention window.
</details>

---

### Question 711
What aspect of an executed query is represented by the remote disk I/O statistic of the Query Profile in Snowflake?

- A. Time spent scanning the table partitions for data based on the predicate
- B. Time spent caching the data to remote storage in order to buffer the data being extracted and exported
- C. Time spent reading and writing data from and to remote storage when the data being accessed does not fit into the executing virtual warehouse node memory
- D. Time spent reading and writing data from and to remote storage when the data being accessed does not fit into either the virtual memory or the local disk

<details><summary>Show Answer</summary>
Correct Answer: D.

⚠ **Updated:** The original source listed C as correct, but current Snowflake documentation on Query Profile statistics defines "Local Disk IO" as time blocked by local disk access, and "Remote Disk IO" as time blocked by remote disk access — which only happens once data has already spilled past both memory *and* local disk. Option C stops at "memory," which actually describes local disk spilling, not remote. Option D correctly captures the two-stage spill (memory → local disk → remote disk).
</details>

---

### Question 712
What action can a user take to address query concurrency issues?

- A. Enable the search optimization service.
- B. Enable the query acceleration service.
- C. Add additional clusters to the virtual warehouse.
- D. Resize the virtual warehouse to a larger instance size.

<details><summary>Show Answer</summary>
Correct Answer: C. Adding clusters to a multi-cluster warehouse increases the number of queries that can run concurrently without queuing.
</details>

---

### Question 713
What does the Client redirect feature in Snowflake enable?

- A. A redirect of client connections to Snowflake accounts in the same regions for business continuity.
- B. A redirect of client connections to Snowflake accounts in different regions for business continuity.
- C. A redirect of client connections to Snowflake accounts in different regions for data replication.
- D. A redirect of client connections to Snowflake accounts in the same regions for data replication.

<details><summary>Show Answer</summary>
Correct Answer: B. Client redirect allows connections to fail over to a secondary account in a different region for business continuity/disaster recovery.
</details>

---

### Question 714
Which Snowflake feature can be used to find sensitive data in a table or column?

- A. Masking
- B. Data classification
- C. Row policies
- D. External functions

<details><summary>Show Answer</summary>
Correct Answer: B. Data classification scans and tags columns to identify sensitive data categories.
</details>

---

### Question 715
Which Snowflake feature allows a user to track sensitive data for compliance, discovery, protection, and resource usage?

- A. Object tagging
- B. Comments
- C. Internal tokenization
- D. Row access policies

<details><summary>Show Answer</summary>
Correct Answer: A. Object tagging lets users attach metadata to objects to support governance, compliance, and cost-tracking use cases.
</details>

---

### Question 716
Snowflake's hierarchical key model includes which keys? (Choose two.)

- A. Account master keys
- B. Database master keys
- C. File keys
- D. Secure view keys
- E. Schema master keys

<details><summary>Show Answer</summary>
Correct Answer: A, C. Snowflake's key hierarchy runs from a root key down through account master keys, table master keys, to individual file keys. Of the listed options, account master keys and file keys are genuine tiers.
</details>

---

### Question 717
What can the Snowflake SCIM API be used to manage? (Choose two.)

- A. Integrations
- B. Network policies
- C. Session policies
- D. Roles
- E. Users

<details><summary>Show Answer</summary>
Correct Answer: D, E. The SCIM API synchronizes users and roles from an external identity provider into Snowflake.
</details>

---

### Question 718
Which privilege is required to use the search optimization service in Snowflake?

- A. GRANT SEARCH OPTIMIZATION ON SCHEMA [schema_name] TO ROLE [role]
- B. GRANT SEARCH OPTIMIZATION ON DATABASE TO ROLE
- C. GRANT ADD SEARCH OPTIMIZATION ON SCHEMA [schema_name] TO ROLE [role]
- D. GRANT ADD SEARCH OPTIMIZATION ON DATABASE [database_name] TO ROLE [role]

<details><summary>Show Answer</summary>
Correct Answer: C. The ADD SEARCH OPTIMIZATION privilege must be granted at the schema (or database) level using this exact syntax.
</details>

---

### Question 719
What is the FASTEST way to bulk load data files from a Stage?

- A. Specifying a list of specific files to load
- B. Loading by path (internal stages)
- C. Using the Snowpipe REST API
- D. Using pattern matching to identify specific files by pattern

<details><summary>Show Answer</summary>
Correct Answer: B. Loading by referencing a stage path avoids the extra processing overhead of explicit file lists or pattern matching.
</details>

---

### Question 720
How does a Snowflake user extract the URL of a directory table on an external stage for further transformation?

- A. Use the SHOW STAGES command.
- B. Use the DESCRIBE STAGE command.
- C. Use the GET_PRESIGNED_URL function.
- D. Use the BUILD_STAGE_FILE_URL function.

<details><summary>Show Answer</summary>
Correct Answer: D. BUILD_STAGE_FILE_URL generates a permanent, Snowflake-authenticated URL for a staged file that can be used in further transformation logic.
</details>

---

### Question 721
A Snowflake user needs to share unstructured data from an internal stage to a reporting tool that does not have Snowflake access. Which file function should be used?

- A. BUILD_SCOPED_FILE_URL
- B. BUILD_STAGE_FILE_URL
- C. GET_PRESIGNED_URL
- D. GET_STAGE_LOCATION

<details><summary>Show Answer</summary>
Correct Answer: C. GET_PRESIGNED_URL creates a temporary URL that grants access without requiring the recipient to authenticate to Snowflake — ideal for external tools.
</details>

---

### Question 722
The use of which Snowflake table type will reduce costs when working with ETL workflows?

- A. Permanent
- B. Temporary
- C. Transient
- D. External

<details><summary>Show Answer</summary>
Correct Answer: C. Transient tables skip Fail-safe storage costs, making them cost-effective for intermediate ETL staging tables.
</details>

---

### Question 723
What is one of the characteristics of data shares?

- A. Data shares support full DML operations.
- B. Data shares work by copying data to consumer accounts.
- C. Data shares utilize secure views for sharing view objects.
- D. Data shares are cloud agnostic and can cross regions by default.

<details><summary>Show Answer</summary>
Correct Answer: C. Only secure views (not standard views) can be added to a share.
</details>

---

### Question 724
What is the MINIMUM configurable idle timeout value for a session policy in Snowflake?

- A. 2 minutes
- B. 5 minutes
- C. 10 minutes
- D. 15 minutes

<details><summary>Show Answer</summary>
Correct Answer: B. The minimum value for `SESSION_IDLE_TIMEOUT_MINS` in a session policy is 5 minutes.
</details>

---

### Question 725
Which command is used to unload data from a Snowflake table to an external stage?

- A. COPY INTO
- B. COPY INTO followed by GET
- C. GET
- D. COPY INTO followed by PUT

<details><summary>Show Answer</summary>
Correct Answer: A. `COPY INTO <location>` unloads table data directly to an external (or internal) stage.
</details>

---

### Question 726
What is a characteristic of materialized views in Snowflake?

- A. Materialized views do not allow joins.
- B. Clones of materialized views can be created directly by the user.
- C. Multiple tables can be joined in the underlying query of a materialized view.
- D. Aggregate functions can be used as window functions in materialized views.

<details><summary>Show Answer</summary>
Correct Answer: A. A materialized view can reference only a single base table, so joins are not supported.
</details>

---

### Question 727
Which Snowflake URL type allows users or applications to download or access files directly from a Snowflake stage without authentication?

- A. Directory
- B. File
- C. Pre-signed
- D. Scoped

<details><summary>Show Answer</summary>
Correct Answer: C. A pre-signed URL includes a temporary access token, letting a holder download the file without authenticating to Snowflake.
</details>

---

### Question 728
Which SQL command will download all the data files from an internal table stage named TBL_EMPLOYEE to a local windows directory on a client machine, in a folder named "folder with space" within the C drive?

- A. `GET @%TBL_EMPLOYEE file://C:\folder with space;`
- B. `GET @%TBL_EMPLOYEE 'file://C:\folder with space';`
- C. `PUT @%TBL_EMPLOYEE 'file://C:\folder with space';`
- D. `COPY INTO 'file://C:\folder with space' FROM @%TBL_EMPLOYEE;`

<details><summary>Show Answer</summary>
Correct Answer: B. GET downloads files from a stage to a local machine, and a path containing spaces must be quoted.
</details>

---

### Question 729
How can the COPY command be used to unload data from a table to an internal stage?

- A. COPY INTO [location]
- B. COPY INTO @stage
- C. COPY INTO [location] with single=true
- D. COPY INTO s3://[bucket]

<details><summary>Show Answer</summary>
Correct Answer: A. `COPY INTO <location>` is the general unload syntax, where the location can be an internal stage.
</details>

---

### Question 730
How does a Snowflake stored procedure compare to a User-Defined Function (UDF)?

- A. A single executable statement can call only two stored procedures. In contrast, a single SQL statement can call multiple UDFs.
- B. A single executable statement can call only one stored procedure. In contrast, a single SQL statement can call multiple UDFs.
- C. A single executable statement can call multiple stored procedures. In contrast, multiple SQL statements can call the same UDFs.
- D. Multiple executable statements can call more than one stored procedure. In contrast, a single SQL statement can call multiple UDFs.

<details><summary>Show Answer</summary>
Correct Answer: B. A statement can invoke only one stored procedure, whereas a single SQL statement can reference multiple UDFs.
</details>

---

### Question 731
Which command should be used to unload all the rows from a table into one or more files in a named stage?

- A. COPY INTO
- B. GET
- C. INSERT INTO
- D. EXPORT

<details><summary>Show Answer</summary>
Correct Answer: A. COPY INTO unloads table rows into files in a stage.
</details>

---

### Question 732
Which command is used to unload data from a table or move a query result to a stage?

- A. COPY INTO
- B. GET
- C. MERGE
- D. PUT

<details><summary>Show Answer</summary>
Correct Answer: A. COPY INTO handles both table unloads and unloading query results to a stage.
</details>

---

### Question 733
What privileges are necessary for a consumer in the Data Exchange to make a request and receive data? (Choose two.)

- A. CREATE DATABASE
- B. IMPORT SHARE
- C. OWNERSHIP
- D. REFERENCE_USAGE
- E. USAGE

<details><summary>Show Answer</summary>
Correct Answer: A, B. The consumer role needs CREATE DATABASE (to materialize the shared data) and IMPORT SHARE (to accept the share).
</details>

---

### Question 734
What are benefits of using Snowpark? (Choose two.)

- A. Snowpark uses a Spark engine to generate optimized SQL query plans.
- B. Snowpark automatically sets up Spark within Snowflake virtual warehouses.
- C. Snowpark does not require that a separate cluster be running outside of Snowflake.
- D. Snowpark allows users to run existing Spark code on virtual warehouses without the need to reconfigure the code.
- E. Snowpark pushes as much work as possible to the Snowflake database for all operations including User-Defined Functions (UDFs).

<details><summary>Show Answer</summary>
Correct Answer: C, E. Snowpark executes entirely within Snowflake's own compute (no external Spark cluster needed) and pushes computation, including UDFs, down into Snowflake.
</details>

---

### Question 735
What are Snowflake best practices when assigning the ACCOUNTADMIN role to users? (Choose two.)

- A. The ACCOUNTADMIN role should be assigned to at least two users.
- B. The ACCOUNTADMIN role should be used to create Snowflake objects.
- C. The ACCOUNTADMIN role should be used for running automated scripts.
- D. The ACCOUNTADMIN role should be given to any user who needs a high level of authority.
- E. All users assigned the ACCOUNTADMIN role should use Multi-Factor Authentication (MFA).

<details><summary>Show Answer</summary>
Correct Answer: A, E. Best practice is to assign ACCOUNTADMIN to at least two users (for continuity) and to require MFA for all of them.
</details>

---

### Question 736
What is a recommended approach for optimizing query performance in Snowflake?

- A. Use subqueries whenever possible.
- B. Use a number of joins to combine data from multiple tables.
- C. Select all columns from tables, even if they are not needed in the query.
- D. Use a smaller number of larger tables rather than a larger number of smaller tables.

<details><summary>Show Answer</summary>
Correct Answer: D. Fewer, larger tables reduce join overhead and simplify query planning compared to many small tables.
</details>

---

### Question 737
When using SnowSQL, which configuration options are required when unloading data via a SQL query run on a local machine? (Choose two.)

- A. connection
- B. quiet
- C. output_file
- D. output_format
- E. header

<details><summary>Show Answer</summary>
Correct Answer: C, D. `output_file` and `output_format` are required to control where and how SnowSQL writes the unloaded data locally.
</details>

---

### Question 738
Which Snowflake view is used to support compliance auditing?

- A. ACCESS_HISTORY
- B. COPY_HISTORY
- C. QUERY_HISTORY
- D. LOGIN_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: A. ACCESS_HISTORY records read/write activity against data, supporting compliance auditing.
</details>

---

### Question 739
How can a Snowflake user load duplicate files with a COPY INTO command?

- A. The COPY INTO options should be set to PURGE = FALSE
- B. The COPY INTO options should be set to FORCE = TRUE
- C. The COPY INTO options should be set to REPLACE = FALSE
- D. The COPY INTO options should be ON_ERROR = CONTINUE

<details><summary>Show Answer</summary>
Correct Answer: B. FORCE = TRUE tells COPY INTO to reload files even if they were already loaded and recorded in load metadata.
</details>

---

### Question 740
What is an advantage of using a multi-cluster virtual warehouse as compared to a single-cluster virtual warehouse in Snowflake?

- A. A user can auto-suspend a running warehouse due to inactivity.
- B. A user can specify a warehouse size while configuring it for use.
- C. A user can resize a warehouse at any time whether running or not.
- D. A user can specify the maximum and minimum number of clusters.

<details><summary>Show Answer</summary>
Correct Answer: D. Multi-cluster warehouses uniquely allow configuring a minimum and maximum cluster count for automatic scaling.
</details>

---

### Question 741
Which transformation techniques are supported for bulk loading data into Snowflake using the COPY INTO [table] command? (Choose two.)

- A. Column grouping
- B. Column omission
- C. Column reordering
- D. Column aggregation
- E. Selection of a limited number of rows

<details><summary>Show Answer</summary>
Correct Answer: B, C. COPY INTO [table] supports column reordering and column omission during a load; it does not support aggregation, grouping, or row limiting.
</details>

---

### Question 742
Which type of charts are supported by Snowsight? (Choose two.)

- A. Flowcharts
- B. Gantt charts
- C. Line charts
- D. Pie charts
- E. Scorecards

<details><summary>Show Answer</summary>
Correct Answer: C, E. Snowsight dashboards support chart types such as line charts and scorecards, among others.
</details>

---

### Question 743
A user wants to upload a file to an internal Snowflake stage using a PUT command. Which tools and/or connectors could be used to execute this command? (Choose two.)

- A. SnowCD
- B. SnowSQL
- C. SQL API
- D. Python connector
- E. Worksheets

<details><summary>Show Answer</summary>
Correct Answer: B, D. PUT is a client-side command supported by SnowSQL and the Snowflake drivers/connectors (e.g., Python), not by the SQL API or Snowsight worksheets.
</details>

---

### Question 744
Which Snowflake table is an implicit object layered on a stage, where the stage can be either internal or external?

- A. Directory table
- B. Temporary table
- C. Transient table
- D. A table with a materialized view

<details><summary>Show Answer</summary>
Correct Answer: A. A directory table is not a standalone object — it is implicitly layered on top of a stage to expose file-level metadata.
</details>

---

### Question 745
The Query Profile in the image is for a query executed in Snowsight. Four of the key nodes are highlighted in yellow. Which highlighted node will be the MOST expensive?

- A. Aggregate[1]
- B. Join[5]
- C. TableScan[2]
- D. TableScan[3]

<details><summary>Show Answer</summary>
Correct Answer: D. *(This question depends on a Query Profile screenshot that was not included in the source material, so the cost comparison cannot be independently re-verified here — the original answer is retained as-is.)*
</details>

---

### Question 746
What is a characteristic of the maintenance of a materialized view?

- A. Materialized views cannot be refreshed automatically.
- B. An additional set of scripts is needed to refresh data in materialized views.
- C. A materialized view is automatically refreshed by a Snowflake managed warehouse.
- D. A materialized view can be set up with the auto-refresh feature using the SQL SET command.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowflake automatically maintains materialized views using background, Snowflake-managed compute, with no user scripts required.
</details>

---

### Question 747
Which command should be used to implement a masking policy that was already created in Snowflake?

- A. ALTER MASKING POLICY
- B. APPLY MASKING POLICY
- C. CREATE MASKING POLICY
- D. ALTER TABLE [table_name] MODIFY COLUMN [column_name] SET MASKING POLICY [policy_name]

<details><summary>Show Answer</summary>
Correct Answer: D. Attaching an already-created masking policy to a column requires an ALTER TABLE ... MODIFY COLUMN ... SET MASKING POLICY statement.
</details>

---

### Question 748
A Snowflake user runs a query for 36 seconds on a size 2XL virtual warehouse. What would be the credit consumption?

- A. Snowflake will charge for 36 seconds at the rate of 32 credits per hour.
- B. Snowflake will charge for 36 seconds at the rate of 64 credits per hour.
- C. Snowflake will charge for 60 seconds at the rate of 32 credits per hour.
- D. Snowflake will charge for 60 seconds at the rate of 64 credits per hour.

<details><summary>Show Answer</summary>
Correct Answer: C. A 2X-Large warehouse consumes 32 credits/hour, and Snowflake bills a 60-second minimum for each time the warehouse starts running.
</details>

---

### Question 749
Which statement accurately describes a characteristic of a materialized view?

- A. A materialized view can query only a single table.
- B. Data accessed through materialized views can be stale.
- C. Materialized view refreshes need to be maintained by the user.
- D. Querying a materialized view is slower than executing a query against the base table of the view.

<details><summary>Show Answer</summary>
Correct Answer: A. Materialized views are restricted to querying a single base table.
</details>

---

### Question 750
The use of which Snowflake table type will reduce costs when working with ETL workflows?

- A. Permanent
- B. Temporary
- C. Transient
- D. External

<details><summary>Show Answer</summary>
Correct Answer: C. Transient tables avoid Fail-safe storage costs, making them well-suited to transient ETL staging data.
</details>

---

### Question 751
A user wants to unload data from a relational table into a CSV file in an external stage. The table must be named exactly as specified by the user. Which file format option MUST be used to do this?

- A. encoding
- B. escape
- C. single = true
- D. file_extension

<details><summary>Show Answer</summary>
Correct Answer: C. Setting `single = true` produces one output file with a user-specified name, instead of Snowflake's default auto-generated, multi-part file names.
</details>

---

### Question 752
Which account usage view in Snowflake can be used to identify the most-frequently accessed tables?

- A. Access_History
- B. Object_Dependencies
- C. Tables
- D. Query_History

<details><summary>Show Answer</summary>
Correct Answer: A. ACCESS_HISTORY records which objects were read or written by each query, making it possible to identify frequently accessed tables.
</details>

---

### Question 753
What metadata does Snowflake store concerning all rows stored in a micro-partition? (Choose two.)

- A. A count of the number of total values in the micro-partition
- B. The range of values for each partition in the micro-partition
- C. The range of values for each of the rows in the micro-partition
- D. The range of values for each of the columns in the micro-partition
- E. The number of distinct values for each column in the micro-partition

<details><summary>Show Answer</summary>
Correct Answer: D, E. For each micro-partition, Snowflake stores the range of values and the count of distinct values, per column.
</details>

---

### Question 754
What role has the privileges to create and manage data shares by default?

- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: A. By default, only ACCOUNTADMIN (or a role explicitly granted the CREATE SHARE global privilege) can create and manage shares.
</details>

---

### Question 755
Which function determines the kind of value stored in a VARIANT column?

- A. CHECK_JSON
- B. IS_ARRAY
- C. IS_JSON
- D. TYPEOF

<details><summary>Show Answer</summary>
Correct Answer: D. TYPEOF returns the underlying data type of a value stored in a VARIANT column.
</details>

---

### Question 756
What operation can be performed using Time Travel?

- A. Restoring tables that have been dropped from a data share
- B. Extending a permanent table's retention duration from 90 to 100 days
- C. Creating a clone of an entire table at a point in the past from a permanent table
- D. Disabling Time Travel for a specific object by setting to NULL

<details><summary>Show Answer</summary>
Correct Answer: C. Time Travel supports cloning a table as it existed at a specific historical point in time.
</details>

---

### Question 757
What are characteristics of Snowflake directory tables? (Choose two.)

- A. Directory tables are separate database objects.
- B. Directory tables can only be used with an external stage.
- C. Directory tables contain data stored in binary format.
- D. Directory tables store file-level metadata about the data files in a stage.
- E. A directory table can be added explicitly to a stage when the stage is created, or later.

<details><summary>Show Answer</summary>
Correct Answer: D, E. Directory tables store file-level metadata for a stage and can be enabled either at stage creation or afterward via ALTER STAGE.
</details>

---

### Question 758
What does the VARIANT data type impose a 16 MB size limit on?

- A. All rows
- B. All columns
- C. Individual rows
- D. Individual columns

<details><summary>Show Answer</summary>
Correct Answer: C. The 16 MB limit applies to each individual VARIANT value (i.e., per row).
</details>

---

### Question 759
Which activities are included in the Cloud Services layer? (Choose two.)

- A. Data storage
- B. Dynamic data masking
- C. Partition scanning
- D. User authentication
- E. Infrastructure management

<details><summary>Show Answer</summary>
Correct Answer: D, E. Authentication and infrastructure management are handled by the Cloud Services layer, distinct from storage or compute.
</details>

---

### Question 760
What does the "scanned from cache" represent in the Query profile?

- A. The percentage of data scanned from the query cache
- B. The percentage of data scanned from the result cache
- C. The percentage of data scanned from the remote disk cache
- D. The percentage of data scanned from the local disk cache

<details><summary>Show Answer</summary>
Correct Answer: D. "Percentage scanned from cache" reflects the share of data read from the warehouse's local disk (SSD) cache instead of remote storage.
</details>

---

### Question 761
Which role has the ability to create a share from a shared database by default?

- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. ORGADMIN

<details><summary>Show Answer</summary>
Correct Answer: A. By default, ACCOUNTADMIN holds the global CREATE SHARE privilege needed to create and manage shares. (Note: Snowflake does not allow directly re-sharing a database or objects that were themselves received via a share — this question is best read as asking which role manages sharing by default.)
</details>

---

### Question 762
Which object-level parameters can be set to help control query processing and concurrency? (Choose two.)

- A. MAX_CONCURRENCY_LEVEL
- B. STATEMENT_QUEUED_TIMEOUT_IN_SECONDS
- C. STATEMENT_TIMEOUT_IN_SECONDS
- D. MAX_STATEMENT_TIME
- E. WAREHOUSE_SIZE

<details><summary>Show Answer</summary>
Correct Answer: B, C. These two parameters control how long a statement can queue and how long it can run before timing out.
</details>

---

### Question 763
What metadata does Snowflake store for micro-partitions? (Choose two.)

- A. Range of values
- B. Distinct values
- C. Index values
- D. Sorted values
- E. Null values

<details><summary>Show Answer</summary>
Correct Answer: A, B. Snowflake tracks the range of values and count of distinct values per column for each micro-partition.
</details>

---

### Question 764
What are valid sub-clauses to the OVER clause for a window function? (Choose two.)

- A. GROUP BY
- B. LIMIT
- C. ORDER BY
- D. PARTITION BY
- E. UNION ALL

<details><summary>Show Answer</summary>
Correct Answer: C, D. Window functions use PARTITION BY and ORDER BY within the OVER clause.
</details>

---

### Question 765
Which kind of Snowflake table stores file-level metadata for each file in a stage?

- A. Directory
- B. External
- C. Temporary
- D. Transient

<details><summary>Show Answer</summary>
Correct Answer: A. A directory table stores file-level metadata for the files in its associated stage.
</details>

---

### Question 766
Which privileges apply to stored procedures? (Choose two.)

- A. MODIFY
- B. MONITOR
- C. OPERATE
- D. OWNERSHIP
- E. USAGE

<details><summary>Show Answer</summary>
Correct Answer: D, E. Stored procedures support OWNERSHIP and USAGE privileges.
</details>

---

### Question 767
What column type does a Kafka connector store formatted information in a single column?

- A. ARRAY
- B. OBJECT
- C. VARCHAR
- D. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: D. The Kafka connector loads each message's contents into a single VARIANT column.
</details>

---

### Question 768
If a size Small virtual warehouse costs two credits per hour, what is the credit cost per hour of a size Large virtual warehouse?

- A. 4
- B. 8
- C. 16
- D. 32

<details><summary>Show Answer</summary>
Correct Answer: B. Warehouse credit cost doubles with each size increase: XS=1, S=2, M=4, L=8 credits/hour.
</details>

---

### Question 769
Which SQL command will list the files in a named stage?

- A. `list @my_stage;`
- B. `get @my_stage;`
- C. `list my_stage;`
- D. `get my_stage;`

<details><summary>Show Answer</summary>
Correct Answer: A. `LIST @my_stage;` lists the files present in the named stage (the `@` prefix is required).
</details>

---

### Question 770
What is the effect of configuring a virtual warehouse auto-suspend value to 0 or NULL?

- A. The warehouse will never suspend automatically.
- B. The warehouse will suspend immediately upon work completion.
- C. The warehouse will not resume automatically.
- D. All clusters in the multi-cluster warehouse will resume immediately.

<details><summary>Show Answer</summary>
Correct Answer: A. Setting auto-suspend to 0 or NULL disables automatic suspension, so the warehouse keeps running (and billing) until manually suspended.
</details>

---

### Question 771
Which data types can be used in Snowflake to store semi-structured data? (Choose two.)

- A. ARRAY
- B. BLOB
- C. CLOB
- D. JSON
- E. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: A, E. ARRAY and VARIANT are Snowflake's semi-structured data types (alongside OBJECT).
</details>

---

### Question 772
While attempting to prevent data duplication, which COPY INTO [location] option should be used to load files with expired load metadata?

- A. PURGE
- B. FORCE
- C. VALIDATION_MODE
- D. LOAD_UNCERTAIN_FILES

<details><summary>Show Answer</summary>
Correct Answer: B. FORCE reloads files even when their load history/metadata has expired or already shows them as loaded.
</details>

---

### Question 773
What service is provided as an integrated Snowflake feature to enhance Multi-Factor Authentication (MFA) support?

- A. Duo Security
- B. OAuth
- C. Okta
- D. Single Sign-on (SSO)

<details><summary>Show Answer</summary>
Correct Answer: A. Snowflake's built-in MFA is powered by Duo Security.
</details>

---

### Question 774
What is the impact on queries that are being executed when a resource monitor set to the "Notify & Suspend" threshold level is exceeded?

- A. All statements being executed are queued.
- B. All statements being executed are restarted.
- C. All statements being executed are cancelled.
- D. All statements being executed are allowed to complete.

<details><summary>Show Answer</summary>
Correct Answer: D. "Notify & Suspend" lets in-flight queries finish, while blocking any new queries from starting.
</details>

---

### Question 775
What tasks can an account administrator perform in the Data Exchange? (Choose two.)

- A. Add and remove members.
- B. Delete data categories.
- C. Approve and deny listing approval requests.
- D. Transfer listing ownership.
- E. Transfer ownership of a provider profile.

<details><summary>Show Answer</summary>
Correct Answer: A, C. Data Exchange administrators manage membership and approve/deny listing requests.
</details>

---

### Question 776
Which types of subqueries does Snowflake support? (Choose two.)

- A. Scalar subqueries in WHERE clauses
- B. Uncorrelated scalar subqueries in any place that a value expression can be used
- C. EXISTS, ANY/ALL, and IN subqueries in WHERE clauses; these subqueries can be uncorrelated only
- D. EXISTS, ANY/ALL, and IN subqueries in WHERE clauses; these can be correlated only
- E. EXISTS, ANY/ALL, and IN subqueries in WHERE clauses; these subqueries can be correlated or uncorrelated

<details><summary>Show Answer</summary>
Correct Answer: B, E. Snowflake supports uncorrelated scalar subqueries anywhere a value expression is valid, and EXISTS/ANY/ALL/IN subqueries that may be correlated or uncorrelated.
</details>

---

### Question 777
How can network and private connectivity security be managed in Snowflake?

- A. By setting up network policies with IPv4 IP addresses
- B. By putting the URL on the allowed list for get method responses
- C. By manually setting up vulnerability patch management policies
- D. By manually setting up an Intrusion Prevention System (IPS) on each account

<details><summary>Show Answer</summary>
Correct Answer: A. Network policies built from allowed/blocked IPv4 addresses (and network rules) are Snowflake's mechanism for controlling network access.
</details>

---

### Question 778
What consideration should be made when loading data into Snowflake?

- A. Create small data files and stage them in cloud storage frequently.
- B. Create large data files to maximize the processing overhead for each file.
- C. The number of load operations that run in parallel can exceed the number of data files to be loaded.
- D. The number of data files that are processed in parallel is determined by the virtual warehouse.

<details><summary>Show Answer</summary>
Correct Answer: D. The virtual warehouse's size determines how many data files can be processed in parallel during a load.
</details>

---

### Question 779
How can a user improve the performance of a single large complex query in Snowflake?

- A. Scale up the virtual warehouse.
- B. Scale out the virtual warehouse.
- C. Enable standard warehouse scaling.
- D. Enable economy scaling.

<details><summary>Show Answer</summary>
Correct Answer: A. Scaling up (increasing warehouse size) adds compute/memory to a single query, whereas scaling out (multi-cluster) helps with concurrency, not single-query speed.
</details>

---

### Question 780
Who can access a referenced file through a scoped URL?

- A. Only the ACCOUNTADMIN
- B. Only the user who generates the URL
- C. Any role specified in GET REST API call with sufficient privileges
- D. Any user specified in the GET REST API call with sufficient privileges

<details><summary>Show Answer</summary>
Correct Answer: B. A scoped URL is tied to the session/user that generated it and cannot be used by anyone else.
</details>

---

### Question 781
Snowflake will return an error when a user attempts to share which object?

- A. Tables
- B. Secure views
- C. Standard views
- D. Secure materialized views

<details><summary>Show Answer</summary>
Correct Answer: C. Only secure views (and secure materialized views/UDFs) can be added to a share; attempting to share a standard view returns an error. This matches current Snowflake documentation.
</details>

---

### Question 782
What setting in Snowsight determines the databases, tables, and other objects that can be seen and the actions that can be performed on them?

- A. Active role
- B. Masking policy
- C. Column-level security
- D. Multi-Factor Authentication (MFA)

<details><summary>Show Answer</summary>
Correct Answer: A. The user's currently active role governs which objects are visible and which actions are permitted in Snowsight.
</details>

---

### Question 783
Why would a Snowflake user decide to use a materialized view instead of a regular view?

- A. The base tables do not change frequently.
- B. The results of the view change often.
- C. The query is not resource intensive.
- D. The query results are not used frequently.

<details><summary>Show Answer</summary>
Correct Answer: A. Materialized views are most beneficial when the underlying data changes infrequently but the (expensive) query is run often.
</details>

---

### Question 784
When a database is cloned, which objects in the clone inherit all granted privileges from the source object? (Choose two.)

- A. Account
- B. Database
- C. Schemas
- D. Tables
- E. Internal named stages

<details><summary>Show Answer</summary>
Correct Answer: C, D. Objects contained within a cloned database — such as schemas and tables — retain the privileges granted on their source objects; the cloned database itself does not inherit privileges granted on the source database.
</details>

---

### Question 785
How does the Access_History view enhance overall data governance pertaining to read and write operations? (Choose two.)

- A. Shows how accessed data was moved from the source to the target objects.
- B. Provides a unified picture of what data was accessed and when it was accessed.
- C. Protects sensitive data from unauthorized access while allowing authorized users to access it at query runtime.
- D. Identifies columns with personal information and tags them so masking policies can be applied to protect sensitive data.
- E. Determines whether a given row in a table can be accessed by the user by filtering the data based on a given policy.

<details><summary>Show Answer</summary>
Correct Answer: A, B. ACCESS_HISTORY tracks data lineage (source-to-target movement) and gives a unified record of what was accessed and when.
</details>

---

### Question 786
What does Snowflake recommend a user do if they need to connect to Snowflake with a tool or technology that is not listed in Snowflake's partner ecosystem?

- A. Use Snowflake's native API.
- B. Use a custom-built connector.
- C. Contact Snowflake Support for a new driver.
- D. Connect through Snowflake's JDBC or ODBC drivers.

<details><summary>Show Answer</summary>
Correct Answer: D. For tools outside the certified partner ecosystem, Snowflake recommends connecting via its standard JDBC or ODBC drivers.
</details>

---

### Question 787
What is the expiration period for a file URL used to access unstructured data in cloud storage?

- A. The remainder of the session
- B. An unlimited amount of time
- C. The length of time specified in the expiration_time
- D. The same length of time as the expiration period for the query results cache

<details><summary>Show Answer</summary>
Correct Answer: B. Unlike scoped or pre-signed URLs, a file URL does not expire.
</details>

---

### Question 788
Which applications can use key pair authentication? (Choose two.)

- A. Snowflake Marketplace
- B. SnowCD
- C. Snowsight
- D. SnowSQL
- E. Snowflake connector for Python

<details><summary>Show Answer</summary>
Correct Answer: D, E. Key pair authentication is supported by client tools such as SnowSQL and the Python connector.
</details>

---

### Question 789
Which commands can only be executed using SnowSQL? (Choose two.)

- A. COPY INTO
- B. GET
- C. LIST
- D. PUT
- E. REMOVE

<details><summary>Show Answer</summary>
Correct Answer: B, D. GET and PUT are client-side file transfer commands that require a client such as SnowSQL or a driver — they cannot run through Snowsight worksheets.
</details>

---

### Question 790
A user has enabled the STRIP_OUTER_ARRAY file format option for the COPY INTO {table} command. What else will this format option and command do?

- A. Load the records into separate table rows.
- B. Unload the records from separate table rows.
- C. Load data files in smaller chunks.
- D. Ensure each unique element stores values of a single native data type.

<details><summary>Show Answer</summary>
Correct Answer: A. STRIP_OUTER_ARRAY removes the outer array structure from JSON so each element loads as its own row.
</details>

---

### Question 791
Which objects will incur storage costs associated with Fail-safe?

- A. Temporary tables
- B. Permanent tables
- C. Data files available in internal stages
- D. Data files available in external stages

<details><summary>Show Answer</summary>
Correct Answer: B. Only permanent tables have a Fail-safe period, which incurs additional storage costs.
</details>

---

### Question 792
What technique does Snowflake use to limit the number of micro-partitions scanned by each query?

- A. B-tree
- B. Indexing
- C. Map reduce
- D. Pruning

<details><summary>Show Answer</summary>
Correct Answer: D. Pruning uses stored micro-partition metadata to skip partitions that can't match the query's filter predicates.
</details>

---

### Question 793
What activities can a user with the ORGADMIN role perform? (Choose two.)

- A. Create an INFORMATION_SCHEMA in a database.
- B. View usage information for all accounts in the organization.
- C. Enable database cloning for an account in the organization.
- D. Enable database replication for an account in the organization.
- E. View micro-partition information for all accounts in the organization.

<details><summary>Show Answer</summary>
Correct Answer: B, D. ORGADMIN can view organization-wide usage information and enable database replication across accounts in the organization.
</details>

---

### Question 794
In a managed access schema, who can grant privileges on objects in the schema to other roles? (Choose two.)

- A. The schema owner role
- B. The ORGADMIN system role
- C. The system role
- D. The role with the MANAGE GRANTS privilege
- E. The role that owns the object in the schema

<details><summary>Show Answer</summary>
Correct Answer: A, D. In a managed access schema, only the schema owner role or a role with the global MANAGE GRANTS privilege can grant privileges — individual object owners can no longer do so.
</details>

---

### Question 795
What are the recommended steps to optimize a SQL query due to data spilling? (Choose two.)

- A. Clone the base table.
- B. Fetch required attributes only.
- C. Use a larger virtual warehouse.
- D. Process the data in smaller batches.
- E. Add another cluster in the virtual warehouse.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Reducing the columns/rows fetched and using a larger warehouse (more memory/local disk) both reduce or eliminate spilling.
</details>

---

### Question 796
A Snowflake user wants to share unstructured data through the use of secure views. Which URL types can be used? (Choose two.)

- A. Scoped URL
- B. HTTPS URL
- C. Cloud storage URL
- D. File URL
- E. Pre-signed URL

<details><summary>Show Answer</summary>
Correct Answer: A, E. Scoped URLs and pre-signed URLs are the two file-access URL types compatible with sharing unstructured data via secure views.
</details>

---

### Question 797
What are characteristics of reader accounts in Snowflake? (Choose two.)

- A. Reader account users cannot add new data to the account.
- B. Reader account users can share data to other reader accounts.
- C. A single reader account can consume data from multiple provider accounts.
- D. Data consumers are responsible for reader account setup and data usage costs.
- E. Reader accounts enable data consumers to access and query data shared by the provider.

<details><summary>Show Answer</summary>
Correct Answer: A, E. Reader account users can only query shared data (no new data can be added), and the whole point of a reader account is to let a consumer without their own Snowflake account query the provider's shared data. (Note: it is the *provider*, not the consumer, who is responsible for reader account setup and costs, which is why D is incorrect.)
</details>

---

### Question 798
Why should a Snowflake user configure a Secure view? (Choose two.)

- A. To encrypt the data in transit.
- B. To execute faster than a standard view.
- C. To protect hidden data from other users.
- D. To improve the performance of a query.
- E. To hide the view definition from unauthorized users.

<details><summary>Show Answer</summary>
Correct Answer: C, E. Secure views protect underlying data from being inferred by unauthorized users and hide the view's SQL definition from them. (Secure views typically run slower than standard views, not faster.)
</details>

---

### Question 799
Which activities are managed by Snowflake's Cloud Services layer?

- A. Authentication
- B. Access delegation
- C. Data pruning
- D. Data compression
- E. Query parsing and optimization

<details><summary>Show Answer</summary>
Correct Answer: A, E. Authentication and query parsing/optimization are functions of the Cloud Services layer.
</details>

---

### Question 800
The COPY INTO [location] command can unload data from a table directly into which locations? (Choose two.)

- A. A named internal stage
- B. A Snowpipe REST endpoint
- C. A network share on a client machine
- D. A local directory or folder on a client machine
- E. A named external stage that references an external cloud location

<details><summary>Show Answer</summary>
Correct Answer: A, E. COPY INTO [location] unloads directly to internal or external named stages — not to Snowpipe endpoints or local/network file systems (those require a separate GET after unloading to a stage).
</details>

---



====================================================================================================
# SnowPro_801-900.md
====================================================================================================

# SnowPro Core Practice Questions — Batch 9 (Q801–Q900)

*Cleaned, reformatted, and cross-checked against current Snowflake documentation (as of July 2026). Answers are hidden in collapsible blocks — click "Show Answer" to reveal. Items with a ⚠ **Updated** note had an answer correction or an important clarification versus the original source.*

---

### Question 801
What does the Activity area of Snowsight allow users to do? (Choose two.)
- A. Schedule automated data backups.
- B. Monitor each step of an executed query.
- C. Monitor queries executed by users in an account.
- D. Create and manage user roles and permissions.
- E. Explore Snowflake Marketplace to find and integrate data.

<details><summary>Show Answer</summary>
Correct Answer: B, C. The Activity area (Query History / Copy History) lets you inspect the execution steps of a query and monitor queries run by others in the account.
</details>

---

### Question 802
In which Snowsight section can a user switch roles, modify their profile, and access documentation?
- A. The user menu
- B. The activity page
- C. The content pane
- D. The worksheets

<details><summary>Show Answer</summary>
Correct Answer: A. The user menu.
</details>

---

### Question 803
What is the recommended way to change the existing file format type in my_format from CSV to JSON?
- A. ALTER FILE FORMAT my_format SET TYPE=JSON;
- B. ALTER FILE FORMAT my_format SWAP TYPE WITH JSON;
- C. CREATE OR REPLACE FILE FORMAT my_format TYPE=JSON;
- D. REPLACE FILE FORMAT my_format TYPE=JSON;

<details><summary>Show Answer</summary>
Correct Answer: C. ALTER FILE FORMAT cannot change the TYPE property — the file format must be recreated.
</details>

---

### Question 804
Which features are included in Snowsight? (Choose two.)
- A. Worksheet sharing
- B. Referencing SnowSQL
- C. Exploring the Marketplace
- D. Changing the Snowflake account cloud provider
- E. Downloading query result data larger than 100 MB

<details><summary>Show Answer</summary>
Correct Answer: A, C.
</details>

---

### Question 805
How long can data that has a pre-signed URL access data files using Snowflake?
- A. Indefinitely
- B. Until the session ends
- C. Until the retention_time is met
- D. Until the expiration_time is exceeded

<details><summary>Show Answer</summary>
Correct Answer: D. Pre-signed URLs are generated with a specified expiration time.
</details>

---

### Question 806
What mechanisms can be used to inform Snowpipe that there are staged files available to load into a Snowflake table? (Choose two.)
- A. Cloud messaging
- B. Email integrations
- C. Error notifications
- D. REST endpoints
- E. Snowsight interactions

<details><summary>Show Answer</summary>
Correct Answer: A, D. Snowpipe can be triggered via cloud provider event notifications (auto-ingest) or by calling the REST API endpoints directly.
</details>

---

### Question 807
A Snowflake user needs to import a JSON file larger than 16 MB. What file format option could be used?
- A. trim_space = true
- B. compression = auto
- C. strip_outer_array = true
- D. ignore_utf8_errors = false

<details><summary>Show Answer</summary>
Correct Answer: C. Stripping the outer array lets Snowflake load each element as a separate row, avoiding the single-row VARIANT size limit.
</details>

---

### Question 808
What is a feature of column-level security in Snowflake?
- A. Row access policies
- B. Network policies
- C. Internal tokenization
- D. External tokenization

<details><summary>Show Answer</summary>
Correct Answer: D. Column-level security includes dynamic data masking and external tokenization; row access policies are row-level (not column-level) security.
</details>

---

### Question 809
Which common query problems can the Query Profile help a user identify and troubleshoot? (Choose two.)
- A. When Window functions are used incorrectly
- B. When there are exploding joins
- C. When there is a UNION without ALL
- D. When the SELECT DISTINCT command returns too many values
- E. When there are Common Table Expressions (CTEs) without a final SELECT statement

<details><summary>Show Answer</summary>
Correct Answer: B, C.
</details>

---

### Question 810
What is the Fail-safe retention period for permanent tables?
- A. 0 days
- B. 1 day
- C. 7 days
- D. 90 days

<details><summary>Show Answer</summary>
Correct Answer: C. Fail-safe is a fixed, non-configurable 7-day period following the Time Travel retention period for permanent tables.
</details>

---

### Question 811
Which features can be enabled by calling the SYSTEM$GLOBAL_ACCOUNT_SET_PARAMETER function by a user with the ORGADMIN role? (Choose two.)
- A. Clustering
- B. Client redirect
- C. Fail-safe
- D. Search optimization service
- E. Account and database replication

<details><summary>Show Answer</summary>
Correct Answer: B, E. This function toggles the ENABLE_ACCOUNT_DATABASE_REPLICATION and ENABLE_CLIENT_REDIRECT organization-level parameters.
</details>

---

### Question 812
What are characteristics of directory tables when used with unstructured data? (Choose two.)
- A. Only Cloud Storage Stages support directory tables.
- B. Each directory table has grantable privileges of its own.
- C. Directory tables store a catalog of staged files in cloud storage.
- D. A directory table can be added explicitly to a stage when the stage is created.
- E. A directory table is a separate database object that can be layered explicitly on a stage.

<details><summary>Show Answer</summary>
Correct Answer: C, D. A directory table is not a standalone object with its own privileges — it's an implicit catalog layered onto a stage via the `DIRECTORY = (ENABLE = TRUE)` parameter, either at creation or via ALTER STAGE.
</details>

---

### Question 813
Snowflake best practice recommends that which role be used to enforce a network policy on a Snowflake account?
- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 814
What is the default behavior of internal stages in Snowflake?
- A. Named internal stages are created by default.
- B. Users manually create their internal stages.
- C. Data files are automatically staged to a default location.
- D. Each user and table are automatically allocated an internal stage.

<details><summary>Show Answer</summary>
Correct Answer: D. Every user gets a user stage (`@~`) and every table gets a table stage automatically; named stages must be created manually.
</details>

---

### Question 815
The MAXIMUM size for a serverless task run is equivalent to what size virtual warehouse?
- A. Medium
- B. Large
- C. 2X-Large
- D. 4X-Large

<details><summary>Show Answer</summary>
Correct Answer: C. Confirmed current: Snowflake documentation states the maximum size for a serverless task run is equivalent to an XXLARGE (2X-Large) warehouse.
</details>

---

### Question 816
What storage cost is completely eliminated when a Snowflake table is defined as transient?
- A. Active
- B. Fail-safe
- C. Staged
- D. Time Travel

<details><summary>Show Answer</summary>
Correct Answer: B. Transient tables have no Fail-safe period (0 days); they still incur active storage and (limited) Time Travel costs.
</details>

---

### Question 817
How can a Snowflake user traverse semi-structured data?
- A. Insert a colon (:) between the VARIANT column name and any first-level element.
- B. Insert a colon (:) between the VARIANT column name and any second-level element.
- C. Insert a double colon (::) between the VARIANT column name and any first-level element.
- D. Insert a double colon (::) between the VARIANT column name and any second-level element.

<details><summary>Show Answer</summary>
Correct Answer: A. A single colon accesses the first-level element; dot or bracket notation continues traversal, and `::` is used for type casting, not traversal.
</details>

---

### Question 818
Based on Snowflake recommendations, when creating a hierarchy of custom roles, the top-most custom role should be assigned to which role?
- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 819
What happens to the privileges granted to Snowflake system-defined roles?
- A. The privileges cannot be revoked.
- B. The privileges can be revoked by an ACCOUNTADMIN.
- C. The privileges can be revoked by an ORGADMIN.
- D. The privileges can be revoked by any user-defined role with appropriate privileges.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 820
By default, which role allows a user to manage a Snowflake Data Exchange share?
- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 821
How does the PARTITION BY option affect an expression for a COPY INTO [location] command?
- A. The unload operation partitions table data into separate files for the specified table.
- B. The unload operation partitions table rows into separate files unloaded to the specified stage.
- C. A single file will be loaded with a user-defined partition key and the user can use this partition key for clustering.
- D. A single file will be loaded with a Snowflake-defined partition key and Snowflake will use this key for pruning.

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 822
How does Snowflake improve the performance of queries that are designed to filter out a significant amount of data?
- A. The use of indexing
- B. The use of pruning
- C. The use of TableScan
- D. By increasing the number of partitions scanned

<details><summary>Show Answer</summary>
Correct Answer: B. Micro-partition metadata allows Snowflake to prune (skip) partitions that can't match the filter.
</details>

---

### Question 823
A JSON document is stored in the source_column of type VARIANT. The document has an array called elements. The array contains the name key that has a string value. How can a Snowflake user extract the name from the first element?
- A. select source_column.elements[0].name
- B. select source_column:elements.name[0]
- C. select source_column:elements[0].name
- D. select source_column.elements.name[0]

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 824
Which function should be used to insert JSON formatted string data into a VARIANT field?
- A. FLATTEN
- B. CHECK_JSON
- C. PARSE_JSON
- D. TO_VARIANT

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 825
Which permission on a Snowflake virtual warehouse allows the role to resize the warehouse?
- A. ALTER
- B. MODIFY
- C. MONITOR
- D. USAGE

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 826
What is it called when a customer managed key is combined with a Snowflake managed key to create a composite key for encryption?
- A. Hierarchical key model
- B. Client-side encryption
- C. Tri-secret Secure encryption
- D. Key pair authentication

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 827
What is the COPY INTO [location] command option default for unloading data into multiple files?
- A. SINGLE = TRUE
- B. SINGLE = NULL
- C. SINGLE = FALSE
- D. MULTIPLE = TRUE

<details><summary>Show Answer</summary>
Correct Answer: C. `SINGLE = FALSE` is the default, which splits unloaded data across multiple files.
</details>

---

### Question 828
A size 3X-Large multi-cluster warehouse runs one cluster for one full hour and then runs two clusters for the next full hour. What would be the total number of credits billed?
- A. 64
- B. 128
- C. 149
- D. 192

<details><summary>Show Answer</summary>
Correct Answer: D. A 3X-Large warehouse consumes 64 credits/hour per cluster. Hour 1: 1 cluster × 64 = 64 credits. Hour 2: 2 clusters × 64 = 128 credits. Total = 64 + 128 = 192 credits.
</details>

---

### Question 829
What is the impact of increasing the number of concurrent clusters on a Snowflake virtual warehouse?
- A. Improved performance for small, simple queries
- B. Improved performance for large, complex queries
- C. Decreased queuing for concurrent queries
- D. Decreased consumption of Snowflake credits

<details><summary>Show Answer</summary>
Correct Answer: C. Multi-cluster warehouses address concurrency/queuing, not single-query performance.
</details>

---

### Question 830
By default, how long is the standard retention period for Time Travel across all Snowflake accounts?
- A. 0 days
- B. 1 day
- C. 7 days
- D. 14 days

<details><summary>Show Answer</summary>
Correct Answer: B. The default is 1 day for all editions (Standard Edition's maximum is also 1 day; Enterprise Edition and above can extend up to 90 days for permanent tables, but the out-of-the-box default is 1 day).
</details>

---

### Question 831
What type of query will benefit from the query acceleration service?
- A. Queries without filters or aggregation
- B. Queries with large scans and selective filters
- C. Queries where the GROUP BY has high cardinality
- D. Queries on tables that have search optimization service enabled

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 832
How does the search optimization service help Snowflake users improve query performance?
- A. By clustering the tables
- B. It maintains a persistent data structure that keeps track of the values of the table's columns in each of its micro-partitions.
- C. It scans the disk cache to avoid scans on the tables used in the query.
- D. It keeps track of running queries and their results and saves those extra scans on the table.

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 833
What can be done to reduce queueing on a virtual warehouse?
- A. Increase the AUTO_SUSPEND setting for the warehouse.
- B. Change the warehouse to a multi-cluster warehouse.
- C. Increase the warehouse size.
- D. Lower the MAX_CONCURRENCY_LEVEL setting on the warehouse.

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 834
What are characteristics of Snowsight worksheets? (Choose two.)
- A. Worksheets can be grouped under folders, and a folder of folders.
- B. Each worksheet is a unique Snowflake session.
- C. Users are limited to running one query on a worksheet.
- D. The Snowflake session ends when a user switches worksheets.
- E. Users can import worksheets and share them with other users.

<details><summary>Show Answer</summary>
Correct Answer: A, B.
</details>

---

### Question 835
What are reasons for using the VALIDATE function after a COPY INTO command execution? (Choose two.)
- A. To validate the files that have been loaded earlier using the COPY INTO command
- B. To view changes that were made during the execution of the COPY command
- C. To return errors encountered during the execution of the COPY INTO command
- D. To identify potential issues in the COPY INTO command before it is executed
- E. To count the number of errors during execution of the COPY INTO command

<details><summary>Show Answer</summary>
Correct Answer: A, C. VALIDATE is a post-load, look-back function (it cannot preview a load before it happens).
</details>

---

### Question 836
Which types of URLs are provided by Snowflake to access unstructured data files? (Choose two.)
- A. Absolute URL
- B. Dynamic URL
- C. File URL
- D. Relative URL
- E. Scoped URL

<details><summary>Show Answer</summary>
Correct Answer: C, E. Snowflake provides File URLs, Scoped URLs, and Pre-signed URLs for unstructured data access.
</details>

---

### Question 837
Which query will return a sample of a table named testtable, in which each row has a 10% probability of being included in the sample?
- A. select * from testtable sample;
- B. select * from testtable sample (10);
- C. select * from testtable sample (10 percent);
- D. select * from testtable sample (10 rows);

<details><summary>Show Answer</summary>
Correct Answer: B. A bare numeric argument to SAMPLE/TABLESAMPLE is interpreted as a percentage (Bernoulli sampling) by default.
</details>

---

### Question 838
Which system can be used to manage access to the data in a share and display certain data only to paying customers?
- A. SYSTEM$ALLOWLIST
- B. SYSTEM$ALLOWLIST_PRIVATELINK
- C. SYSTEM$AUTHORIZE_PRIVATELINK
- D. Data Exchange / Data Marketplace listings

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 839
Which Snowflake object does not consume any storage costs?
- A. Secure View
- B. Materialized view
- C. Temporary table
- D. Transient table

<details><summary>Show Answer</summary>
Correct Answer: A. Views (including secure views) are query definitions only and store no data; materialized views do consume storage since they persist result data.
</details>

---

### Question 840
What does the LATERAL modifier for the FLATTEN function do?
- A. Casts the values of the flattened data
- B. Extracts the path of the flattened data
- C. Joins information outside the object with the flattened data
- D. Retrieves a single instance of a repeating element in the flattened data

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 841
How can a Snowflake user validate data that is loaded using the COPY INTO [location] command?
- A. Load the data into a CSV file.
- B. Load the data into a relational table.
- C. Use the VALIDATION_MODE = RETURN_ERRORS SQL statement.
- D. Use the VALIDATION_MODE = RETURN_ROWS statement.

<details><summary>Show Answer</summary>
Correct Answer: C. (Note: VALIDATION_MODE also supports `RETURN_<n>_ROWS` for testing before a real load, but `RETURN_ERRORS` is the standard validation option among the answers given.)
</details>

---

### Question 842
What role in Snowflake separates the management of users and roles from the management of all grants?
- A. ACCOUNTADMIN
- B. SYSADMIN
- C. SECURITYADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: D. USERADMIN is dedicated to user/role management; SECURITYADMIN (which inherits USERADMIN) manages grants globally.
</details>

---

### Question 843
Which command will unload data from a table into an external stage?
- A. PUT
- B. INSERT
- C. COPY INTO [location]
- D. GET

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 844
Why is a federated environment used for user authentication in Snowflake?
- A. To enhance data security and privacy
- B. To provide real-time monitoring of user activities
- C. To separate authentication from access
- D. To enable direct integration with external databases

<details><summary>Show Answer</summary>
Correct Answer: C. Federated authentication (SSO/SAML) separates the act of verifying identity (handled by the IdP) from Snowflake's authorization/access model.
</details>

---

### Question 845
What will happen if a Snowflake user increases the size of a suspended virtual warehouse?
- A. The provisioning of compute for the warehouse will begin immediately.
- B. The warehouse will remain suspended but new resources will be added to the query acceleration service.
- C. The provisioning of additional compute resources will be in effect when the warehouse is next resumed.
- D. The warehouse will resume immediately and start to share the compute load with other running virtual warehouses.

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 846
The VALIDATE table function has which parameter as an input argument for a Snowflake user?
- A. LAST_QUERY_ID
- B. CURRENT_STATEMENT
- C. UUID_STRING
- D. JOB_ID

<details><summary>Show Answer</summary>
Correct Answer: D. VALIDATE takes a JOB_ID (the query ID of the COPY INTO statement, or `'_last'`).
</details>

---

### Question 847
Which Snowflake edition supports Protected Health Information (PHI) data (in accordance with HIPAA and HITRUST CSF regulations), and has a dedicated metadata store and pool of compute resources?
- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: D. Business Critical also supports HIPAA/HITRUST, but VPS is the edition specifically defined by a completely dedicated (non-multi-tenant) metadata store and compute resource pool.
</details>

---

### Question 848
Which Snowflake table types are used to manage costs for short-lived tables? (Choose two.)
- A. External tables
- B. Permanent tables
- C. Directory tables
- D. Temporary tables
- E. Transient tables

<details><summary>Show Answer</summary>
Correct Answer: D, E.
</details>

---

### Question 849
What are key characteristics of virtual warehouses in Snowflake? (Choose two.)
- A. Warehouses that are multi-cluster can have nodes of different sizes.
- B. Warehouses can be started and stopped at any time.
- C. Warehouses can be resized at any time, even while running.
- D. Warehouses are billed on a per-minute usage basis.
- E. Warehouses can only be used for querying and cannot be used for data loading.

<details><summary>Show Answer</summary>
Correct Answer: B, C. All clusters in a multi-cluster warehouse are the same size (A is false), and billing is per-second with a 60-second minimum, not strictly "per-minute" (D is imprecise and not selected).
</details>

---

### Question 850
What strategies can be used to optimize the performance of a virtual warehouse? (Choose two.)
- A. Reduce queuing.
- B. Allow memory spillage.
- C. Increase the STATEMENT_TIMEOUT_IN_SECONDS parameter.
- D. Increase the warehouse size.
- E. Suspend the warehouse frequently.

<details><summary>Show Answer</summary>
Correct Answer: A, D.
</details>

---

### Question 851
How are privileges inherited in a role hierarchy in Snowflake?
- A. Privileges are inherited by any higher roles in the hierarchy.
- B. Privileges are inherited by any roles at the same level in the hierarchy.
- C. Privileges are only inherited by the direct parent role in the hierarchy.
- D. Privileges are only inherited by the direct child role in the hierarchy.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 852
At what level can the STATEMENT_TIMEOUT_IN_SECONDS parameter be set?
- A. Account
- B. Role
- C. Session, Warehouse, and Account
- D. Virtual warehouse

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 853
What entity is responsible for hosting and sharing data in Snowflake?
- A. Data provider
- B. Data consumer
- C. Reader account
- D. Managed account

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 854
Which function will provide the proxy information needed to protect Snowsight?
- A. SYSTEM$GET_TAG
- B. SYSTEM$GET_PRIVATELINK
- C. SYSTEM$ALLOWLIST_PRIVATELINK
- D. SYSTEM$AUTHORIZE_PRIVATELINK

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 855
The DATA_RETENTION_TIME_IN_DAYS property is set at which level?
- A. User
- B. Role
- C. Account, Database, Schema, Table
- D. Organization

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 856
When unloading the data for file format type specified (TYPE = 'CSV'), SQL NULL can be converted to string 'null' using which file format option?
- A. EMPTY_FIELD_AS_NULL
- B. FIELD_OPTIONALLY_ENCLOSED_BY
- C. NULL_IF
- D. ESCAPE_UNENCLOSED_FIELD

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 857
Which table function should be used to view details on a Directed Acyclic Graph (DAG) run that is presently scheduled or is executing?
- A. TASK_HISTORY
- B. TASK_DEPENDENTS
- C. CURRENT_TASK_GRAPHS
- D. DAG_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 858
What Snowflake database object is derived from a query specification, stored for later use, and can speed up expensive aggregation on large data sets?
- A. Table
- B. External table
- C. Secure view
- D. Materialized view

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 859
User1, who has the SYSADMIN role, executed a query on Snowsight. User2, who is in the same Snowflake account, wants to view the result set of the query executed by User1 using the Snowsight history. What will happen if User2 tries to access the query history?
- A. If User2 has the SYSADMIN role they will be able to see the results.
- B. If User2 has the SECURITYADMIN role they will be able to see the results.
- C. If User2 has the ACCOUNTADMIN role they will be able to see the results.
- D. User2 will be unable to view the result set of the query executed by User1.

<details><summary>Show Answer</summary>
Correct Answer: D. Query results are only visible to the user who ran the query (within the result cache window), regardless of role.
</details>

---

### Question 860
A permanent table and temporary table have the same name, TBL1, in a schema. What will happen if a user executes `SELECT * FROM TBL1;`?
- A. The temporary table will take precedence over the permanent table.
- B. The permanent table will take precedence over the temporary table.
- C. An error will say there cannot be two tables with the same name in a schema.
- D. The table that was created most recently will take precedence over the older table.

<details><summary>Show Answer</summary>
Correct Answer: A. Temporary tables exist only for the session and shadow any permanent/transient table of the same name within that session.
</details>

---

### Question 861
The effects of query pruning can be observed by evaluating which statistics? (Choose two.)
- A. Partitions scanned
- B. Partitions total
- C. Bytes scanned
- D. Bytes read from result
- E. Bytes written

<details><summary>Show Answer</summary>
Correct Answer: A, B. Comparing "partitions scanned" against "partitions total" in the Query Profile shows how effective pruning was.
</details>

---

### Question 862
Which data types optimally store semi-structured data? (Choose two.)
- A. ARRAY
- B. CHARACTER
- C. STRING
- D. VARCHAR
- E. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: A, E.
</details>

---

### Question 863
What compute resource is used when loading data using Snowpipe?
- A. Snowpipe uses virtual warehouses provided by the user.
- B. Snowpipe uses an Apache Kafka server for its compute resources.
- C. Snowpipe uses compute resources provided by Snowflake.
- D. Snowpipe uses cloud platform compute resources provided by the user.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowpipe is a serverless feature — Snowflake manages and provisions the compute for it.
</details>

---

### Question 864
Which file function gives a user or application access to download unstructured data from a Snowflake stage?
- A. GET_STAGE_URL
- B. BUILD_STAGE_FILE_URL
- C. GET_PRESIGNED_URL
- D. BUILD_SCOPED_FILE_URL

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 865
By default, which role can create resource monitors?
- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 866
Which DDL/DML operation is allowed on an inbound data share?
- A. ALTER TABLE
- B. INSERT INTO
- C. MERGE
- D. SELECT

<details><summary>Show Answer</summary>
Correct Answer: D. Data shares are read-only for the consumer.
</details>

---

### Question 867
Which types of charts does Snowsight support? (Choose two.)
- A. Area charts
- B. Bar charts
- C. Column charts
- D. Radar charts
- E. Scorecards

<details><summary>Show Answer</summary>
Correct Answer: B, E.
</details>

---

### Question 868
Which role in Snowflake allows users to enable replication for multiple accounts?
- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. ORGADMIN

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 869
Which Snowflake tool is recommended for data batch processing?
- A. SnowCD
- B. SnowSQL
- C. Snowsight
- D. The Snowflake API

<details><summary>Show Answer</summary>
Correct Answer: B. SnowSQL is the command-line client best suited for scripted/batch workloads; Snowsight is the browser-based UI oriented toward interactive use.
</details>

---

### Question 870
Which Snowflake mechanism is used to limit the number of micro-partitions scanned by a query?
- A. Caching
- B. Cluster depth
- C. Query pruning
- D. Retrieval optimization

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 871
While clustering a table, columns with which data types can be used as clustering keys? (Choose two.)
- A. BINARY
- B. GEOGRAPHY
- C. GEOMETRY
- D. OBJECT
- E. VARIANT

<details><summary>Show Answer</summary>
Correct Answer: A, C. Confirmed current: Snowflake documentation states a clustering key can be any data type except GEOGRAPHY, VARIANT, OBJECT, or ARRAY — so BINARY and GEOMETRY are both valid.
</details>

---

### Question 872
Which use case does the search optimization service support?
- A. Disjuncts (OR) in join predicates
- B. Inequality join predicates
- C. Join predicates on VARIANT columns
- D. Conjunctions (AND) of multiple equality predicates

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 873
What should be used when creating a CSV file format where the columns are wrapped by single quotes or double quotes?
- A. BINARY_FORMAT
- B. ESCAPE_UNENCLOSED_FIELD
- C. FIELD_OPTIONALLY_ENCLOSED_BY
- D. ENCLOSED_BY

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 874
If a multi-cluster warehouse is using an economy scaling policy, how long will queries wait in the queue before another cluster is started?
- A. 1 minute
- B. 2 minutes
- C. 6 minutes
- D. 8 minutes

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 875
What does the TableScan operator represent in the Query Profile?
- A. The scan of a single table
- B. The access to data stored in stage objects
- C. The list of values provided with the VALUES clause
- D. The records generated using the construct

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 876
What information is found within the Statistic output in the Query Profile Overview?
- A. Operator tree
- B. Table pruning
- C. Most expensive nodes
- D. Nodes by execution time

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 877
Which roles can make grant decisions to objects within a managed access schema? (Choose two.)
- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. ORGADMIN
- E. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: A, B. In a managed access schema, only the schema owner or a role with the MANAGE GRANTS privilege (ACCOUNTADMIN/SECURITYADMIN by default) can grant privileges on objects in that schema — object owners lose that ability.
</details>

---

### Question 878
How can a Snowflake user post-process the result of SHOW FILE FORMATS?
- A. Use the RESULT_SCAN function.
- B. Create a CURSOR for the command.
- C. Put it in the FROM clause in brackets.
- D. Assign the command to RESULTSET.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 879
A Snowflake account administrator has set the resource monitors with actions defined for each resource monitor as "Notify & Suspend Immediately". What is the MAXIMUM limit of credits that Warehouse 2 can consume?
- A. 1000
- B. 1500
- C. 3500
- D. 5000

<details><summary>Show Answer</summary>
Correct Answer: D (as given in the original source).

**Note:** This question references a specific resource-monitor credit-quota table/scenario that was not included in the supplied source text, so the numeric answer cannot be independently re-derived here — it is carried over from the original answer key as-is. If you have the original exhibit/table for this question, double-check the quota assigned to "Warehouse 2" against it.
</details>

---

### Question 880
When initially creating an account in Snowflake, which settings can be specified? (Choose two.)
- A. Account name
- B. Organization name
- C. Account locator
- D. Region
- E. Snowflake edition

<details><summary>Show Answer</summary>
Correct Answer: D, E. Region and edition are chosen at creation; the account locator is system-generated.
</details>

---

### Question 881
What activities can a user with the ORGADMIN role perform? (Choose two.)
- A. Create an account for an organization.
- B. Edit the data for an organization.
- C. Delete the account data for an organization.
- D. View usage information for all accounts in an organization.
- E. Select all the data in tables across all databases in an organization.

<details><summary>Show Answer</summary>
Correct Answer: A, D.
</details>

---

### Question 882
What is one of the benefits of using a multi-cluster virtual warehouse?
- A. It will speed up loading.
- B. It will reduce the cost of running the warehouse.
- C. It will automatically increase the warehouse size as needed.
- D. It will automatically start and stop additional clusters as needed.

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 883
When should a multi-cluster virtual warehouse be used in Snowflake?
- A. When queuing is delaying query execution on the warehouse.
- B. When there is significant disk spilling shown on the Query Profile.
- C. When dynamic vertical scaling is being used in the warehouse.
- D. When there are no concurrent queries running on the warehouse.

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 884
What is used to denote a pre-computed data set derived from a SELECT query specification and stored for later use?
- A. View
- B. Secure view
- C. Materialized view
- D. External table

<details><summary>Show Answer</summary>
Correct Answer: C.
</details>

---

### Question 885
A Snowflake user wants to temporarily bypass a network policy by configuring the user object property MINS_TO_BYPASS_MFA. What should they do?
- A. Use the SECURITYADMIN role.
- B. Use SYSADMIN role.
- C. Use the ACCOUNTADMIN role.
- D. Contact Snowflake Support.

<details><summary>Show Answer</summary>
Correct Answer: D (as originally given), but see the ⚠ **Updated** note below.

⚠ **Updated:** This question mixes up two distinct, similarly-named user properties. `MINS_TO_BYPASS_MFA` temporarily suspends the MFA requirement for a user (e.g., if they lose their authenticator device) and is set directly with `ALTER USER ... SET MINS_TO_BYPASS_MFA = <minutes>` — no Snowflake Support ticket is required. That command can be run by any role with sufficient privilege over the user object (typically SECURITYADMIN or a role that inherits USERADMIN privileges, or ACCOUNTADMIN). Separately, there is a `MINS_TO_BYPASS_NETWORK_POLICY` property, which is what actually controls a temporary bypass of a **network policy**; it is likewise set via ALTER USER by an appropriately privileged role. Contacting Snowflake Support is generally only necessary for account-level lockouts (e.g., an administrator is locked out entirely and no one internally has the privilege to fix it) — not for routine, self-service bypasses of either MFA or a network policy. If the question is strictly interpreted as written (bypassing MFA via an admin-settable property), the best answer among the given options is actually **A. Use the SECURITYADMIN role**, not D.
</details>

---

### Question 886
What is the default access of a securable object until other access is granted?
- A. No access
- B. Read access
- C. Write access
- D. Full access

<details><summary>Show Answer</summary>
Correct Answer: A.
</details>

---

### Question 887
From what stage can a Snowflake user omit the FROM clause while loading data into a table?
- A. The user stage
- B. The table stage
- C. The internal named stage
- D. The external named stage

<details><summary>Show Answer</summary>
Correct Answer: B. Because a table stage is implicitly tied to its table, `COPY INTO <table>` can omit the FROM clause.
</details>

---

### Question 888
What is used during the FIRST execution of `SELECT COUNT(*) FROM ORDER`?
- A. Remote disk cache
- B. Virtual warehouse cache
- C. Result cache
- D. Metadata-based result

<details><summary>Show Answer</summary>
Correct Answer: D. Snowflake can answer simple aggregate queries like COUNT(*) directly from table metadata without scanning data or even requiring a running warehouse.
</details>

---

### Question 889
What is the purpose of a resource monitor in Snowflake?
- A. To monitor the query performance of virtual warehouses.
- B. To create and suspend virtual warehouses automatically.
- C. To manage cloud services needed for virtual warehouses.
- D. To control costs and credit usage by virtual warehouses.

<details><summary>Show Answer</summary>
Correct Answer: D.
</details>

---

### Question 890
Which data formats are supported by Snowflake when unloading semi-structured data? (Choose two.)
- A. Binary file in Avro
- B. Binary file in Parquet
- C. Comma-separated JSON
- D. Newline Delimited JSON
- E. Plain text file containing XML elements

<details><summary>Show Answer</summary>
Correct Answer: B, D.
</details>

---

### Question 891
In Snowflake, the use of federated authentication enables which Single Sign-On (SSO) activities? (Choose two.)
- A. Authorizing users
- B. Initiating user sessions
- C. Logging into Snowflake
- D. Logging out of Snowflake
- E. Performing role authentication

<details><summary>Show Answer</summary>
Correct Answer: C, D.
</details>

---

### Question 892
What does the worksheet and database explorer feature in Snowsight allow users to do?
- A. Add users from a worksheet.
- B. Move a worksheet to a folder or a dashboard.
- C. Combine multiple worksheets into a single worksheet.
- D. Tag frequently accessed worksheets for ease of access.

<details><summary>Show Answer</summary>
Correct Answer: B.
</details>

---

### Question 893
When unloading data from Snowflake to AWS, what permissions are required? (Choose two.)
- A. s3:DeleteObject
- B. s3:CopyObject
- C. s3:GetObject
- D. s3:PutObject
- E. s3:GetBucketLocation

<details><summary>Show Answer</summary>
Correct Answer: A, D. Snowflake's sample IAM policy for an external stage used for unloading includes `s3:PutObject` (to write files) and `s3:DeleteObject` (so Snowflake can overwrite/replace files as needed).
</details>

---

### Question 894
What step can resolve data spilling in Snowflake?
- A. Using a larger virtual warehouse
- B. Increasing the virtual warehouse maximum timeout limit
- C. Increasing the amount of remote storage for the virtual warehouse
- D. Using a Common Table Expression (CTE) instead of a temporary table

<details><summary>Show Answer</summary>
Correct Answer: A. Spilling happens when a query's intermediate data exceeds available memory/local disk; a larger warehouse provides more memory and local SSD to avoid spilling to remote storage.
</details>

---

### Question 895
Which user preferences can be set for a user profile in Snowsight? (Choose two.)
- A. Multi-Factor Authentication (MFA)
- B. Default database
- C. Default schema
- D. Notifications
- E. Username

<details><summary>Show Answer</summary>
Correct Answer: A, D.
</details>

---

### Question 896
What privilege is needed for a Snowflake user to see the definition of a secure view?
- A. OWNERSHIP
- B. MODIFY
- C. CREATE
- D. USAGE

<details><summary>Show Answer</summary>
Correct Answer: A. Secure views intentionally hide their definition (via SHOW VIEWS / GET_DDL / Information Schema) from everyone except the object owner.
</details>

---

### Question 897
What guideline does Snowflake recommend when setting the auto-suspension time limit?
- A. Set tasks for immediate suspension.
- B. Set tasks for suspension after 5 minutes.
- C. Set query warehouses for suspension after 15 minutes.
- D. Set query warehouses for suspension after 30 minutes.

<details><summary>Show Answer</summary>
Correct Answer: A.

⚠ **Updated:** The original source listed B as the answer. Current Snowflake documentation ("Optimizing the warehouse cache") explicitly states general guidelines: **for task warehouses, Snowflake recommends immediate suspension**; for DevOps/DataOps/Data Science warehouses, roughly 5 minutes; and for BI/query warehouses, at least 10 minutes (to preserve the warm cache). None of the given options describes "at least 10 minutes" for query warehouses, so among the choices provided, **A** is the one that matches current official guidance — the "5 minutes" figure in the original answer (B) belongs to a different workload category (DevOps/DataOps), not tasks.
</details>

---

### Question 898
When does Snowflake automatically encrypt data that is loaded into Snowflake? (Choose two.)
- A. After the data is staged.
- B. After loading the data into a table.
- C. After loading the data into an internal stage.
- D. After loading data into an external stage.
- E. Only when using an encrypted stage.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Snowflake automatically encrypts data at rest once it reaches an internal stage or a table; encryption of data in a customer-managed external stage is the customer's/cloud provider's responsibility, not automatic Snowflake encryption.
</details>

---

### Question 899
When data is loaded into Snowflake, what formats does Snowflake use internally to store the data in cloud? (Choose two.)
- A. Key-value
- B. Columnar
- C. Graph
- D. Document
- E. Compressed

<details><summary>Show Answer</summary>
Correct Answer: B, E. Snowflake stores data in compressed, columnar micro-partitions.
</details>

---

### Question 900
What do temporary and transient tables have in common in Snowflake?
- A. Both tables have no Fail-safe period.
- B. Both tables have data retention period maximums of one day.
- C. Both tables are visible only to a single user session.
- D. For both tables, the retention period ends when the tables are dropped.
- E. For both tables, the retention period does not end when the session ends.

<details><summary>Show Answer</summary>
Correct Answer: A, B. (Note: only temporary tables are session-scoped — C is false for transient tables, which persist across sessions like permanent tables but lack Fail-safe.)
</details>

---

## Summary of Corrections & Notes

| Question | Original Answer | Status | Note |
|---|---|---|---|
| 815 | C | ✅ Confirmed | Serverless task max = 2X-Large (XXLARGE), per current docs |
| 871 | AC | ✅ Confirmed | Clustering keys exclude GEOGRAPHY/VARIANT/OBJECT/ARRAY only; BINARY & GEOMETRY are valid |
| 885 | D | ⚠ Updated | Question conflates MINS_TO_BYPASS_MFA with network-policy bypass; a self-service ALTER USER by an admin role is the realistic mechanism, not a Support ticket |
| 897 | B | ⚠ Updated | Current Snowflake guidance recommends **immediate** suspension for task warehouses (Answer A), not "5 minutes" |
| 879 | D | ℹ️ Unverifiable | Original question references a resource-monitor exhibit/table not present in the supplied source text |

All other answers were reviewed against current Snowflake product behavior and match standard, stable Snowflake functionality as of July 2026.



====================================================================================================
# SnowPro_901-1000.md
====================================================================================================

# SnowPro Core Practice Questions — Batch 10 (Questions 901–1000)

*Cleaned, reformatted, and cross-checked against current Snowflake documentation (as of July 2026). Correct answers are hidden in collapsible sections below each question — click to reveal.*

---

### Question 901

What are the least privileges needed to view and modify resource monitors? (Choose two.)

- **A.** SELECT
- **B.** OWNERSHIP
- **C.** MONITOR
- **D.** MODIFY
- **E.** USAGE

<details><summary>Show Answer</summary>

Correct Answer: **CD**

</details>

---

### Question 902

When does a materialized view get suspended in Snowflake?

- **A.** When a column is added to the base table
- **B.** When a column is dropped from the base table
- **C.** When a DML operation is run on the base table
- **D.** When the base table is reclustered

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 903

What happens when a Snowflake user alters the data retention period at the account level?

- **A.** All child objects will retain data for the new retention period.
- **B.** All child objects that do not have an explicit retention period will automatically inherit the new retention period.
- **C.** All child objects with an explicit retention period will be overridden with the new retention period.
- **D.** All explicit child object retention periods will remain unchanged.

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 904

Snowpark provides libraries for which programming languages? (Choose two.)

- **A.** JavaScript
- **B.** Python
- **C.** Scala
- **D.** C++

<details><summary>Show Answer</summary>

Correct Answer: **BC**

</details>

---

### Question 905

How can a Snowflake user sample 10% of a table named SNOWPRO? (Choose two.)

- **A.** SELECT * FROM SNOWPRO SAMPLE SYSTEM (10);
- **B.** SELECT * FROM SNOWPRO TABLESAMPLE (10 ROWS);
- **C.** SELECT * FROM SNOWPRO TABLESAMPLE BLOCK (10);
- **D.** SELECT * FROM SNOWPRO TABLESAMPLE BLOCK (10 ROWS);
- **E.** SELECT * FROM SNOWPRO SAMPLE BERNOULLI (10 ROWS);

<details><summary>Show Answer</summary>

Correct Answer: **AC**

</details>

---

### Question 906

Why would a Snowflake user choose to use a transient table?

- **A.** To store data for long-term analysis
- **B.** To store large data files that are used frequently
- **C.** To create a permanent table for ongoing use in ELT
- **D.** To store transitory data that needs to be maintained beyond the session

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 907

What does a masking policy consist of in Snowflake?

- **A.** A single data type, with one or more conditions, and one or more masking functions
- **B.** A single data type, with only one condition, and only one masking function
- **C.** Multiple data types, with only one condition, and one or more masking functions
- **D.** Multiple data types, with one or more conditions, and one or more masking functions

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 908

What actions can be performed by a consumer account on a shared database? (Choose two.)

- **A.** Cloning a shared table
- **B.** Modifying the data in a shared table
- **C.** Using Time Travel on a table
- **D.** Executing the SELECT statement on a shared table
- **E.** Joining the data from a shared table with another table

<details><summary>Show Answer</summary>

Correct Answer: **DE**

</details>

---

### Question 909

What data type is used to ingest semi-structured data into a Snowflake table?

- **A.** BOOLEAN
- **B.** NUMBER
- **C.** VARBINARY
- **D.** VARIANT

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 910

Which security feature is used to connect or log in to a Snowflake account?

- **A.** Network policies
- **B.** SCIM
- **C.** Role-Based Access Control (RBAC)
- **D.** Key pair authentication

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 911

Given the statement template below, which database objects can be added to a share? (Choose two.)
`GRANT [privilege] ON [object] [object_name] TO SHARE [share_name];`

- **A.** Secure functions
- **B.** Stored procedures
- **C.** Streams
- **D.** Tables
- **E.** Tasks

<details><summary>Show Answer</summary>

Correct Answer: **AD**

</details>

---

### Question 912

Which Snowflake feature or tool helps troubleshoot issues in SQL query expressions that commonly cause performance bottlenecks?

- **A.** Persisted results
- **B.** QUERY_HISTORY view
- **C.** Query acceleration service
- **D.** Query Profile

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 913

What is a non-configurable feature that provides historical data that Snowflake may recover during a 7-day period?

- **A.** Fail-safe
- **B.** Time Travel
- **C.** Cloning
- **D.** Account replication

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 914

Which function should be used to authorize users to access rows in a base table when using secure views with Secure Data Sharing?

- **A.** CURRENT_ROLE()
- **B.** CURRENT_ACCOUNT()
- **C.** CURRENT_REGION()
- **D.** CURRENT_USER()

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 915

What is the purpose of collecting statistics on data in Snowflake?

- **A.** To identify data storage order correlations
- **B.** To enable efficient pruning based on query filters
- **C.** To reduce the total of micro-partitions in a table
- **D.** To optimize query performance by reading all data in a table

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 916

What type of function returns one value for each invocation?

- **A.** Aggregate
- **B.** Scalar
- **C.** Table
- **D.** Window

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 917

Which file formats support unloading semi-structured data? (Choose two.)

- **A.** AVRO
- **B.** JSON
- **C.** ORC
- **D.** Parquet
- **E.** XML

<details><summary>Show Answer</summary>

Correct Answer: **BD**

</details>

---

### Question 918

Which Snowflake role has the ability to rename an account and specify whether the original URL can be used to access the renamed account?

- **A.** ACCOUNTADMIN
- **B.** SECURITYADMIN
- **C.** SYSADMIN
- **D.** ORGADMIN

<details><summary>Show Answer</summary>

Correct Answer: **D**

**⚠ Updated:** ORGADMIN remains correct today, but Snowflake is phasing out the ORGADMIN role for multi-account organizations in favor of a new **GLOBALORGADMIN** role (used in the dedicated organization account) for organization-level tasks such as renaming accounts. Expect SnowPro content to transition to GLOBALORGADMIN terminology.

</details>

---

### Question 919

How can a user get the MOST detailed information about individual table storage details in Snowflake?

- **A.** SHOW TABLES command
- **B.** SHOW EXTERNAL TABLES command
- **C.** TABLES view
- **D.** TABLE_STORAGE_METRICS view

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 920

What type of account can be used to share data with a consumer who does not have a Snowflake account?

- **A.** Data provider
- **B.** Data consumer
- **C.** Reader
- **D.** Organization

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 921

By default, which role has access to the SYSTEM$GLOBAL_ACCOUNT_SET_PARAMETER function?

- **A.** ACCOUNTADMIN
- **B.** SECURITYADMIN
- **C.** SYSADMIN
- **D.** ORGADMIN

<details><summary>Show Answer</summary>

Correct Answer: **D**

**⚠ Updated:** ORGADMIN is still the classically tested answer, and current documentation confirms ORGADMIN (along with ACCOUNTADMIN) can execute this function. Note that Snowflake is phasing out ORGADMIN for multi-account organizations in favor of the **GLOBALORGADMIN** role for organization-level administration.

</details>

---

### Question 922

If a virtual warehouse is suspended, what happens to the warehouse cache?

- **A.** The cache is dropped when the warehouse is suspended and is no longer available upon resume.
- **B.** The warehouse cache persists for as long as the warehouse exists, regardless of its suspension status.
- **C.** The cache is maintained for up to two hours and can be restored if the warehouse is restarted within this limit.
- **D.** The cache is maintained for the auto_suspend duration and can be restored if the warehouse is restarted within this limit.

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 923

What are the primary authentication methods that Snowflake supports for securing REST API interactions? (Choose two.)

- **A.** OAuth
- **B.** Key pair authentication
- **C.** Federated authentication
- **D.** Multi-Factor Authentication (MFA)
- **E.** Username and password authentication

<details><summary>Show Answer</summary>

Correct Answer: **AB**

</details>

---

### Question 924

A Snowflake user is trying to load a 125 GB file using a COPY command. The file continues to load for almost an entire day. What will happen at the 24-hour mark?

- **A.** The file will continue to load until all contents are loaded.
- **B.** The file will stop loading and all data up to that point will be committed.
- **C.** The file loading will be aborted without any portion of the file being committed.
- **D.** The file's number of allowable hours to load can be programmatically controlled to load easily into Snowflake.

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 925

What information does the Query Profile provide?

- **A.** Graphical representation of the data model
- **B.** Statistics for each component of the processing plan
- **C.** Detailed information about the database schema
- **D.** Real-time monitoring of database operations

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 926

Which command is used to start configuring Snowflake for Single Sign-on (SSO)?

- **A.** CREATE SESSION POLICY
- **B.** CREATE NETWORK RULE
- **C.** CREATE SECURITY INTEGRATION
- **D.** CREATE POLICY

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 927

Which sequence (order) of object privileges should be used to grant a custom role read-only access on a table?

- **A.** 1. Schema Usage, 2. Database Usage, 3. Table Select
- **B.** 1. Table Select, 2. Schema Usage, 3. Database Usage
- **C.** 1. Database Usage, 2. Schema Usage, 3. Table Select
- **D.** 1. Database Select, 2. Schema Select, 3. Table Select

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 928

Which command removes a role from another role in Snowflake?

- **A.** ALTER ROLE
- **B.** REVOKE ROLE
- **C.** USE ROLE
- **D.** USE ROLES

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 929

In which hierarchy is tag inheritance possible?

- **A.** Organization -> Account -> Role
- **B.** Account -> User -> Schema
- **C.** Database -> View -> Column
- **D.** Database -> Schema -> Table -> Column

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 930

What happens when a network policy includes values that appear in both the allowed and blocked IP address lists?

- **A.** Those IP addresses are allowed access to the Snowflake account as Snowflake applies the allowed IP address list first.
- **B.** Those IP addresses are denied access to the Snowflake account as Snowflake applies the blocked IP address list first.
- **C.** Snowflake issues an alert and adds the duplicate IP address values to the allowed and blocked IP address lists.
- **D.** Snowflake issues an error message and adds the duplicate IP address values to both the allowed and blocked IP address lists.

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 931

For directory tables, what stage allows for automatic refreshing of metadata?

- **A.** User stage
- **B.** Table stage
- **C.** Named internal stage
- **D.** Named external stage

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 932

Which command is used to unload data from a Snowflake database table into one or more files in a Snowflake stage?

- **A.** CREATE STAGE
- **B.** COPY INTO [location]
- **C.** INSERT INTO [location]
- **D.** CREATE PIPE

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 933

Any user with the appropriate privileges can view data storage for individual tables by using which queries? (Choose two.)

- **A.** METERING_HISTORY view in the ACCOUNT_USAGE schema
- **B.** TABLE_STORAGE_METRICS view in the INFORMATION_SCHEMA
- **C.** STORAGE_USAGE in the ACCOUNT_USAGE schema
- **D.** TABLES view in the INFORMATION_SCHEMA
- **E.** STORAGE_METRICS view in the ORGANIZATION_USAGE schema

<details><summary>Show Answer</summary>

Correct Answer: **BD**

</details>

---

### Question 934

A user created a database and set the DATA_RETENTION_TIME_IN_DAYS to 30, but did not set the DATA_RETENTION_TIME_IN_DAYS in table T1. After 5 days, the user accidentally drops table T1. What are the considerations for recovering table T1?

- **A.** The user can recover the table T1 after 30 days.
- **B.** The table can be recovered because the table retention period defaults to the database level.
- **C.** The table can only be recovered by contacting Snowflake Support to recover the table from Fail-safe.
- **D.** The table cannot be recovered because the parameter was not set for table T1.

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 935

What table functions in the Snowflake Information Schema can be queried to retrieve information about directory tables? (Choose two.)

- **A.** STAGE_DIRECTORY_FILE_REGISTRATION_HISTORY
- **B.** STAGE_FILE_HISTORY
- **C.** EXTERNAL_TABLE_HISTORY
- **D.** DIRECTORY_TABLE_USAGE
- **E.** DIRECTORY_TABLE_REFRESH_HISTORY

<details><summary>Show Answer</summary>

Correct Answer: **AE**

</details>

---

### Question 936

Which Snowflake table type persists until it is explicitly dropped, is available for all users with relevant privileges (across sessions), and has no Fail-safe period?

- **A.** Temporary
- **B.** Permanent
- **C.** External
- **D.** Transient

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 937

Snowflake's access control framework combines which models for securing data? (Choose two.)

- **A.** Attribute-based Access Control (ABAC)
- **B.** Discretionary Access Control (DAC)
- **C.** Access Control List (ACL)
- **D.** Role-based Access Control (RBAC)
- **E.** Rule-based Access Control (RuBAC)

<details><summary>Show Answer</summary>

Correct Answer: **BD**

</details>

---

### Question 938

Which semi-structured file format is a compressed, efficient, columnar data representation?

- **A.** JSON
- **B.** CSV
- **C.** XML
- **D.** Parquet

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 939

How does Snowflake describe its unique architecture?

- **A.** A single-cluster shared data architecture using a central data repository and massively parallel processing (MPP)
- **B.** A multi-cluster shared data architecture using a central data repository and massively parallel processing (MPP)
- **C.** A single-cluster shared nothing architecture using a siloed data repository and symmetric multiprocessing (SMP)
- **D.** A multi-cluster shared nothing architecture using a siloed data repository and symmetric multiprocessing (SMP)

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 940

Which data type can be used to load semi-structured data files directly, without explicitly describing the hierarchical structure of the data?

- **A.** BOOLEAN
- **B.** VARIANT
- **C.** VARCHAR
- **D.** VARBINARY

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 941

The following settings are configured:
The DATA_RETENTION_TIME_IN_DAYS is set to 5 at the account level.
The DATA_RETENTION_TIME_IN_DAYS is set to 2 at the object level.
How many days will the data be retained at the object level?

- **A.** 0
- **B.** 5
- **C.** 2
- **D.** 7

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 942

Which key control concept does Snowflake describe as a defined level of access to an object?

- **A.** Grant
- **B.** Privilege
- **C.** Role
- **D.** Session

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 943

Which Snowflake object consumes credits for maintenance?

- **A.** Regular table
- **B.** Regular View
- **C.** Materialized view
- **D.** Cached query result

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 944

How many credits does a size 3X-Large virtual warehouse consume if it runs continuously for 2 hours?

- **A.** 32
- **B.** 64
- **C.** 128
- **D.** 256

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 945

What is the purpose of a Query Profile?

- **A.** To profile how many times a particular query was executed and analyze its usage statistics over time.
- **B.** To profile a particular query to understand the mechanics of the query, its behavior, and performance.
- **C.** To profile the user and/or role of a query and all privileges and policies applied to the objects within the query.
- **D.** To profile which queries are running in each warehouse and identify proper warehouse utilization and sizing for better performance and cost balancing.

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 946

Which common query problems are identified by the Query Profile? (Choose two.)

- **A.** Syntax errors
- **B.** Inefficient pruning
- **C.** Ambiguous column names
- **D.** Queries too large to fit in memory
- **E.** Object does not exist or not authorized

<details><summary>Show Answer</summary>

Correct Answer: **BD**

</details>

---

### Question 947

While running a query on a virtual warehouse in auto-scale mode, additional clusters are started immediately if which setting is configured?

- **A.** Scaling policy is Economy
- **B.** Scaling policy is Maximized
- **C.** Scaling policy is Standard
- **D.** Scaling policy is Custom

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 948

Which Snowflake role can manage any object grant globally, including modifying and revoking grants?

- **A.** USERADMIN
- **B.** ORGADMIN
- **C.** SYSADMIN
- **D.** SECURITYADMIN

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 949

What is the MINIMUM permission needed to access a file URL from an external stage?

- **A.** MODIFY
- **B.** READ
- **C.** SELECT
- **D.** USAGE

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 950

In the Data Exchange, who can get or request data from the listings? (Choose two.)

- **A.** Users with the ACCOUNTADMIN role
- **B.** Users with the SYSADMIN role
- **C.** Users with the ORGADMIN role
- **D.** Users with the IMPORT SHARE privilege
- **E.** Users with the MANAGE GRANTS privilege

<details><summary>Show Answer</summary>

Correct Answer: **AD**

</details>

---

### Question 951

What does Snowflake attempt to do if any of the compute resources for a virtual warehouse fail to provision during start up?

- **A.** Repair the failed resources
- **B.** Restart the failed resources
- **C.** Queue the failed resources
- **D.** Provision the failed resources

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 952

How does Snowflake manage its approach to Discretionary Access Control (DAC)?

- **A.** A defined level of access to an object.
- **B.** An entity to which access can be granted.
- **C.** Each object has an owner, who can in turn grant access to that object.
- **D.** Access privileges are assigned to roles, which are in turn assigned to users.

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 953

Which command is used to take away staged files from a Snowflake stage after a successful data ingestion?

- **A.** DELETE
- **B.** DROP
- **C.** REMOVE
- **D.** TRUNCATE

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 954

The Snowflake VARIANT data type imposes a 16 MB size limit on what?

- **A.** An individual row
- **B.** An individual column
- **C.** A view
- **D.** A stage

<details><summary>Show Answer</summary>

Correct Answer: **A**

**⚠ Updated:** The concept (the limit applies per row/value, not per whole table or stage) is still correct, but the number itself is outdated. Snowflake has since raised the default size limit for VARIANT, ARRAY, and OBJECT values to **128 MB** (and 64 MB for GEOGRAPHY/GEOMETRY) via Behavior Change Bundles — the 16 MB ceiling is the legacy default, not the current one.

</details>

---

### Question 955

Which Snowflake feature records changes made to a table so actions can be taken using that data capture?

- **A.** Materialized View
- **B.** Pipe
- **C.** Stream
- **D.** Task

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 956

Which system-defined, read-only view displays information on column lineage that specifies how data flows from source to target in a SQL write operation?

- **A.** ACCESS_HISTORY
- **B.** LOAD_HISTORY
- **C.** QUERY_HISTORY
- **D.** COPY_HISTORY

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 957

Who can create network policies within Snowflake? (Choose two.)

- **A.** SYSADMIN only
- **B.** ORGADMIN only
- **C.** SECURITYADMIN or higher
- **D.** A role with the CREATE NETWORK POLICY privilege
- **E.** A role with the CREATE SECURITY INTEGRATION privilege

<details><summary>Show Answer</summary>

Correct Answer: **CD**

</details>

---

### Question 958

Who can grant object privileges in a regular schema?

- **A.** Object owner
- **B.** Schema owner
- **C.** Database owner
- **D.** SYSADMIN

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 959

Which command can be used to list all the file formats for which a user has access privileges?

- **A.** LIST FILE FORMATS
- **B.** ALTER FILE FORMAT
- **C.** DESCRIBE FILE FORMAT
- **D.** SHOW FILE FORMATS

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 960

Which Snowflake feature supports continuous data loading into tables as soon as new data is available?

- **A.** Snowpark
- **B.** SnowSQL
- **C.** Snowcd
- **D.** Snowpipe

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 961

What value provides information on disk usage for operations where intermediate results do not fit in memory in a Query profile?

- **A.** Initialization
- **B.** Network
- **C.** Pruning
- **D.** Spilling

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 962

Regardless of which notation is used, what are considerations for writing the column name and element names when traversing semi-structured data?

- **A.** The column name and element names are both case-sensitive.
- **B.** The column name and element names are both case-insensitive.
- **C.** The column name is case-sensitive but element names are case-insensitive.
- **D.** The column name is case-insensitive but element names are case-sensitive.

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 963

Which Snowflake data type is used to store JSON key value pairs?

- **A.** ARRAY
- **B.** BINARY
- **C.** STRING
- **D.** VARIANT

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 964

How are network policies defined in Snowflake?

- **A.** They are a set of rules that define the network routes within Snowflake.
- **B.** They are a set of rules that dictate how Snowflake accounts can be used between multiple users.
- **C.** They are a set of rules that dictate how data can be shared between different Snowflake accounts within an organization.
- **D.** They are a set of rules that control access to Snowflake accounts by specifying the IP addresses or ranges of IP addresses that are allowed to connect.

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 965

What is the only supported character set for loading and unloading data from all supported file formats?

- **A.** UTF-8
- **B.** UTF-16
- **C.** ISO-8859-1
- **D.** WINDOWS-1252

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 966

Which function is used to convert rows in a relational table to a single VARIANT column?

- **A.** ARRAY_AGG
- **B.** OBJECT_AGG
- **C.** ARRAY_CONSTRUCT
- **D.** OBJECT_CONSTRUCT

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 967

Which command can be used to delete Staged files from a Snowflake Stage when the files are no longer needed?

- **A.** DELETE
- **B.** DROP
- **C.** REMOVE
- **D.** TABLE

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 968

A Virtual warehouse initially had high latency as a result of queries from multiple concurrent processes queuing. Over time, the problem resolved. What action can be taken to prevent this from happening again?

- **A.** Increase the size of the virtual warehouse.
- **B.** Add a cluster key for the most used JOIN key.
- **C.** Change the multi-cluster settings to add additional clusters.
- **D.** Enable the search optimization service for the underlying tables.

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 969

What action can be performed using the GET command in Snowflake?

- **A.** Automatically rename downloaded files.
- **B.** Automatically decrypt downloaded data on a client machine.
- **C.** Download data files from Snowflake internal stages to a local directory/folder.
- **D.** Download data files from Snowflake external stages to a local directory.

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 970

Which validation option is the only one that supports the COPY INTO [location] command?

- **A.** RETURN_ROWS
- **B.** RETURN_ALL_ERRORS
- **C.** RETURN_ERRORS
- **D.** VALIDATION_MODE

<details><summary>Show Answer</summary>

Correct Answer: **A**

**⚠ Updated:** The original answer (RETURN_ERRORS) is incorrect for this question as worded. Per current Snowflake documentation, **RETURN_ROWS is the only VALIDATION_MODE value supported by `COPY INTO <location>` (unloading)**. RETURN_ERRORS and RETURN_ALL_ERRORS are valid only for `COPY INTO <table>` (loading), not for unload operations.

</details>

---

### Question 971

What are the correct settings for column and element names, regardless of which notation is used while accessing elements in a JSON object?

- **A.** Both the column name and the element name are case-insensitive.
- **B.** Both the column name and the element name are case-sensitive.
- **C.** The column name is case-sensitive and the element names are case-insensitive.
- **D.** The column name is case-insensitive and the element name is case-sensitive.

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 972

How can the Query Profile be used to identify the costliest operator of a query?

- **A.** Select any node in the tree and look at the number of micro-partitions scanned.
- **B.** Find the operator node with the highest fraction of time or percentage of total time.
- **C.** Select the TableScan operator node and look at the percentage scanned from cache.
- **D.** Look at the number of rows between operator nodes across the operator tree.

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 973

In order to access Snowflake Marketplace listings, who needs to accept the Snowflake Consumer Terms of Service?

- **A.** SYSADMIN
- **B.** SECURITYADMIN
- **C.** ACCOUNTADMIN
- **D.** ORGADMIN

<details><summary>Show Answer</summary>

Correct Answer: **D**

**⚠ Updated:** Still correct today — Snowflake documentation confirms the organization administrator (ORGADMIN role) must accept the Snowflake Provider and Consumer Terms before anyone in the org can access Marketplace listings. As with other ORGADMIN-related tasks, note that Snowflake is transitioning organization-level administration toward the newer **GLOBALORGADMIN** role.

</details>

---

### Question 974

Which statistics are displayed in a Query Profile that indicate that intermediate results do not fit in memory? (Choose two.)

- **A.** Bytes scanned
- **B.** Partitions scanned
- **C.** Bytes spilled to local storage
- **D.** Bytes spilled to remote storage
- **E.** Percentage scanned from cache

<details><summary>Show Answer</summary>

Correct Answer: **CD**

</details>

---

### Question 975

How can a dropped internal stage be restored?

- **A.** Enable Time Travel.
- **B.** Clone the dropped stage.
- **C.** Execute the UNDROP command.
- **D.** Recreate the dropped stage.

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 976

Which command line flags can be used to log into a Snowflake account using SnowSQL? (Choose two.)

- **A.** -a (account)
- **B.** -p (password)
- **C.** -r (role)
- **D.** -u (user)
- **E.** -d (database)

<details><summary>Show Answer</summary>

Correct Answer: **AD**

</details>

---

### Question 977

What is a key benefit of using organizations in Snowflake?

- **A.** Ability to use ACCOUNT_USAGE views
- **B.** Ability to use zero-copy cloning across accounts
- **C.** Ability to consolidate account management and billing
- **D.** Ability to access new releases for testing and validation purposes

<details><summary>Show Answer</summary>

Correct Answer: **C**

**⚠ Updated:** Still correct — consolidated account management and billing is a core organizations benefit. Be aware that day-to-day organization administration is shifting from the ORGADMIN role toward the newer **GLOBALORGADMIN** role in a dedicated organization account.

</details>

---

### Question 978

Which privilege is required on a virtual warehouse to abort any existing executing queries?

- **A.** USAGE
- **B.** OPERATE
- **C.** MODIFY
- **D.** MONITOR

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 979

Which command should be used to look into the validity of an XML object in Snowflake?

- **A.** XMLGET
- **B.** TO_XML
- **C.** PARSE_XML
- **D.** CHECK_XML

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 980

Who can activate a network policy for users in a Snowflake account? (Choose two.)

- **A.** ACCOUNTADMIN
- **B.** USERADMIN
- **C.** PUBLIC
- **D.** SYSADMIN
- **E.** Any role that has the global ATTACH POLICY privilege

<details><summary>Show Answer</summary>

Correct Answer: **AE**

</details>

---

### Question 981

In which use cases is running a virtual warehouse required? (Choose two.)

- **A.** When creating a table
- **B.** When loading data into a table
- **C.** When unloading data from a table
- **D.** When executing a SHOW command
- **E.** When executing a LIST command

<details><summary>Show Answer</summary>

Correct Answer: **BC**

</details>

---

### Question 982

What action should be taken if a Snowflake user wants to share a newly created object in a database with consumers?

- **A.** Use the automatic sharing feature for seamless access.
- **B.** Drop the object and then re-add it to the database to trigger sharing.
- **C.** Recreate the object with a different name in the database before sharing.
- **D.** Use the GRANT privilege TO SHARE command to grant the necessary privileges.

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 983

Which privilege is required on a pipe object to pause or resume pipes?

- **A.** OPERATE
- **B.** READ
- **C.** SELECT
- **D.** USAGE

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 984

Which commands can a Snowflake user execute to specify a cluster key for a table? (Choose two.)

- **A.** CREATE TABLE
- **B.** UPDATE
- **C.** ALTER TABLE
- **D.** SET
- **E.** SHOW

<details><summary>Show Answer</summary>

Correct Answer: **AC**

</details>

---

### Question 985

Authorization to execute CREATE [object] statements comes only from which role?

- **A.** Primary role
- **B.** Secondary role
- **C.** Application role
- **D.** Database role

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 986

Which VALIDATION_MODE value will return all errors across the files specified in a COPY command, including files that partially loaded during an earlier load?

- **A.** RETURN_ROWS
- **B.** RETURN_ERRORS
- **C.** RETURN_1_ERROR
- **D.** RETURN_ALL_ERRORS

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 987

Which command is used to upload data files from a local directory or folder on a client machine to an internal stage, for a specified table?

- **A.** GET
- **B.** PUT
- **C.** CREATE STREAM
- **D.** COPY INTO [location]

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 988

Which governance feature is supported by all Snowflake editions?

- **A.** Object tags
- **B.** Masking policies
- **C.** Row access policies
- **D.** OBJECT_DEPENDENCIES view

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 989

Which chart type is supported in Snowsight for Snowflake users to visualize data with dashboards?

- **A.** Area chart
- **B.** Box plot
- **C.** Heat grid
- **D.** Pie chart

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 990

At what levels is the DATA_RETENTION_TIME_IN_DAYS parameter set?

- **A.** Account
- **B.** Database
- **C.** Schema
- **D.** All of the above

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 991

Which function returns an integer between 0 and 100 when used to calculate the similarity of strings?

- **A.** APPROXIMATE_SIMILARITY
- **B.** JAROWINKLER_SIMILARITY
- **C.** EDITDISTANCE
- **D.** MINHASH_COMBINE

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 992

Which Snowflake data feature can support auditing when a query reads data?

- **A.** Access History
- **B.** Data classification
- **C.** Column-level security
- **D.** Object dependencies

<details><summary>Show Answer</summary>

Correct Answer: **A**

</details>

---

### Question 993

Which categories are included in the execution time summary in a Query Profile? (Choose two.)

- **A.** Pruning
- **B.** Spilling
- **C.** Initialization
- **D.** Local Disk I/O
- **E.** Percentage of data read from cache

<details><summary>Show Answer</summary>

Correct Answer: **CD**

</details>

---

### Question 994

Which command can be used to list all network policies available in an account?

- **A.** DESCRIBE SESSION POLICY
- **B.** DESCRIBE NETWORK POLICY
- **C.** SHOW SESSION POLICIES
- **D.** SHOW NETWORK POLICIES

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 995

Which type of loop requires a BREAK statement to stop executing?

- **A.** FOR
- **B.** LOOP
- **C.** REPEAT
- **D.** WHILE

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 996

Which virtual warehouse consideration can help lower compute resource credit consumption?

- **A.** Setting up a dedicated warehouse
- **B.** Resizing the virtual warehouse to a larger size
- **C.** Automating the virtual warehouse suspension and resumption settings
- **D.** Increasing the maximum cluster count parameter for a multi-cluster virtual warehouse

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 997

To use the OVERWRITE option on INSERT, which privilege must be granted to the role?

- **A.** TRUNCATE
- **B.** DELETE
- **C.** UPDATE
- **D.** SELECT

<details><summary>Show Answer</summary>

Correct Answer: **B**

</details>

---

### Question 998

What happens when a suspended virtual warehouse is resized in Snowflake?

- **A.** It will return an error.
- **B.** It will return a warning.
- **C.** The suspended warehouse is resumed and compute resources are provisioned immediately.
- **D.** The additional compute resources are provisioned when the warehouse is resumed.

<details><summary>Show Answer</summary>

Correct Answer: **D**

</details>

---

### Question 999

How does Snowflake handle the data retention period for a table if a stream has not been consumed?

- **A.** The data retention period defaults to a minimum of 14 days.
- **B.** The data retention period is permanently extended for the table.
- **C.** The data retention period is temporarily extended to the stream's offset.
- **D.** The data retention period is not affected by the stream consumption.

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---

### Question 1000

Which task is supported by the use of Access History in Snowflake?

- **A.** Data backups
- **B.** Cost monitoring
- **C.** Compliance auditing
- **D.** Performance optimization

<details><summary>Show Answer</summary>

Correct Answer: **C**

</details>

---



====================================================================================================
# snowpro_1001-1100.md
====================================================================================================

# SnowPro Core (COF-C03) Practice Questions — Batch 1001–1100

Cleaned, reformatted, and cross-checked against current Snowflake documentation (as of July 2026). Answers are hidden in collapsible blocks for self-testing. Items flagged **⚠ Updated** had an original answer that no longer matches (or never fully matched) current documented Snowflake behavior.

---

### Question 1001

Which feature of Snowflake's Continuous Data Protection (CDP) has associated costs?

- A. Fail-safe
- B. Network policies
- C. Data encryption
- D. Multi-Factor Authentication (MFA)

<details><summary>Show Answer</summary>

Correct Answer: A. Fail-safe is a fixed 7-day recovery period (non-configurable) billed as extra storage; the other three are free security features.
</details>

---

### Question 1002

When enabling access to unstructured data, which URL permits temporary access to a staged file without the need to grant privileges to the stage or issue tokens?

- A. File URL
- B. Scoped URL
- C. Relative URL
- D. Pre-signed URL

<details><summary>Show Answer</summary>

Correct Answer: B. A scoped URL is embedded in query results, tied to the issuing session/persisted-results period, and needs no stage privileges — that's the key differentiator from a File URL (permanent, needs privileges) and Pre-signed URL (needs GET_PRESIGNED_URL + privileges to generate, though not to use).
</details>

---

### Question 1003

Which Snowflake function is maintained separately from the data and helps to support features such as Time Travel, Secure Data Sharing, and pruning?

- A. Column compression
- B. Data Clustering
- C. Micro-partitioning
- D. Metadata management

<details><summary>Show Answer</summary>

Correct Answer: D. Snowflake's metadata layer is stored independently of the actual table data and is what powers Time Travel, pruning statistics, and sharing.
</details>

---

### Question 1004

A tag object has been assigned to a table (TABLE_A) in a schema within a database. Which CREATE object statement will automatically assign the TABLE_A tag to a target object?

- A. CREATE TABLE [table_name] LIKE TABLE_A;
- B. CREATE VIEW [view_name] AS SELECT * FROM TABLE_A;
- C. CREATE TABLE [table_name] AS SELECT * FROM TABLE_A;
- D. CREATE MATERIALIZED VIEW [view_name] AS SELECT * FROM TABLE_A;

<details><summary>Show Answer</summary>

Correct Answer: A. CREATE TABLE ... LIKE clones structure (columns, tags) without copying data. CTAS (option C) copies data but does NOT carry over tags — a classic exam trap.
</details>

---

### Question 1005

In addition to performing all the standard steps to share data, which privilege must be granted on each database referenced by a secure view in order to be shared?

- A. READ
- B. REFERENCES
- C. REFERENCE_USAGE
- D. USAGE

<details><summary>Show Answer</summary>

Correct Answer: C. REFERENCE_USAGE lets a secure view/UDF reference objects in a different database than the one being shared, without exposing the underlying objects directly.
</details>

---

### Question 1006

Which function can be used with the COPY INTO [LOCATION] statement to convert rows from a relational table to a single VARIANT column and to unload the rows into a JSON file?

- A. FLATTEN
- B. OBJECT_AGG
- C. OBJECT_CONSTRUCT
- D. TO_VARIANT

<details><summary>Show Answer</summary>

Correct Answer: C. OBJECT_CONSTRUCT builds a single VARIANT/JSON object out of column name/value pairs for each row — the standard pattern for unloading relational rows to JSON.
</details>

---

### Question 1007

Which type of role can be assigned to a Share?

- A. Account role
- B. Custom role
- C. Database role
- D. Secondary role

<details><summary>Show Answer</summary>

Correct Answer: B. Only database roles can be granted to a share (via GRANT DATABASE ROLE ... TO SHARE) — account/custom roles cannot.
</details>

---

### Question 1008

When unloading data with the COPY INTO [location] command, what is the purpose of the PARTITION BY parameter option?

- A. To sort the contents of the output file by the specified expression.
- B. To delimit the records in the output file using the specified expression.
- C. To include a new column in the output using the specified window function expression.
- D. To split the output into multiple files, one for each distinct value of the specified expression.

<details><summary>Show Answer</summary>

Correct Answer: D. PARTITION BY writes one or more files per distinct value of the expression (e.g., partitioning unloaded files by date), similar in spirit to Hive-style partitioning.
</details>

---

### Question 1009

What are potential impacts of storing non-native values like dates and timestamps in a VARIANT column in Snowflake?

- A. Faster query performance and increased storage consumption
- B. Slower query performance and increased storage consumption
- C. Faster query performance and decreased storage consumption
- D. Slower query performance and decreased storage consumption

<details><summary>Show Answer</summary>

Correct Answer: B. Non-native types get stored as strings inside VARIANT, which both bloats storage and slows operations compared to a native relational column of that type.
</details>

---

### Question 1010

Which views are included in the ACCOUNT_USAGE schema? (Choose two.)

- A. ACCESS_HISTORY
- B. FILE_FORMATS
- C. WAREHOUSES
- D. QUERY_HISTORY
- E. DATA_TYPES

<details><summary>Show Answer</summary>

Correct Answer: A, D. ACCESS_HISTORY and QUERY_HISTORY are classic ACCOUNT_USAGE views used for auditing and monitoring; FILE_FORMATS and DATA_TYPES aren't ACCOUNT_USAGE views at all.
</details>

---

### Question 1011

What does a table with a clustering depth of 1 mean in Snowflake?

- A. The table has 1 micro-partition.
- B. The table has 1 overlapping micro-partition.
- C. The table has no overlapping micro-partitions.
- D. The table has no micro-partitions.

<details><summary>Show Answer</summary>

Correct Answer: C. A clustering depth of 1 (the theoretical minimum) means for any given point in the clustering key's range, exactly one micro-partition needs to be scanned — i.e., no overlap.
</details>

---

### Question 1012

Which Snowflake object contains all the information required to share a database?

- A. Private listing
- B. Secure view
- C. Stage
- D. Share

<details><summary>Show Answer</summary>

Correct Answer: D. A Share object bundles the grants on objects plus the list of consumer accounts — everything needed to share a database.
</details>

---

### Question 1013

What is the PRIMARY factor that determines the cost of using a virtual warehouse in Snowflake?

- A. The type of SQL statements executed
- B. The number of tables or databases queried
- C. The amount of data stored in the warehouse
- D. The length of time the compute resources in each cluster run

<details><summary>Show Answer</summary>

Correct Answer: D. Warehouses bill per-second (60s minimum) for however long compute is running — not by query type, table count, or storage (storage is billed separately).
</details>

---

### Question 1014

Which function generates a Snowflake-hosted file URL to a staged file using the stage name and relative file path as inputs, with a file URL that does not expire?

- A. BUILD_SCOPED_FILE_URL
- B. BUILD_STAGE_FILE_URL
- C. GET_STAGE_LOCATION
- D. GET_PRESIGNED_URL

<details><summary>Show Answer</summary>

Correct Answer: B. BUILD_STAGE_FILE_URL returns a permanent file URL (requires stage privileges to use); contrast with BUILD_SCOPED_FILE_URL (temporary, no privileges needed) and GET_PRESIGNED_URL (temporary, expires).
</details>

---

### Question 1015

When a Snowflake user loads CSV data from a stage, which COPY INTO [table] command guideline should they follow?

- A. The CSV field delimiter must be a comma character (,).
- B. The number of columns in each row should be consistent.
- C. The data file in the stage must be in a compressed format.
- D. The data must have the same number of columns as the target table.

<details><summary>Show Answer</summary>

Correct Answer: B. Delimiter is configurable (doesn't have to be a comma), compression is optional, and COPY INTO can map a subset/reorder of columns — but every row in the file must have the same column count as every other row.
</details>

---

### Question 1016

A user creates a stage using the following command:
`CREATE STAGE mystage DIRECTORY = (ENABLE = TRUE) FILE_FORMAT = myformat;`
What will be the outcome?

- A. A stage with a directory table set to automatically refresh will be created.
- B. A stage with a directory table that has metadata that must be manually refreshed will be created.
- C. An error will be received stating that the storage location for the stage must be identified when creating a stage with a directory table.
- D. The command will fail because the name of the directory table is not specified.

<details><summary>Show Answer</summary>

Correct Answer: B. No URL means this is a valid internal named stage — internal stages don't require a storage location, so it does NOT error. By default, a directory table (internal or external) requires a manual `ALTER STAGE ... REFRESH`.

**⚠ Updated: The original source lists **C** (error) as correct. Current Snowflake docs confirm a `CREATE STAGE` with no `URL` simply creates an **internal** named stage — internal stages never require a storage location, so no error occurs. The corrected answer is **B**: the directory table is created but its metadata must be refreshed manually (automatic refresh for internal-stage directory tables is a narrow AWS-only preview capability, not the default).**
</details>

---

### Question 1017

Which statistics on a Query Profile reflect the efficiency of the query pruning? (Choose two.)

- A. Partitions scanned
- B. Partitions total
- C. Bytes scanned
- D. Bytes spilled
- E. Bytes written

<details><summary>Show Answer</summary>

Correct Answer: A, B. Comparing partitions scanned against partitions total tells you how much pruning actually happened; bytes scanned/spilled/written speak to volume and memory pressure, not pruning efficiency specifically.
</details>

---

### Question 1018

Which operation can be performed on Snowflake external tables?

- A. INSERT
- B. JOIN
- C. RENAME
- D. SELECT

<details><summary>Show Answer</summary>

Correct Answer: D. External tables are read-only metadata layers over files in cloud storage — only SELECT (querying) is supported; no DML.
</details>

---

### Question 1019

A user wants to access files stored in a stage without authenticating into Snowflake. Which type of URL should be used?

- A. File URL
- B. Staged URL
- C. Scoped URL
- D. Pre-signed URL

<details><summary>Show Answer</summary>

Correct Answer: D. A pre-signed URL embeds temporary credentials directly in the URL, so anyone with the link can open the file in a browser with no Snowflake login required.
</details>

---

### Question 1020

Which table function is used to view all errors encountered during a previous data load?

- A. VALIDATE
- B. INFER_SCHEMA
- C. GENERATOR
- D. QUERY_HISTORY

<details><summary>Show Answer</summary>

Correct Answer: A. VALIDATE(table_name, JOB_ID => '...') returns the row-level errors from a specific past COPY INTO load.
</details>

---

### Question 1021

What is the MINIMUM size requirement when creating a Snowpark-optimized virtual warehouse?

- A. X-Small
- B. Small
- C. Medium
- D. Large

<details><summary>Show Answer</summary>

Correct Answer: C. Snowpark-optimized warehouses cannot be smaller than MEDIUM — X-Small/Small don't provide enough memory per node.
</details>

---

### Question 1022

Which role has the ability to create and manage users and roles?

- A. ORGADMIN
- B. USERADMIN
- C. SYSADMIN
- D. SECURITYADMIN

<details><summary>Show Answer</summary>

Correct Answer: B. USERADMIN owns user/role creation by default (it's granted CREATE USER and CREATE ROLE); SECURITYADMIN inherits USERADMIN plus manages grants/policies globally.
</details>

---

### Question 1023

What issues can be identified and troubleshooted using the Query Profile? (Choose two.)

- A. Full index scans
- B. Cartesian products
- C. Insufficient privileges
- D. Queries too large to fit in memory
- E. Virtual warehouse credit consumption

<details><summary>Show Answer</summary>

Correct Answer: B, D. Query Profile visually flags exploding joins (cartesian products) and memory spillage (query too large for memory) — Snowflake has no indexes, so 'index scans' isn't a real concept, and privileges/credits aren't Query Profile concerns.
</details>

---

### Question 1024

What happens to the objects in a reader account when the DROP MANAGED ACCOUNT command is executed?

- A. The objects are dropped and are permanently lost.
- B. The objects enter the Fail-safe period.
- C. The objects enter the Time Travel period.
- D. The objects are immediately moved to the provider account.

<details><summary>Show Answer</summary>

Correct Answer: A. Reader accounts are lightweight/managed — dropping one hard-deletes its objects immediately with no Time Travel or Fail-safe recovery window.
</details>

---

### Question 1025

What function can be used with the recursive argument to return a list of distinct key names in all nested elements in an object?

- A. FLATTEN
- B. GET_PATH
- C. CHECK_JSON
- D. PARSE_JSON

<details><summary>Show Answer</summary>

Correct Answer: A. FLATTEN(..., RECURSIVE => TRUE) walks every nesting level of an OBJECT/ARRAY/VARIANT, letting you pull out all key names, not just the top level.
</details>

---

### Question 1026

What does Snowflake recommend when planning virtual warehouse usage for a data load?

- A. Load the fewest possible number of large files.
- B. Dedicate a separate warehouse for loading data.
- C. Increase the size of the warehouse used.
- D. Use several single-cluster warehouses.

<details><summary>Show Answer</summary>

Correct Answer: B. Isolating load workloads on their own warehouse avoids resource contention with BI/analytics queries and simplifies cost attribution; loads generally scale better with many smaller files, not fewer large ones.
</details>

---

### Question 1027

Which Snowflake database object can be used to track data changes made to table data?

- A. Tag
- B. Task
- C. Stream
- D. Stored procedure

<details><summary>Show Answer</summary>

Correct Answer: C. A Stream tracks CDC (insert/update/delete) against a table by recording offsets and change metadata columns.
</details>

---

### Question 1028

Who can activate and enforce a network policy for all users in a Snowflake account? (Choose two.)

- A. A user with an USERADMIN or higher role
- B. A user with a SECURITYADMIN or higher role
- C. A role that has been granted the ATTACH POLICY privilege
- D. A role that has the NETWORK_POLICY account parameter set
- E. A role that has the OWNERSHIP of the network policy

<details><summary>Show Answer</summary>

Correct Answer: B, C. Setting an account-level network policy needs SECURITYADMIN (or higher, i.e. ACCOUNTADMIN) or a role explicitly granted ATTACH POLICY — mere ownership of the policy object or USERADMIN alone isn't enough.
</details>

---

### Question 1029

How can a data provider share their Snowflake data? (Choose two.)

- A. External table
- B. Snowpark API
- C. Direct share
- D. External function
- E. Snowflake Marketplace listing

<details><summary>Show Answer</summary>

Correct Answer: C, E. The two native Secure Data Sharing distribution mechanisms are a Direct Share (to specific accounts) and a Marketplace listing (public/private). External tables/functions and the Snowpark API are unrelated to provider-side sharing.
</details>

---

### Question 1030

What will prevent unauthorized access to a Snowflake account from an unknown source?

- A. Network policy
- B. Data encryption
- C. Multi-Factor Authentication (MFA)
- D. Role-Based Access Control (RBAC)

<details><summary>Show Answer</summary>

Correct Answer: A. Network policies allow/block connections by IP address range — the only one of these four that gates access based on *where* a request originates from.
</details>

---

### Question 1031

Which query type is required for implementing the search optimization service?

- A. Queries with column concatenation
- B. Substring search queries on external tables
- C. String searches on columns using the COLLATE function
- D. Equality searches on columns using supported data types

<details><summary>Show Answer</summary>

Correct Answer: D. The (non-substring) search optimization service is built for point lookups — equality/IN predicates on supported data types — not substring/wildcard search or external tables.
</details>

---

### Question 1032

What Snowflake feature provides a data hub for secure data collaboration, with a selected group of invited members?

- A. Data Replication
- B. Secure Data Sharing
- C. Data Exchange
- D. Snowflake Marketplace

<details><summary>Show Answer</summary>

Correct Answer: C. A Data Exchange is a private, invitation-only hub you curate — contrast with the public Snowflake Marketplace.
</details>

---

### Question 1033

Which semi-structured data function interprets an input string as a JSON document that produces a VARIANT value?

- A. PARSE_JSON
- B. CHECK_JSON
- C. PARSE_XML
- D. TO_JSON

<details><summary>Show Answer</summary>

Correct Answer: A. PARSE_JSON converts a VARCHAR containing JSON text into a VARIANT; CHECK_JSON only validates syntax and returns NULL/error text, it doesn't produce a VARIANT.
</details>

---

### Question 1034

Which Snowflake data types can be used to build nested hierarchical data? (Choose two.)

- A. INTEGER
- B. OBJECT
- C. VARIANT
- D. VARCHAR
- E. LIST

<details><summary>Show Answer</summary>

Correct Answer: B, C. OBJECT and VARIANT (along with ARRAY) are Snowflake's semi-structured types capable of nesting; there is no 'LIST' data type in Snowflake.
</details>

---

### Question 1035

Which statistics can be used to identify queries that have inefficient pruning? (Choose two.)

- A. Bytes scanned
- B. Bytes written to result
- C. Partitions scanned
- D. Partitions total
- E. Percentage scanned from cache

<details><summary>Show Answer</summary>

Correct Answer: C, D. Same pattern as Q1017 — compare partitions scanned to partitions total to gauge pruning efficiency.
</details>

---

### Question 1036

Which element in the Query Profile interface shows the relationship between the nodes in the execution of a query?

- A. Node List
- B. Steps
- C. Overview
- D. Operator Tree

<details><summary>Show Answer</summary>

Correct Answer: D. The Operator Tree is the visual DAG showing how each execution step feeds into the next.
</details>

---

### Question 1037

What will happen if a Snowflake user suspends the updates to a materialized view?

- A. The queries on that view will generate an error message.
- B. The queries on that view will return the last stored data.
- C. The queries on that view will return the data using Time Travel.
- D. The queries on that view will return the data with a warning message.

<details><summary>Show Answer</summary>

Correct Answer: B. Suspending refresh just freezes the materialized view at its last successfully computed state — queries keep working, just against stale data, no error and no warning.
</details>

---

### Question 1038

Which Snowflake function will parse a JSON-null into a SQL-null?

- A. TO_CHAR
- B. TO_VARIANT
- C. TO_VARCHAR
- D. STRIP_NULL_VALUE

<details><summary>Show Answer</summary>

Correct Answer: D. STRIP_NULL_VALUE converts a VARIANT containing JSON `null` into a true SQL NULL — a subtle but important distinction Snowflake otherwise preserves.
</details>

---

### Question 1039

Which Snowflake command can be used to unload the result of a query to a single file?

- A. Use COPY INTO [external stage] followed by a GET command to download the file.
- B. Use COPY INTO [internal stage] followed by a PUT command to download the file.
- C. Use COPY INTO [internal stage] with SINGLE=TRUE followed by a GET command to download the file.
- D. Use COPY INTO [internal stage] with SINGLE=TRUE followed by a PUT command to download the file.

<details><summary>Show Answer</summary>

Correct Answer: C. SINGLE=TRUE forces one output file instead of the default multi-file split; GET (not PUT, which is for uploading) is what pulls a staged file down to your local machine.
</details>

---

### Question 1040

How are micro-partitions enabled on Snowflake tables?

- A. Micro-partitioning requires a cluster key on a table.
- B. Micro-partitioning is automatically performed on all tables.
- C. Micro-partitioning requires the use of the Search Optimization Service.
- D. Micro-partitioning is defined by the user when a table is created.

<details><summary>Show Answer</summary>

Correct Answer: B. Micro-partitioning happens automatically on every table as data loads — no configuration, clustering key, or add-on service required.
</details>

---

### Question 1041

What persistent data structures are used by the search optimization service to improve the performance of point lookups?

- A. Micro-partitions
- B. Clustering keys
- C. Equality searches
- D. Search access paths

<details><summary>Show Answer</summary>

Correct Answer: D. The service builds and maintains its own persistent search access path data structures (separate from micro-partition metadata) to accelerate selective equality lookups.
</details>

---

### Question 1042

Which Snowflake feature provides increased login security for users connecting to Snowflake that is powered by Duo Security service?

- A. OAuth
- B. Network policies
- C. Single Sign-on (SSO)
- D. Multi-Factor Authentication (MFA)

<details><summary>Show Answer</summary>

Correct Answer: D. Snowflake's built-in MFA is implemented via the Duo Security service, distinct from SSO/OAuth which delegate authentication to an external identity provider.
</details>

---

### Question 1043

A user with which privileges can create or manage other users in a Snowflake account? (Choose two.)

- A. GRANT
- B. SELECT
- C. MODIFY
- D. OWNERSHIP
- E. CREATE USER

<details><summary>Show Answer</summary>

Correct Answer: D, E. OWNERSHIP on the user object, or the global CREATE USER privilege, are what actually let a role manage users — GRANT/SELECT/MODIFY aren't real user-management privileges in this context.
</details>

---

### Question 1044

Which items are considered schema objects in Snowflake? (Choose two.)

- A. Pipe
- B. File format
- C. Resource monitor
- D. Storage integration
- E. Virtual warehouse

<details><summary>Show Answer</summary>

Correct Answer: A, B. Pipes and file formats live inside a schema. Resource monitors, storage integrations, and warehouses are account-level objects, not scoped to a schema.
</details>

---

### Question 1045

What does SnowCD help Snowflake users to do?

- A. Copy data into files.
- B. Manage different databases and schemas.
- C. Troubleshoot network connections to Snowflake.
- D. Write SELECT queries to retrieve data from external tables.

<details><summary>Show Answer</summary>

Correct Answer: C. SnowCD (Snowflake Connectivity Diagnostic Tool) tests and reports on network connectivity to Snowflake endpoints, useful before/during outage troubleshooting.
</details>

---

### Question 1046

Awarding which privileges on all virtual warehouses is equivalent to granting the user the global MANAGE WAREHOUSES privilege?

- A. MODIFY, MONITOR, and OPERATE privileges
- B. OWNERSHIP and USAGE privileges
- C. APPLYBUDGET and AUDIT privileges
- D. MANAGE LISTING AUTOFULFILLMENT and RESOLVE ALL privileges

<details><summary>Show Answer</summary>

Correct Answer: A. Confirmed against current docs: granting the global MANAGE WAREHOUSES privilege is explicitly defined as equivalent to granting MODIFY, MONITOR, and OPERATE on every warehouse in the account.
</details>

---

### Question 1047

A Snowflake account has activated federated authentication. What will occur when a user with a password that was defined by Snowflake attempts to log in to Snowflake?

- A. The user will be unable to enter a password.
- B. The user will encounter an error, and will not be able to log in.
- C. The user will be able to log into Snowflake successfully.
- D. After entering the username and password, the user will be redirected to an Identity Provider (IdP) login page.

<details><summary>Show Answer</summary>

Correct Answer: C. Federated authentication doesn't remove the ability to log in directly with a Snowflake-managed password as a fallback — it adds SSO as an option, it doesn't force every login through the IdP.
</details>

---

### Question 1048

Which solution improves the performance of point lookup queries that return a small number of rows from large tables using highly selective filters?

- A. Automatic clustering
- B. Materialized views
- C. Query acceleration service
- D. Search optimization service

<details><summary>Show Answer</summary>

Correct Answer: D. This is the textbook definition/use case for the search optimization service.
</details>

---

### Question 1049

What does a "Notify & Suspend" action for a resource monitor do?

- A. Send an alert notification to all account users who have notifications enabled.
- B. Send an alert notification to all virtual warehouse users when thresholds over 100% have been met.
- C. Send a notification to all account administrators who have notifications enabled, and suspend all assigned warehouses after all statements being executed by the warehouses have completed.
- D. Send a notification to all account administrators who have notifications enabled, and suspend all assigned warehouses immediately, canceling any statements being executed.

<details><summary>Show Answer</summary>

Correct Answer: C. 'Notify & Suspend' is the graceful option — running statements finish first, then the warehouse suspends. 'Notify & Suspend Immediately' is the harsher variant that cancels running statements (option D describes that one, and is a classic distractor).
</details>

---

### Question 1050

When working with a managed access schema, who has the OWNERSHIP privilege of any tables added to the schema?

- A. The database owner
- B. The object owner (the user who created it)
- C. The schema owner
- D. The Snowflake user's role

<details><summary>Show Answer</summary>

Correct Answer: B. Managed access only centralizes the *ability to grant* further privileges at the schema owner — it doesn't change who owns (OWNERSHIP) the individual objects created inside it; that's still the creator's role.
</details>

---

### Question 1051

How can a Snowsight user change a Standard virtual warehouse to a Snowpark-optimized virtual warehouse?

- A. Use the ALTER WAREHOUSE command on an active Standard virtual warehouse.
- B. Use the ALTER WAREHOUSE command on an active Snowpark-optimized warehouse.
- C. Use the ALTER WAREHOUSE command on a suspended Standard virtual warehouse.
- D. Use the ALTER WAREHOUSE command on a suspended Snowpark-optimized warehouse.

<details><summary>Show Answer</summary>

Correct Answer: C. You can't change a Snowpark-optimized warehouse *back* to Standard by acting on it as if it already were Standard (rules out B/D), and D's premise is also backwards. Suspending first (C) is the traditionally safe/exam-expected pattern.

**⚠ Updated: Older docs required the warehouse to be SUSPENDED to change WAREHOUSE_TYPE. Current Snowflake documentation states you can now change the warehouse type **whether the warehouse is STARTED or SUSPENDED** — suspending first only avoids double-billing during the transition, it's no longer a hard requirement. So **A** (active) is technically valid too today; **C** remains the safest/traditionally-correct choice and the one most exam versions still expect.**
</details>

---

### Question 1052

According to best practices, which table type should be used if the data can be recreated outside of Snowflake?

- A. Permanent table
- B. Temporary table
- C. Transient table
- D. Volatile table

<details><summary>Show Answer</summary>

Correct Answer: C. Transient tables skip Fail-safe (cheaper storage) since you don't need Snowflake's disaster-recovery guarantee for data you can regenerate elsewhere. ('Volatile table' isn't a Snowflake table type — that's a distractor from other SQL dialects.)
</details>

---

### Question 1053

Which function unloads data from a relational table to JSON?

- A. TO_OBJECT
- B. TO_JSON
- C. TO_VARIANT
- D. OBJECT_CONSTRUCT

<details><summary>Show Answer</summary>

Correct Answer: D. Same pattern as Q1006/Q1070 — OBJECT_CONSTRUCT is the standard function for this.
</details>

---

### Question 1054

What is the purpose of the STRIP_NULL_VALUES file format option when loading semi-structured data files into Snowflake?

- A. It removes null values from all columns in the data.
- B. It converts null values to empty strings during data loading.
- C. It skips rows with null values during the loading process.
- D. It removes object or array elements containing null values.

<details><summary>Show Answer</summary>

Correct Answer: D. STRIP_NULL_VALUES (load-time file format option) drops object/array elements whose value is null, rather than storing them — it doesn't touch whole rows or relational columns.
</details>

---

### Question 1055

Which Snowflake edition enables data sharing only through Snowflake Support?

- A. Virtual Private Snowflake (VPS)
- B. Business Critical
- C. Enterprise
- D. Standard

<details><summary>Show Answer</summary>

Correct Answer: A. Confirmed against current docs: VPS collaboration (private listings) explicitly requires Snowflake Support to be involved to broker the connection between provider and consumer.
</details>

---

### Question 1056

What is the primary purpose of partitioning staged data files for regular data loads?

- A. To improve the performance of data loads
- B. To compress the data for efficient storage
- C. To encrypt the data for enhanced security
- D. To organize the data into subfolders for easy browsing

<details><summary>Show Answer</summary>

Correct Answer: A. Organizing files into logical path/partition structures lets Snowflake parallelize and target loads more efficiently — a performance optimization, not primarily a storage/browsing convenience.
</details>

---

### Question 1057

What is the minimum Snowflake Edition that supports secure storage of Protected Health Information (PHI) data?

- A. Standard Edition
- B. Enterprise Edition
- C. Business Critical Edition
- D. Virtual Private Snowflake Edition

<details><summary>Show Answer</summary>

Correct Answer: C. Business Critical is the baseline edition with the enhanced security/compliance controls (e.g., Tri-Secret Secure, HIPAA support) needed for regulated data like PHI.
</details>

---

### Question 1058

What can a Snowflake user do to reduce queuing on a multi-cluster virtual warehouse?

- A. Increase the warehouse size.
- B. Use an economy scaling policy.
- C. Increase the maximum number of clusters.
- D. Convert the warehouse to a Snowpark-optimized warehouse.

<details><summary>Show Answer</summary>

Correct Answer: C. Queuing on a multi-cluster warehouse means concurrency, not per-query compute, is the bottleneck — raising MAX_CLUSTER_COUNT lets more clusters spin up in parallel; bumping size only helps individual query speed, and Economy scaling actually favors queuing over spinning up new clusters (it would make queuing worse, not better).
</details>

---

### Question 1059

What statements describe benefits of Snowflake's separation of compute and storage? (Choose two.)

- A. The separation allows independent scaling of computing and storage.
- B. The separation ensures consistent data encryption across all virtual data warehouses.
- C. The separation supports automatic conversion of semi-structured data into structured data for advanced data analysis.
- D. Storage volume growth and compute usage growth can be tightly coupled.
- E. Compute can be scaled up or down without the requirement to add more storage.

<details><summary>Show Answer</summary>

Correct Answer: A, E. The core architectural benefit is decoupled, independent scaling of the two — encryption consistency and semi-structured auto-conversion are unrelated benefits, and 'tightly coupled' growth (D) is the literal opposite of separation.
</details>

---

### Question 1060

What should be used to show the status of partial data loads and loading errors?

- A. The COPY_HISTORY function
- B. The QUERY_HISTORY function
- C. The ACCESS_HISTORY view
- D. The VALIDATE function

<details><summary>Show Answer</summary>

Correct Answer: D. VALIDATE surfaces the row-level errors for a specific past load job. (Edge case worth knowing: COPY_HISTORY is the broader function/view for load *status* — 'loaded'/'load failed'/'partially loaded' — across many loads; VALIDATE drills into the actual per-row errors of one load.)
</details>

---

### Question 1061

What are supported transformations when loading data into a table using the COPY INTO command? (Choose two.)

- A. Column reordering
- B. Column omission
- C. JOIN function
- D. FLATTEN function
- E. GROUP BY function

<details><summary>Show Answer</summary>

Correct Answer: A, B. COPY INTO <table> supports a lightweight SELECT with column reordering/omission and casting — but not JOIN, FLATTEN, or GROUP BY; those require first loading to a staging table and transforming with a full SQL statement.
</details>

---

### Question 1062

Which object can be used with Secure Data Sharing?

- A. View
- B. Materialized view
- C. External table
- D. User-Defined Table Function (UDTF)

<details><summary>Show Answer</summary>

Correct Answer: B. Materialized views can be added to a share (regular views can too, generally through secure views) — but UDTFs and external tables cannot be shared this way.
<br>
<b>Correction: Answer is C</b>
</details>

---

### Question 1063

Which parameter can be set at the account level to set the minimum number of days for which Snowflake retains historical data in Time Travel?

- A. DATA_RETENTION_TIME_IN_DAYS
- B. MIN_DATA_RETENTION_TIME_IN_DAYS
- C. MIN_RETENTION_TIME_IN_DAYS
- D. MAX_CONCURRENCY_LEVEL

<details><summary>Show Answer</summary>

Correct Answer: B. MIN_DATA_RETENTION_TIME_IN_DAYS is the account-level floor; DATA_RETENTION_TIME_IN_DAYS (option A) is the per-object setting that can't go below that floor.
</details>

---

### Question 1064

Which commands are restricted in caller's rights stored procedures? (Choose two.)

- A. SHOW
- B. MERGE
- C. INSERT
- D. DELETE
- E. DESCRIBE

<details><summary>Show Answer</summary>

Correct Answer: A, E. Session/metadata-inspection commands like SHOW and DESCRIBE are restricted in caller's rights procedures (to prevent leaking the caller's session context); DML like MERGE/INSERT/DELETE is unaffected.
</details>

---

### Question 1065

What is the relationship between a Query Profile and a virtual warehouse?

- A. A Query Profile can help right-size virtual warehouses.
- B. A Query Profile defines the hardware specifications of the virtual warehouse.
- C. A Query Profile can help determine the number of virtual warehouses available.
- D. A Query profile automatically scales the virtual warehouse based on the query complexity.

<details><summary>Show Answer</summary>

Correct Answer: A. Reading spillage, pruning, and execution-time stats in a Query Profile is exactly how you decide whether to size a warehouse up, down, or leave it alone — it's diagnostic, not prescriptive/automatic.
</details>

---

### Question 1066

Which transformation is supported by a COPY INTO [table] command?

- A. Filter using a WHERE clause
- B. Filter using a LIMIT keyword
- C. Cast using a SELECT statement
- D. Order using an ORDER BY clause

<details><summary>Show Answer</summary>

Correct Answer: C. Same family as Q1061 — casting via a SELECT is supported; WHERE/LIMIT/ORDER BY are not valid in a COPY INTO's transformation SELECT.
</details>

---

### Question 1067

How can a Snowflake administrator determine which user has accessed a database object that contains sensitive information?

- A. Review the granted privileges for the database object.
- B. Review the row access policy for the database object.
- C. Query the ACCESS_HISTORY view in the ACCOUNT_USAGE schema.
- D. Query the USERS view in the ORGANIZATION_USAGE schema.

<details><summary>Show Answer</summary>

Correct Answer: C. ACCESS_HISTORY is the audit trail of who actually read/wrote which columns/objects — privileges (A) only show who *could* access something, not who did.
</details>

---

### Question 1068

How does conditional data masking work in Snowflake?

- A. It selectively masks plain text data based on user role.
- B. It selectively masks multiple columns at once.
- C. It masks all values in a given column unconditionally.
- D. It selectively masks a column value based on another column's value.

<details><summary>Show Answer</summary>

Correct Answer: D. Conditional masking specifically means the masking policy's CASE logic looks at a *different* column's value to decide whether to mask the target column — role-based masking (A) is the more common but unconditional pattern.
</details>

---

### Question 1069

If a virtual warehouse runs for 60 seconds, shuts down, and then restarts and runs for 30 seconds, for how many seconds is it billed?

- A. 60
- B. 90
- C. 120
- D. 121

<details><summary>Show Answer</summary>

Correct Answer: C. Each start/resume incurs its own 60-second minimum billing charge: 60s (first run, exactly the minimum) + 60s minimum (charged for the 30s second run, since it's under the minimum) = 120s total, not the raw 90s of actual usage.
</details>

---

### Question 1070

What function, combined with the COPY command, should be used to unload data from a relational table into a JSON file?

- A. LATERAL
- B. CAST
- C. FLATTEN
- D. OBJECT_CONSTRUCT

<details><summary>Show Answer</summary>

Correct Answer: D. Same OBJECT_CONSTRUCT pattern as Q1006/Q1053/Q1099 — expect to see this repeated across the bank; it's a favorite exam point.
</details>

---

### Question 1071

What is the primary purpose of a directory table in Snowflake?

- A. To store actual data from external stages.
- B. To automatically expire file URLs for security.
- C. To manage user privileges and access control.
- D. To store file-level metadata about data files in a stage.

<details><summary>Show Answer</summary>

Correct Answer: D. A directory table is purely a metadata catalog (filenames, sizes, URLs, last-modified) layered on a stage — it never stores the actual file bytes.
</details>

---

### Question 1072

Which Snowflake table objects can be shared with other accounts? (Choose two.)

- A. External tables
- B. Permanent tables
- C. Transient tables
- D. Temporary tables
- E. User-Defined Table Functions (UDTFs)

<details><summary>Show Answer</summary>

Correct Answer: B, C. Permanent and transient tables can both be shared; temporary tables (session-scoped) and UDTFs cannot be added to a share.
<br>
<b>Correction: Answer: A and B</b>
</details>

---

### Question 1073

Which metadata table will store the storage utilization information even for dropped tables?

- A. TABLES
- B. TABLE_STORAGE_METRICS
- C. STORAGE_USAGE
- D. TABLE_HISTORY

<details><summary>Show Answer</summary>

Correct Answer: B. TABLE_STORAGE_METRICS keeps reporting storage figures for a table through its Time Travel and Fail-safe retention periods even after it's been dropped.
</details>

---

### Question 1074

How is role hierarchy established in Snowflake?

- A. By assigning privileges to roles
- B. By default when a role is created
- C. By granting one role to another role
- D. By transferring ownership of one role to another role

<details><summary>Show Answer</summary>

Correct Answer: C. GRANT ROLE child_role TO ROLE parent_role builds the inheritance chain — privileges alone don't create hierarchy, and hierarchy isn't automatic at creation time.
</details>

---

### Question 1075

What commands can be used to see what files are stored in a stage? (Choose two.)

- A. LIST
- B. SELECT
- C. GET
- D. LS
- E. DESCRIBE

<details><summary>Show Answer</summary>

Correct Answer: A, D. LIST (and its alias LS) enumerates staged files; SELECT queries a directory table (not the raw file listing directly), GET downloads files, DESCRIBE shows stage properties, not contents.
</details>

---

### Question 1076

Which stages are created by default, with no need to use the CREATE STAGE command? (Choose two.)

- A. External stage
- B. Internal named stage
- C. Named stage
- D. Table stage
- E. User stage

<details><summary>Show Answer</summary>

Correct Answer: D, E. Every table and every user automatically gets its own implicit stage — named/internal/external stages must always be explicitly created.
</details>

---

### Question 1077

While working with unstructured data, which file function generates a Snowflake-hosted file URL to a staged file using the stage name and relative file path as inputs?

- A. BUILD_STAGE_FILE_URL
- B. GET_ABSOLUTE_PATH
- C. GET_PRESIGNED_URL
- D. BUILD_SCOPED_FILE_URL

<details><summary>Show Answer</summary>

Correct Answer: A. Same function as Q1014, phrased differently — BUILD_STAGE_FILE_URL is the non-expiring, privilege-gated file URL generator.
</details>

---

### Question 1078

Who can create and manage reader accounts? (Choose two.)

- A. A user with ACCOUNTADMIN role
- B. A user with SECURITYADMIN role
- C. A user with SYSADMIN role
- D. A user with ORGADMIN role
- E. A user with CREATE ACCOUNT privilege

<details><summary>Show Answer</summary>

Correct Answer: A, E. ACCOUNTADMIN can always manage reader accounts; otherwise any role explicitly granted the global CREATE ACCOUNT privilege can too — SECURITYADMIN/SYSADMIN/ORGADMIN have no inherent reader-account authority.
</details>

---

### Question 1079

Which command allows for continuous loading of data files as soon as they are available in a stage?

- A. COPY INTO [table]
- B. ALTER STAGE
- C. CREATE PIPE
- D. GET

<details><summary>Show Answer</summary>

Correct Answer: C. CREATE PIPE sets up Snowpipe, which auto-ingests new files (via event notification or REST call) as soon as they land — COPY INTO is the batch/manual equivalent Snowpipe runs under the hood.
</details>

---

### Question 1080

What is an advantage of using database roles instead of granting privileges on objects directly to a share in Snowflake?

- A. Easier management of cross-region data sharing
- B. Greater flexibility in including objects from multiple databases
- C. More control over object-level access for different user groups
- D. Reduction in the number of shares required for different objects in the same database

<details><summary>Show Answer</summary>

Correct Answer: C. Database roles let you compose fine-grained, reusable bundles of object grants and layer them for different consumer groups — direct share-level grants are flatter and harder to segment.
</details>

---

### Question 1081

What is the order of precedence (highest to lowest) of network policies when applied at the account, user, and security integrations layers?

- A. Account, security integration, user
- B. Account, security integration, user
- C. User, security integration, account
- D. User, account, security integration

<details><summary>Show Answer</summary>

Correct Answer: C. A user-level network policy always wins over a security-integration-level policy, which in turn wins over the account-level (broadest, lowest-precedence) policy.
</details>

---

### Question 1082

Which type of Snowflake virtual warehouse provides 10 times the memory for each node, and is recommended for larger workloads like Machine Learning (ML) training?

- A. A Size X-Large Warehouse
- B. A standard warehouse
- C. A multi-cluster warehouse
- D. A Snowpark-optimized warehouse

<details><summary>Show Answer</summary>

Correct Answer: D. Snowpark-optimized warehouses are purpose-built with substantially more memory per node (default config is commonly cited as 16x in current docs, historically described as ~10x) for memory-hungry single-node workloads like ML training.
</details>

---

### Question 1083

Which common query issues can be identified by the Query Profile? (Choose two.)

- A. Insufficient credit quota
- B. Inefficient query pruning
- C. Excessive query pruning
- D. Exploding joins
- E. Credit usage that exceeds a set threshold

<details><summary>Show Answer</summary>

Correct Answer: B, D. Same theme as Q1023/Q1035 — pruning efficiency and cartesian/exploding joins are the two classic Query Profile diagnoses. Credits/quota aren't things Query Profile reports on.
</details>

---

### Question 1084

In Snowflake, what allows a user to perform recursive queries?

- A. QUALIFY
- B. LATERAL
- C. PIVOT
- D. CONNECT BY

<details><summary>Show Answer</summary>

Correct Answer: D. CONNECT BY is Snowflake's Oracle-style hierarchical/recursive query syntax (recursive CTEs are the ANSI-standard alternative, but weren't offered as an option here).
</details>

---

### Question 1085

A user wants to create objects within a schema but wants to restrict other users' ability to grant privileges on these objects. What configuration should be used to create the schema?

- A. Use a regular (non-managed) schema.
- B. Use a managed access schema.
- C. Use a transient schema.
- D. Set the RESTRICT_GRANTS parameter.

<details><summary>Show Answer</summary>

Correct Answer: B. A managed access schema centralizes all further granting authority with the schema owner, taking that ability away from individual object owners — the opposite of a regular schema's default behavior. ('Transient schema' and 'RESTRICT_GRANTS' aren't real Snowflake constructs.)
</details>

---

### Question 1086

What is the MOST cost-effective way to resolve memory spillage in a virtual warehouse?

- A. Enable automatic clustering.
- B. Enable the query acceleration service.
- C. Enable the search optimization service.
- D. Convert to a Snowpark-optimized warehouse.

<details><summary>Show Answer</summary>

Correct Answer: D. None of these four is Snowflake's *primary* documented fix for spillage (simply resizing the warehouse up is) — but among the given options, a Snowpark-optimized warehouse's extra memory per node is the only one that actually targets memory pressure; clustering and search optimization solve pruning/lookup problems, not spillage, and QAS targets scan-heavy single queries.
</details>

---

### Question 1087

What objects in Snowflake are supported by Dynamic Data Masking? (Choose two.)

- A. Views
- B. Materialized views
- C. Tables
- D. External tables
- E. Future grants

<details><summary>Show Answer</summary>

Correct Answer: A, C. Masking policies attach to columns on tables and views; materialized views and external tables are not supported targets.
</details>

---

### Question 1088

A user has created a dashboard in Snowsight and wants to share it with colleagues. How can the dashboard be shared?

- A. By creating a private Data Exchange.
- B. By using the share option within Snowsight.
- C. By using a Direct Share with another account.
- D. By creating a listing on Snowflake Marketplace.

<details><summary>Show Answer</summary>

Correct Answer: B. Snowsight dashboards have their own native, lightweight 'Share' control for granting other users/roles in the same account access — no Secure Data Sharing objects (shares, exchanges, listings) are involved.
</details>

---

### Question 1089

When would Snowsight automatically detect if a target account is in a different region and enable cross-cloud auto-fulfillment?

- A. When using a paid listing on the Snowflake Marketplace.
- B. When using a private listing on the Snowflake Marketplace.
- C. When using a personalized listing on the Snowflake Marketplace.
- D. When using a Direct Share with another account.

<details><summary>Show Answer</summary>

Correct Answer: B. Confirmed against current docs: "For all listings shared with specific consumer accounts [i.e., private listings], Snowsight automatically detects whether the target account is in a different region and enables auto-fulfillment." Direct Shares (D) don't get this automatic cross-region detection/handling.
</details>

---

### Question 1090

Which languages require that User-Defined Function (UDF) handlers be written inline? (Choose two.)

- A. Java
- B. JavaScript
- C. Scala
- D. Python
- E. SQL

<details><summary>Show Answer</summary>

Correct Answer: B, E. JavaScript and SQL UDF handler code must be written inline in the CREATE FUNCTION statement; Java, Python, and Scala handlers can instead reference a pre-staged file.
</details>

---

### Question 1091

Which task privilege does a Snowflake role need in order to suspend or resume a task?

- A. USAGE
- B. OPERATE
- C. MONITOR
- D. OWNERSHIP

<details><summary>Show Answer</summary>

Correct Answer: B. OPERATE on a task is specifically what's needed to suspend/resume it — MONITOR only lets you view state/history, and OWNERSHIP is broader than strictly necessary.
</details>

---

### Question 1092

What is a directory table in Snowflake?

- A. A separate database object that is used to store file-level metadata.
- B. An implicit object layered on a stage that is used to store file-level metadata.
- C. A database object with grantable privileges for unstructured data tasks.
- D. A Snowflake table specifically designed for storing unstructured files.

<details><summary>Show Answer</summary>

Correct Answer: B. A directory table isn't a standalone object with its own OWNERSHIP/grants — it's an implicit layer tied to (and inheriting privileges from) its parent stage.
</details>

---

### Question 1093

What factors impact storage costs in Snowflake? (Choose two.)

- A. The account type
- B. The storage file format
- C. The region used
- D. The type of data being stored
- E. The cloud platform being used

<details><summary>Show Answer</summary>

Correct Answer: C, E. Per-TB storage rates vary by cloud platform and region — not by account/edition type, file format, or the kind of data stored.
</details>

---

### Question 1094

Which ACCOUNT_USAGE database role provides visibility into policy-related information?

- A. USAGE_VIEWER
- B. GOVERNANCE_VIEWER
- C. OBJECT_VIEWER
- D. SECURITY_VIEWER

<details><summary>Show Answer</summary>

Correct Answer: B. GOVERNANCE_VIEWER is the built-in database role scoped to policy/tag/governance-related ACCOUNT_USAGE views.
</details>

---

### Question 1095

How should clustering be used to optimize the performance of queries that run on a very large table?

- A. Manually re-cluster the table regularly.
- B. Choose one high cardinality column as the clustering key.
- C. Use the column that is most frequently used in query select clauses as the clustering key.
- D. Access the average table depth to identify if clustering is impacting the query.

<details><summary>Show Answer</summary>

Correct Answer: D. Check clustering (average) depth first — Automatic Clustering already handles re-clustering, an overly high-cardinality key can hurt more than help, and the clustering key should reflect WHERE/filter predicates, not SELECT-list columns.
</details>

---

### Question 1096

Which privilege must be granted by one role to another role, and cannot be revoked?

- A. MONITOR
- B. OPERATE
- C. OWNERSHIP
- D. ALL

<details><summary>Show Answer</summary>

Correct Answer: C. OWNERSHIP can only be *transferred* to another role (by re-granting it), never simply revoked while leaving the object ownerless.
</details>

---

### Question 1097

How can performance be optimized for a query that returns a small amount of data from a very large base table?

- A. Use clustering keys.
- B. Create materialized views.
- C. Use the search optimization service.
- D. Use the query acceleration service.

<details><summary>Show Answer</summary>

Correct Answer: C. Same point-lookup pattern as Q1048/Q1031.
</details>

---

### Question 1098

A column named "Data" contains VARIANT data and stores values as follows:
`{ "employee": { "name": "John", "age": 30 }, "location": "New York" }`
How will the user extract the employee's name from the data?

- A. data.employee.name
- B. data:employee:name
- C. data:employee.name
- D. data.employee:name

<details><summary>Show Answer</summary>

Correct Answer: C. A colon always separates the VARIANT column name from the first-level key; subsequent nesting can then use either dot or colon notation. `data:employee.name` is the textbook form Snowflake documentation demonstrates.

**Edge case worth knowing: `data:employee:name` (option B) is **also valid** — Snowflake's docs confirm dot and colon are interchangeable for levels after the first colon. Don't be thrown if you see both forms used interchangeably on the real exam; `data.employee.name` (no leading colon) and `data.employee:name` are the genuinely invalid ones.**
</details>

---

### Question 1099

Use of which Snowflake function is recommended when unloading data from a relational table into a JSON file?

- A. TO_JSON
- B. TO_VARIANT
- C. OBJECT_INSERT
- D. OBJECT_CONSTRUCT

<details><summary>Show Answer</summary>

Correct Answer: D. Same recurring OBJECT_CONSTRUCT answer as Q1006/Q1053/Q1070.
</details>

---

### Question 1100

Which command parameter should be used to generate a single file when unloading data from a Snowflake table into a file?

- A. PARTITION BY
- B. SINGLE = FALSE
- C. SINGLE = TRUE
- D. OVERWRITE = TRUE

<details><summary>Show Answer</summary>

Correct Answer: C. SINGLE = TRUE (the same parameter from Q1039) forces a single output file instead of the default multi-file split.
</details>

---



====================================================================================================
# snowpro_1101_1200.md
====================================================================================================

# SnowPro Core Practice Questions (1101–1200)

*Cleaned, reformatted, and fact-checked against current Snowflake documentation (as of July 2026). Answers are collapsed by default — click "Show Answer" to reveal. Corrections to the original source, if any, are flagged with ⚠ Updated.*

---

### Question 1101
Which of the following describes how multiple Snowflake accounts in a single organization relate to various cloud providers?

- A. Each Snowflake account can be hosted in a different cloud vendor and region.
- B. Each Snowflake account must be hosted in a different cloud vendor and region.
- C. All accounts must be hosted in the same cloud vendor and region.
- D. Each Snowflake account can be hosted in a different cloud vendor, but must be in the same region.

<details><summary>Show Answer</summary>
Correct Answer: A. Accounts within an organization are independent and can each be provisioned on any supported cloud platform and region — there's no requirement to match vendor or region across accounts.
</details>

---

### Question 1102
Which commands should be used to grant the privilege allowing a role to select data from all current tables and any tables that will be created later in a schema? (Choose two.)

- A. grant USAGE on all tables in schema SCHEMA to role MYROLE;
- B. grant USAGE on future tables in schema SCHEMA to role MYROLE;
- C. grant SELECT on all tables in schema DB1.SCHEMA to role MYROLE;
- D. grant SELECT on future tables in schema DB1.SCHEMA to role MYROLE;
- E. grant SELECT on all tables in database DB1 to role MYROLE;
- F. grant SELECT on future tables in database DB1 to role MYROLE;

<details><summary>Show Answer</summary>
Correct Answer: C, D. GRANT ... ON ALL TABLES covers tables that exist right now; GRANT ... ON FUTURE TABLES covers tables created afterward — you need both to cover "current and future."
</details>

---

### Question 1103
Which table type has a Fail-safe of 7 days?

- A. Temporary table
- B. Transient table
- C. Permanent table
- D. External table

<details><summary>Show Answer</summary>
Correct Answer: C. Permanent tables get a fixed 7-day Fail-safe period. Temporary and transient tables have 0 days of Fail-safe, and external tables don't participate in Fail-safe at all since Snowflake doesn't own the underlying data.
</details>

---

### Question 1104
How does Snowflake enable OAuth?

- A. By creating an external integration
- B. By configuring a security integration
- C. By establishing IP allowed lists and IP blocked lists
- D. By using SnowSQL to enable an OAuth connection using the SAML protocol

<details><summary>Show Answer</summary>
Correct Answer: B. OAuth (Snowflake OAuth or an external OAuth provider) is configured through a CREATE SECURITY INTEGRATION object.
</details>

---

### Question 1105
Which type of workload traditionally benefits from the use of the query acceleration service?

- A. Workloads with a predictable data volume for each query
- B. Workloads that include ad-hoc data analyses
- C. Queries with small scans and non-selective filters
- D. Queries that do not have filters or aggregation

<details><summary>Show Answer</summary>
Correct Answer: B. QAS is designed for outlier queries with unpredictable data volume — ad-hoc analytics is the classic example — plus large scans with selective filters.
</details>

---

### Question 1106
Which Snowflake object is supported by both database replication and replication groups?

- A. Pipes
- B. Users
- C. Stages
- D. Materialized views

<details><summary>Show Answer</summary>
Correct Answer: C. Stages are database-level objects that travel with a replicated database, and they're also among the object types replication groups can include.
<br>
<b>Correction: ANS:-D</b>
</details>

---

### Question 1107
When unloading data, which combination of parameters should be used to differentiate between empty strings and NULL values? (Choose two.)

- A. FIELD_OPTIONALLY_ENCLOSED_BY
- B. EMPTY_FIELD_AS_NULL
- C. NULL_IF
- D. ESCAPE_UNENCLOSED_FIELD
- E. DATE_FORMAT

<details><summary>Show Answer</summary>
Correct Answer: A, B. FIELD_OPTIONALLY_ENCLOSED_BY quotes empty-string values so they're distinguishable from unquoted (NULL) fields, and setting EMPTY_FIELD_AS_NULL = FALSE prevents empty strings from being unloaded as NULL.
</details>

---

### Question 1108
Which role must be used to create resource monitors?

- A. SECURITYADMIN
- B. ACCOUNTADMIN
- C. SYSADMIN
- D. ORGADMIN

<details><summary>Show Answer</summary>
Correct Answer: B. Only ACCOUNTADMIN (or a role explicitly granted the CREATE RESOURCE MONITOR privilege) can create resource monitors.
</details>

---

### Question 1109
What step does Snowflake recommend when loading data from a Stage?

- A. Use PURGE when using the COPY INTO [table] command
- B. Use REMOVE when using the COPY INTO [table] command
- C. Use the LOAD_HISTORY function to view the status of loaded files
- D. Use the COPY_HISTORY function to update the status of loaded files

<details><summary>Show Answer</summary>
Correct Answer: A. Setting PURGE = TRUE on COPY INTO &lt;table&gt; automatically deletes staged files once they've loaded successfully, which keeps the stage clean and avoids accidental reloads.
</details>

---

### Question 1110
How can a user MINIMIZE Continuous Data Protection costs when using large, high-churn dimension tables?

- A. Create transient tables and periodically COPY them to permanent tables.
- B. Create temporary tables and periodically copy them to permanent tables.
- C. Create regular tables with extended Time Travel and Fail-safe settings.
- D. Create transient tables.

<details><summary>Show Answer</summary>
Correct Answer: D. Transient tables skip Fail-safe entirely, which is the biggest lever for reducing CDP storage costs on high-churn tables that don't need that extra protection.
</details>

---

### Question 1111
Which Snowsight feature can be used to perform data manipulations and transformations using a programming language?

- A. SnowSQL
- B. Dashboards
- C. Worksheets
- D. Provider Studio

<details><summary>Show Answer</summary>
Correct Answer: C. Snowsight Worksheets support SQL and Python (via Snowpark), letting you transform data directly in the browser-based editor.
</details>

---

### Question 1112
In Snowflake's data security framework, how does column-level security contribute to the protection of sensitive information? (Choose two.)

- A. Implementation of column-level security will optimize query performance.
- B. Column-level security supports encryption of the entire database.
- C. Column-level security ensures the table can mask the data.
- D. Column-level security limits access to specific columns within a table based on user privileges.
- E. Column-level security allows the application of a masking policy to a column within a table or view.

<details><summary>Show Answer</summary>
Correct Answer: D, E. Column-level security restricts who can see specific columns and is implemented via masking policies applied to those columns.
</details>

---

### Question 1113
How does Snowflake utilize clustering information to improve query performance?

- A. It prunes micro-partitions based on Clustering metadata.
- B. It compresses the data within micro-partitions for faster querying.
- C. It automatically allocates additional resources to improve query execution.
- D. It organizes clustering information to speed-up data retrieval from storage.

<details><summary>Show Answer</summary>
Correct Answer: A. Snowflake stores min/max metadata per micro-partition and uses it to prune (skip) partitions that can't match the query's filter, based on how well-clustered the table is.
</details>

---

### Question 1114
How can staged files be removed during data loading once the files have loaded successfully?

- A. Use the DROP command.
- B. Use the PURGE copy option.
- C. Use the REMOVE=TRUE parameter.
- D. Use the DELETE_AFTER_LOAD copy option.

<details><summary>Show Answer</summary>
Correct Answer: B. The PURGE copy option on COPY INTO &lt;table&gt; deletes files from the stage automatically after a successful load.
</details>

---

### Question 1115
What objects can be cloned within Snowflake? (Choose two.)

- A. Schemas
- B. Users
- C. External tables
- D. Internal named stages
- E. External named stages

<details><summary>Show Answer</summary>
Correct Answer: A, D. Schemas and internal named stages support zero-copy cloning. Users aren't cloneable objects, and external stages/tables reference external storage rather than Snowflake-managed data, so they aren't cloned the same way.
</details>

---

### Question 1116
What can be used to process unstructured data?

- A. Directory tables
- B. The COPY INTO command
- C. External functions
- D. Snowpipe

<details><summary>Show Answer</summary>
Correct Answer: A. Directory tables sit on top of a stage and expose file-level metadata (name, size, URL, etc.) for unstructured files, letting you query and process them like table rows.
</details>

---

### Question 1117
Which type of workload is recommended for Snowpark-optimized virtual warehouses?

- A. Workloads with ad hoc analytics
- B. Workloads that have large memory requirements
- C. Workloads with large data volumes for each query
- D. Workloads that are queried with small table scans and selective filters

<details><summary>Show Answer</summary>
Correct Answer: B. Snowpark-optimized warehouses provide significantly more memory per node, which benefits memory-intensive workloads like ML training and large UDF/stored-procedure processing.
</details>

---

### Question 1118
What is the benefit of using the STRIP_OUTER_ARRAY parameter with the COPY INTO [table] command when loading data from a JSON file into a table?

- A. It flattens multiple arrays into a single row.
- B. It removes the outer array structure and loads separate rows of data.
- C. It transforms a pivoted table into an array.
- D. It tokenizes each data string using the defined delimiters.

<details><summary>Show Answer</summary>
Correct Answer: B. STRIP_OUTER_ARRAY strips the enclosing `[ ]` from the JSON so each element becomes its own row instead of the whole array loading as one row.
</details>

---

### Question 1119
A query containing a WHERE clause is running longer than expected. The Query Profile shows that all micro-partitions are being scanned. How should this query be optimized?

- A. Create a view on the table.
- B. Add a clustering key to the table.
- C. Add a LIMIT clause to the query.
- D. Add a Dynamic Data Masking policy to the table.

<details><summary>Show Answer</summary>
Correct Answer: B. A clustering key co-locates related rows, improving pruning so filtered queries scan far fewer micro-partitions.
</details>

---

### Question 1120
Which access control entity in Snowflake can be created as part of a hierarchy within an account?

- A. Securable object
- B. Role
- C. Privilege
- D. User

<details><summary>Show Answer</summary>
Correct Answer: B. Roles can be granted to other roles, forming a role hierarchy that determines how privileges cascade upward.
</details>

---

### Question 1121
When an object is created in Snowflake, who owns the object?

- A. The PUBLIC role
- B. The default role
- C. The current active primary role
- D. The owner of the parent schema

<details><summary>Show Answer</summary>
Correct Answer: C. Ownership is assigned to whichever role is active (the primary role in the session) at the moment the object is created.
</details>

---

### Question 1122
What is the MINIMUM Snowflake edition that must be used in order to see the ACCESS_HISTORY view?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: B. Access History (the ACCESS_HISTORY view in ACCOUNT_USAGE) is an Enterprise Edition (or higher) feature — confirmed current as of 2026.
</details>

---

### Question 1123
Which role is responsible for managing the billing and credit data within Snowflake?

- A. ORGADMIN
- B. ACCOUNTADMIN
- C. SYSADMIN
- D. SECURITYADMIN

<details><summary>Show Answer</summary>
Correct Answer: B. ACCOUNTADMIN has visibility into and manages billing/credit usage at the account level.
</details>

---

### Question 1124
What can be used to identify the database, schema, stage, and file path to a set of files, and to allow a role that has sufficient privileges on the stage to access the files?

- A. A scoped URL
- B. A file URL
- C. A pre-signed URL
- D. A directory table

<details><summary>Show Answer</summary>
Correct Answer: B. A file URL is a permanent URL that encodes the db/schema/stage/path and relies on the requesting role having stage privileges — unlike a scoped URL (tied to a query result and expires) or a pre-signed URL (time-limited, no login required).
</details>

---

### Question 1125
Which command is used to remove files from either external cloud storage or an internal stage?

- A. DELETE
- B. REMOVE
- C. TRUNCATE
- D. DROP

<details><summary>Show Answer</summary>
Correct Answer: B. REMOVE deletes files from a stage (internal or external).
</details>

---

### Question 1126
How does Snowflake recommend defining a clustering key on a high-cardinality column that includes a 15 digit ID numbered column, ID_NUMBER?

- A. Use the column ID_NUMBER as the cluster key.
- B. Cast the ID_NUMBER column to a string.
- C. Create an expression on the ID_NUMBER column (e.g. TRUNCATE) to reduce the cardinality.
- D. High cardinality columns cannot be used as cluster keys.

<details><summary>Show Answer</summary>
Correct Answer: C. Applying an expression (like truncating or bucketing the value) reduces effective cardinality, which makes clustering maintenance more efficient on very high-cardinality columns.
</details>

---

### Question 1127
While unloading data into a stage, how can the user ensure that the output will be a single file?

- A. Use the copy option FILES=SINGLE.
- B. Use the copy option SINGLE=TRUE.
- C. Use the GET option SINGLE=TRUE.
- D. Use the GET option FILES=SINGLE.

<details><summary>Show Answer</summary>
Correct Answer: B. SINGLE = TRUE on COPY INTO &lt;location&gt; forces all unloaded data into one file.
</details>

---

### Question 1128
Which query types will have significant performance improvement when run using the search optimization service? (Choose two.)

- A. Range searches
- B. Equality point lookups searches
- C. Substring searches
- D. Queries with IN predicates
- E. Queries with aggregation

<details><summary>Show Answer</summary>
Correct Answer: B, C. Search optimization is built for highly selective point lookups (equality) and substring/regex matches. Current Snowflake documentation confirms it also accelerates IN predicates and geospatial queries, but B and C remain the standard designated answer pair for this exam question. Range scans and aggregations are not what it targets — those are clustering/warehouse-sizing problems.
<br>
<b>
CORRECTION:-
<br>
B. Equality point lookups searches and D. Queries with IN predicates.
</b>
</details>

---

### Question 1129
Which Query Profile operator is considered a DML operator?

- A. ExternalScan
- B. Flatten
- C. Merge
- D. Sort

<details><summary>Show Answer</summary>
Correct Answer: C. Merge performs data manipulation (insert/update/delete in one statement), making it a DML operator in the Query Profile.
</details>

---

### Question 1130
Masking policies are created at what level in Snowflake?

- A. Table
- B. Column
- C. Schema
- D. Database

<details><summary>Show Answer</summary>
Correct Answer: C. A masking policy is a schema-level object (CREATE MASKING POLICY); it's later attached ("set") to specific table or view columns.
</details>

---

### Question 1131
What would cause different results to be returned when running the same query twice?

- A. SAMPLE is used on the set.
- B. SAMPLE is used and the seed is not set.
- C. Fraction-based sampling is used.
- D. Fixed-size sampling is used.

<details><summary>Show Answer</summary>
Correct Answer: B. Without a REPEATABLE seed, SAMPLE picks a new random set of rows on each execution.
</details>

---

### Question 1132
What are type predicates used for?

- A. Extracting data from a VARIANT column
- B. Casting a value in a VARIANT column to a particular data type
- C. Determining if a value in a VARIANT column is a particular data type
- D. Manipulating objects and arrays in a VARIANT column

<details><summary>Show Answer</summary>
Correct Answer: C. Type predicates (IS_ARRAY, IS_OBJECT, IS_VARCHAR, etc.) test whether a VARIANT value is a given type.
</details>

---

### Question 1133
Which table function is used to perform additional processing on the results of a previously-run query?

- A. QUERY_HISTORY
- B. RESULT_SCAN
- C. DESCRIBE_RESULTS
- D. LAST_QUERY_ID

<details><summary>Show Answer</summary>
Correct Answer: B. RESULT_SCAN(query_id) turns a prior query's cached result set into a table you can further query.
</details>

---

### Question 1134
Which actions can be performed using a resource monitor in Snowflake? (Choose two.)

- A. Monitor the performance of individual queries in real-time.
- B. Automatically allocate more storage space to a virtual warehouse.
- C. Modify the queries being executed within a virtual warehouse.
- D. Suspend a virtual warehouse when its credit usage reaches a defined limit.
- E. Trigger a notification to account administrators when credit usage reaches a specified threshold.

<details><summary>Show Answer</summary>
Correct Answer: D, E. Resource monitors track credit consumption and can suspend warehouses or fire notifications at defined thresholds — they don't touch query performance, storage, or query content.
</details>

---

### Question 1135
Which Snowflake native tool can be used to diagnose and troubleshoot network connections?

- A. snowcli
- B. Snowflake Python Connector
- C. Snowsight
- D. snowcd

<details><summary>Show Answer</summary>
Correct Answer: D. SnowCD (Snowflake Connectivity Diagnostic Tool) checks network connectivity to the Snowflake service and dependent endpoints.
</details>

---

### Question 1136
Why would a Snowflake user load JSON data into a VARIANT column instead of a String column?

- A. A VARIANT column is more secure than a string column.
- B. A VARIANT column compresses data and a String column does not.
- C. A VARIANT column can be used to query hierarchical data directly, and a string column cannot.
- D. A VARIANT column will have better query performance than a string column.

<details><summary>Show Answer</summary>
Correct Answer: C. VARIANT stores parsed semi-structured data, so you can query nested fields directly with dot/bracket notation rather than re-parsing a raw string every time.
</details>

---

### Question 1137
How can a 5 GB table be downloaded into a single file MOST efficiently?

- A. Keep the default MAX_FILE_SIZE of 16 MB.
- B. Set the MAX_FILE_SIZE to 5 GB.
- C. Set the SINGLE parameter to TRUE.
- D. Use a regular expression in the stage specifications of the COPY command.

<details><summary>Show Answer</summary>
Correct Answer: C. SINGLE = TRUE on the unload guarantees one output file regardless of size, which is the standard mechanism (rather than manually tuning MAX_FILE_SIZE).
</details>

---

### Question 1138
Which Security models are used in Snowflake to manage access control? (Choose two.)

- A. Discretionary Access Control (DAC)
- B. Identity Access Management (IAM)
- C. Mandatory Access Control (MAC)
- D. Role-Based Access Control (RBAC)
- E. Security Assertion Markup Language (SAML)

<details><summary>Show Answer</summary>
Correct Answer: A, D. Snowflake combines DAC (object owners control access) with RBAC (privileges granted to roles, roles granted to users).
</details>

---

### Question 1139
Which Snowflake governance feature allows users to assign metadata labels to improve data governance and database access control?

- A. Secure functions
- B. Secure views
- C. Object tagging
- D. Row-level security

<details><summary>Show Answer</summary>
Correct Answer: C. Object tagging attaches key-value metadata labels to objects/columns, which can also drive classification and masking/access policies.
</details>

---

### Question 1140
What is the MINIMUM Snowflake edition that supports database replication?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: A. Current Snowflake documentation confirms database and share replication are available to all editions, including Standard. Replication of other account objects and failover/failback capability require Business Critical Edition or higher.
</details>

---

### Question 1141
Which Snowflake function and command combination should be used to convert rows in a relational table to a single VARIANT column, and unload the rows into a file in JSON format? (Choose two.)

- A. PUT
- B. GET
- C. COPY INTO
- D. EXPORT
- E. OBJECT_CONSTRUCT

<details><summary>Show Answer</summary>
Correct Answer: C, E. OBJECT_CONSTRUCT builds a VARIANT (JSON-like) object from row data, and COPY INTO &lt;location&gt; unloads the result to a file.
</details>

---

### Question 1142
What Snowflake recommendation is designed to ensure that staged data is only loaded once?

- A. Partitioning staged data files
- B. Loading only the most recently-staged data files
- C. Removing files after loading
- D. Identifying and removing duplicates after each data load

<details><summary>Show Answer</summary>
Correct Answer: C. Removing (purging) files once they've loaded prevents them from being picked up again in a later COPY INTO run.
</details>

---

### Question 1143
Which privilege grants the ability to set a column-level security masking policy on a table or view column?

- A. APPLY MASKING POLICY
- B. CREATE MASKING POLICY
- C. MODIFY MASKING POLICY
- D. SET MASKING POLICY

<details><summary>Show Answer</summary>
Correct Answer: A. APPLY MASKING POLICY lets a role attach an existing masking policy to a column via ALTER TABLE/VIEW.
</details>

---

### Question 1144
When sharing data in Snowflake, what privileges does a Provider need to grant along with a share? (Choose two.)

- A. USAGE on the specific tables in the database.
- B. MODIFY on the specific tables in the database.
- C. SELECT on the specific tables in the database.
- D. USAGE on the database and the schema containing the tables to share.
- E. OPERATE on the database and the schema containing the tables to share.

<details><summary>Show Answer</summary>
Correct Answer: C, D. Consumers need USAGE on the database and schema to "see into" them, plus SELECT on the actual objects to query the data. Shared data is always read-only, so MODIFY/OPERATE aren't relevant.
</details>

---

### Question 1145
How can the Query Profile be used to troubleshoot a problematic query?

- A. It will indicate if a virtual warehouse memory is too small to run the query.
- B. It will indicate if a user lacks the privileges needed to run the query.
- C. It will indicate if a virtual warehouse is in auto-scale mode.
- D. It will indicate if the user has enough Snowflake credits to run the query.

<details><summary>Show Answer</summary>
Correct Answer: A. Query Profile surfaces spilling to local/remote disk, which is the classic signal that the warehouse doesn't have enough memory for the query.
</details>

---

### Question 1146
Which data type can be used for floating-point numbers without losing precision?

- A. BINARY
- B. VARIANT
- C. INTEGER
- D. DOUBLE

<details><summary>Show Answer</summary>
Correct Answer: D. DOUBLE (a.k.a. FLOAT/DOUBLE PRECISION) is Snowflake's floating-point type, distinct from the fixed-precision NUMBER type used for exact decimals.
</details>

---

### Question 1147
Which data sharing option allows a Snowflake user to set up and manage a group of accounts and offer a share to that group?

- A. Standard listing
- B. Paid listing
- C. Direct Share
- D. Data Exchange

<details><summary>Show Answer</summary>
Correct Answer: D. A Data Exchange lets a provider manage an invite-only group of accounts and publish listings privately to that group — this remains current Snowflake terminology as of 2026.
</details>

---

### Question 1148
What kind of authentication do Snowpipe REST endpoints use?

- A. OAuth
- B. Key-based authentication (Key Pair)
- C. Username and password
- D. Single Sign-on

<details><summary>Show Answer</summary>
Correct Answer: B. Snowpipe REST API calls are authenticated with a JWT signed using key-pair (RSA) authentication.
</details>

---

### Question 1149
What are the possible values within a METADATA$ACTION column in a Snowflake stream? (Choose two.)

- A. INSERT
- B. UPDATE
- C. DELETE
- D. TRUNCATE
- E. UPSERT

<details><summary>Show Answer</summary>
Correct Answer: A, C. Streams only ever record INSERT and DELETE; an UPDATE shows up as a paired DELETE + INSERT row.
</details>

---

### Question 1150
What is the MINIMUM Snowflake edition that offers data protection for extremely sensitive data, such as Protected Health Information (PHI)?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: C. Business Critical Edition is designed for extremely sensitive data (e.g., PHI under HIPAA/HITRUST).
</details>

---

### Question 1151
What takes the highest precedence in Snowflake format options, when specified in multiple places during data loading?

- A. The stage definition
- B. The table definition
- C. The use of a COPY INTO [table] statement
- D. The default account parameters

<details><summary>Show Answer</summary>
Correct Answer: C. Format options specified directly in the COPY INTO statement override the table definition, which in turn overrides the stage definition, which overrides account defaults.
</details>

---

### Question 1152
Which service or tool is a Command Line Interface (CLI) client used for connecting to Snowflake to execute SQL queries?

- A. Snowsight
- B. snowcd
- C. Snowpark
- D. SnowSQL

<details><summary>Show Answer</summary>
Correct Answer: D. SnowSQL is Snowflake's official CLI client for running SQL and performing DML operations, including data loading/unloading.
</details>

---

### Question 1153
What Snowflake objects can contain custom application logic written in JavaScript? (Choose two.)

- A. Stored procedures
- B. Stages
- C. Tasks
- D. Views
- E. User-Defined Functions (UDFs)

<details><summary>Show Answer</summary>
Correct Answer: A, E. Stored procedures and UDFs can be written in JavaScript (among other supported languages). Stages, tasks, and views don't hold procedural logic.
</details>

---

### Question 1154
What is the MINIMUM Snowflake edition required to use the Security Integration for SAML SSO?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: A. Current Snowflake documentation places no edition-level restriction on the SAML2 security integration for SSO — it's available starting at Standard Edition.
</details>

---

### Question 1155
Which command should be used to assign a key to a Snowflake user who needs to connect using key pair authentication?

- A. ALTER USER jsmith SET RSA_PUBLIC_KEY='...';
- B. ALTER USER jsmith SET ENCRYPTED_KEY='...';
- C. ALTER USER jsmith SET PUBLIC_KEY='...';
- D. ALTER ACCOUNT SET RSA_PUBLIC_KEY='...';

<details><summary>Show Answer</summary>
Correct Answer: A. ALTER USER ... SET RSA_PUBLIC_KEY assigns the user's public key so Snowflake can verify JWTs signed with the matching private key.
</details>

---

### Question 1156
Secured Data Sharing is allowed for which Snowflake database objects? (Choose two.)

- A. Tables
- B. User-Defined Table Functions (UDTFs)
- C. Secure Views
- D. Stored procedures
- E. Worksheets

<details><summary>Show Answer</summary>
Correct Answer: A, C. Tables and secure views (along with secure UDFs and a few other secure object types) can be shared. UDTFs, stored procedures, and worksheets cannot be shared.
</details>

---

### Question 1157
What optional properties can a Snowflake user set when creating a virtual warehouse? (Choose two.)

- A. Auto-suspend
- B. Cache size
- C. Auto-resume
- D. Resource monitor
- E. Storage size

<details><summary>Show Answer</summary>
Correct Answer: A, C. AUTO_SUSPEND and AUTO_RESUME are configurable warehouse properties. Cache size and storage size aren't warehouse-level settings, and resource monitors are separate objects assigned to warehouses rather than a warehouse creation property.
</details>

---

### Question 1158
What is the purpose of the use of the VALIDATE command?

- A. To retry any queries that encountered an error
- B. To verify that a SELECT query will run without error
- C. To prevent a PUT statement from running if an error occurs
- D. To see all errors from a previously run COPY INTO [table] statement

<details><summary>Show Answer</summary>
Correct Answer: D. The VALIDATE function returns the errors (if any) encountered during a specific prior COPY INTO &lt;table&gt; load.
</details>

---

### Question 1159
Which function is used to unload a relational table into a JSON file?

- A. PARSE_JSON
- B. TO_JSON
- C. TO_VARIANT
- D. OBJECT_CONSTRUCT

<details><summary>Show Answer</summary>
Correct Answer: D. OBJECT_CONSTRUCT builds a VARIANT (JSON-like object) from table columns, which can then be unloaded via COPY INTO as JSON.
</details>

---

### Question 1160
How can the ACCESS_HISTORY view in the ACCOUNT_USAGE schema be used to review the data governance settings for an account? (Choose two.)

- A. Identify queries run by a particular user.
- B. Identify access to the roles given to a user.
- C. Identify SQL statements that failed to run.
- D. Identify objects that were modified by a query.
- E. Identify object dependencies.

<details><summary>Show Answer</summary>
Correct Answer: A, D. ACCESS_HISTORY logs which user ran which query and which objects/columns were read or modified — it doesn't track role grants, failed statements, or dependency graphs (that's OBJECT_DEPENDENCIES).
</details>

---

### Question 1161
Which command is used to unload data from a Snowflake table into a Snowflake stage?

- A. GET
- B. CREATE STAGE
- C. COPY INTO [location]
- D. PUT

<details><summary>Show Answer</summary>
Correct Answer: C. COPY INTO &lt;location&gt; unloads table data into a stage; COPY INTO &lt;table&gt; is the reverse (load) direction.
</details>

---

### Question 1162
What should an account administrator do to help a user log into Snowflake, if the user cannot authenticate using Multi-Factor Authentication (MFA)?

- A. Set DISABLE_MFA to TRUE for the user.
- B. Set MINS_TO_BYPASS_MFA equal to the desired time.
- C. Set MFA_REQUIRED to FALSE for the account.
- D. Set MFA to FALSE for the user.

<details><summary>Show Answer</summary>
Correct Answer: B. ALTER USER ... SET MINS_TO_BYPASS_MFA temporarily lets the user log in without MFA for a defined window, so they can re-enroll a device.
</details>

---

### Question 1163
Which command can be executed from a reader account?

- A. INSERT
- B. CREATE SHARE
- C. SHOW PROCEDURES
- D. SELECT

<details><summary>Show Answer</summary>
Correct Answer: D. Reader accounts can only query (SELECT) shared data — they can't create objects or write data.
</details>

---

### Question 1164
Which command line parameter value can be pre-specified as an environment variable in SnowSQL?

- A. ACCOUNT
- B. VARIABLE
- C. OPTION
- D. MFA_PASSCODE

<details><summary>Show Answer</summary>
Correct Answer: A. SnowSQL supports connection parameters like account, username, etc. as environment variables (e.g., SNOWSQL_ACCOUNT).
</details>

---

### Question 1165
Which command is used to determine the file name of each row of data from a staged file?

- A. SHOW FILE FORMATS
- B. SELECT METADATA$FILE_ROW_NUMBER
- C. SELECT METADATA$FILE_LAST_MODIFIED
- D. SELECT METADATA$FILENAME

<details><summary>Show Answer</summary>
Correct Answer: D. METADATA$FILENAME is a pseudo-column that returns the name of the staged file each row came from.
</details>

---

### Question 1166
Which Snowflake feature improves the performance of point lookup queries?

- A. Materialized views
- B. Automatic clustering
- C. Query acceleration service
- D. Search optimization service

<details><summary>Show Answer</summary>
Correct Answer: D. The search optimization service is purpose-built to accelerate selective point lookup queries.
</details>

---

### Question 1167
What is the impact of selecting one Snowflake edition over another? (Choose two.)

- A. The edition will impact the unit costs for storage.
- B. The edition will impact which regions can be accessed by the accounts.
- C. The edition will determine the unit costs for the compute credits.
- D. The edition will impact the total allowed storage space.
- E. The edition will determine if certain features (e.g. column level security) are available.

<details><summary>Show Answer</summary>
Correct Answer: C, E. Higher editions cost more per compute credit and unlock additional governance/security features. Storage pricing is generally uniform across editions, region access isn't edition-gated, and there's no fixed storage cap tied to edition.
</details>

---

### Question 1168
In a managed access schema, only the schema owner or a role with what privilege can help centralize privilege management?

- A. USAGE
- B. OPERATE
- C. MANAGE GRANTS
- D. IMPORTED PRIVILEGES

<details><summary>Show Answer</summary>
Correct Answer: C. In a managed access schema, object-grant authority is centralized to the schema owner (or MANAGE GRANTS holders), rather than being delegated to individual object owners.
</details>

---

### Question 1169
A Snowflake user wants to design a series of transformations that need to be executed in a specific order, on a given schedule. What Snowflake objects should be used?

- A. Pipes
- B. Tasks
- C. Streams
- D. Sequences

<details><summary>Show Answer</summary>
Correct Answer: B. Tasks execute SQL (including stored procedure calls) on a schedule and can be chained together into a dependency graph (DAG) for ordered execution.
</details>

---

### Question 1170
Which command should be used to drop files from an internal or external stage?

- A. DELETE
- B. DROP
- C. REMOVE
- D. TRUNCATE

<details><summary>Show Answer</summary>
Correct Answer: C. REMOVE deletes files from a stage.
</details>

---

### Question 1171
Which parameters can be used together to ensure that a virtual warehouse never has a backlog of queued SQL statements? (Choose two.)

- A. STATEMENT_QUEUED_TIMEOUT_IN_SECONDS
- B. STATEMENT_TIMEOUT_IN_SECONDS
- C. MAX_STATEMENT_TIME
- D. MAX_CONCURRENCY_LEVEL

<details><summary>Show Answer</summary>
Correct Answer: A, D. STATEMENT_QUEUED_TIMEOUT_IN_SECONDS cancels statements that sit too long in the queue, and MAX_CONCURRENCY_LEVEL limits how many statements a cluster runs at once, preventing an unbounded backlog.
</details>

---

### Question 1172
What action should be taken if a large number of concurrent queries are queued in a virtual warehouse?

- A. Scale-up by resizing the warehouse.
- B. Scale-out with a multi-cluster warehouse.
- C. Disable auto-suspend on the warehouse.
- D. Enable auto-resume on the warehouse.

<details><summary>Show Answer</summary>
Correct Answer: B. Concurrency/queuing problems are solved by scaling out (adding clusters); scaling up (bigger warehouse) addresses single-query complexity instead.
</details>

---

### Question 1173
Which feature is supported in column-level security in Snowflake?

- A. Object tagging
- B. Data classification
- C. External tokenization
- D. Dynamic Data Masking

<details><summary>Show Answer</summary>
Correct Answer: D. Dynamic Data Masking is the mechanism that implements column-level security in Snowflake.
</details>

---

### Question 1174
A network policy applied at the user level takes precedence over a network policy applied to what Snowflake object?

- A. A role
- B. An account
- C. A database
- D. An organization

<details><summary>Show Answer</summary>
Correct Answer: B. A user-level network policy overrides the account-level network policy for that specific user.
</details>

---

### Question 1175
Which Snowflake storage object can be used to store data beyond a single session and will not incur Fail-safe costs?

- A. Permanent table
- B. External table
- C. Temporary table
- D. Transient table

<details><summary>Show Answer</summary>
Correct Answer: D. Transient tables persist across sessions (unlike temporary tables) but carry 0 days of Fail-safe, so they avoid that storage cost.
</details>

---

### Question 1176
Which data sharing mechanism can be used to share data privately or publicly within the Snowflake Marketplace?

- A. Listing
- B. Direct share
- C. Reader account
- D. Data Exchange

<details><summary>Show Answer</summary>
Correct Answer: A. Listings are the mechanism for publishing data either privately to specific accounts or publicly on the Snowflake Marketplace.
</details>

---

### Question 1177
What metrics will the SHOW TABLES command in Snowsight display?

- A. Time Travel bytes
- B. Active bytes
- C. Fail-safe bytes
- D. Retained for clone bytes

<details><summary>Show Answer</summary>
Correct Answer: B. SHOW TABLES surfaces the table's active storage ("bytes"); the more granular Time Travel/Fail-safe/clone-retained breakdown lives in the ACCOUNT_USAGE storage views.
</details>

---

### Question 1178
An external stage, @my_stage, contains many directories, including one, app_files, that contains CSV files. How can all the CSV files from this directory be moved into table my_table without scanning files that are not needed?

- A. COPY INTO my_table FROM @my_stage/app_files/
- B. COPY INTO my_table FROM @my_stage PATTERN='.*app_files.*'
- C. COPY INTO my_table FROM @my_stage FILES=('app_files')
- D. COPY INTO my_table FROM @my_stage PATTERN='.*.csv'

<details><summary>Show Answer</summary>
Correct Answer: A. Pointing directly at the subdirectory path scans only files under that path, whereas a PATTERN regex has to evaluate every file in the stage first.
</details>

---

### Question 1179
Using which object level parameters will help limit query processing and concurrency slowdowns? (Choose two.)

- A. STATEMENT_QUEUED_TIMEOUT_IN_SECONDS
- B. STATEMENT_TIMEOUT_IN_SECONDS
- C. MAX_CONCURRENCY_LEVEL
- D. MAX_STATEMENT_TIME
- E. QUERY_TIMEOUT_IN_SECONDS

<details><summary>Show Answer</summary>
Correct Answer: A, B. Capping how long a statement can sit queued (STATEMENT_QUEUED_TIMEOUT_IN_SECONDS) and how long it can run (STATEMENT_TIMEOUT_IN_SECONDS) prevents runaway or backlogged statements from degrading the warehouse.
</details>

---

### Question 1180
The ORDERS table contains 100 rows. Which query will return 10 rows that are randomly sampled from the table every time the query is run?

- A. select * from ORDERS fetch 10;
- B. select * from ORDERS limit 10;
- C. select * from ORDERS sample (10);
- D. select * from ORDERS sample (10 rows);

<details><summary>Show Answer</summary>
Correct Answer: D. SAMPLE (n ROWS) returns a fixed count of rows, selected randomly on each execution since no REPEATABLE seed is given. SAMPLE(10) without ROWS is interpreted as a 10% probability sample, not a fixed 10-row count, and LIMIT/FETCH return the same rows deterministically (in whatever order the query returns them), not a random sample.
</details>

---

### Question 1181
Which function will convert semi-structured data to a relational data format?

- A. PARSE_JSON
- B. FLATTEN
- C. OBJECT_CONSTRUCT
- D. OBJECT_AGG

<details><summary>Show Answer</summary>
Correct Answer: B. FLATTEN explodes VARIANT arrays/objects into multiple relational rows.
</details>

---

### Question 1182
What triggers the automated maintenance of a table's clustering key after it has been defined?

- A. A scheduled task established by the ORGADMIN.
- B. A time-based schedule set by the user.
- C. A Snowflake determination based on the table size.
- D. A Snowflake determination that the table will benefit from maintenance.

<details><summary>Show Answer</summary>
Correct Answer: D. Automatic clustering runs as a background service that Snowflake triggers when it determines a table has drifted enough from its clustering key to benefit from re-clustering — it's not on a fixed schedule or purely size-based.
</details>

---

### Question 1183
Which Snowflake object will consume credits during automatic background maintenance?

- A. View
- B. Table
- C. External table
- D. Materialized view

<details><summary>Show Answer</summary>
Correct Answer: D. Materialized views are automatically refreshed by a background service, which consumes serverless credits.
</details>

---

### Question 1184
Snowflake can create a resource monitor at which levels? (Choose two.)

- A. User level
- B. Pipe level
- C. Account level
- D. Cloud services level
- E. Virtual warehouse level

<details><summary>Show Answer</summary>
Correct Answer: C, E. Resource monitors can be set at the account level (covering all warehouses) or assigned to individual virtual warehouses.
</details>

---

### Question 1185
Which Snowflake objects can be secured to protect data privacy using masking policies? (Choose two.)

- A. Schemas
- B. Stages
- C. Views
- D. Tables
- E. Tags

<details><summary>Show Answer</summary>
Correct Answer: C, D. Masking policies attach to columns within tables and views.
</details>

---

### Question 1186
How does Snowflake optimize queries on tables by leveraging the sorting and storage of data within micro-partitions?

- A. The data is sorted by column to eliminate unnecessary micro-partitions, then the rows within the remaining micro-partitions are filtered.
- B. The data is pruned by micro-partitions based on column values, then rows within the remaining micro-partitions are filtered.
- C. Any micro-partitions that are not needed for the query are pruned, then the data within the remaining micro-partitions is pruned by column.
- D. The data within micro-partitions is sorted by rows, then the columns are filtered based on the query conditions.

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake first prunes whole micro-partitions using stored min/max column metadata, then applies row-level filtering within whatever partitions remain.
</details>

---

### Question 1187
Which resource monitor setting will cancel all active queries in a virtual warehouse when the threshold is met?

- A. NOTIFY
- B. NOTIFY_USERS
- C. SUSPEND
- D. SUSPEND_IMMEDIATE

<details><summary>Show Answer</summary>
Correct Answer: D. SUSPEND_IMMEDIATE cancels all currently running queries right away; SUSPEND lets in-flight queries finish but blocks new ones.
</details>

---

### Question 1188
What role should be used when creating a new user?

- A. ORGADMIN
- B. SECURITYADMIN
- C. USERADMIN
- D. SYSADMIN

<details><summary>Show Answer</summary>
Correct Answer: C. USERADMIN (or a role above it in the hierarchy) is dedicated to creating and managing users and roles.
</details>

---

### Question 1189
Which ACCOUNT_USAGE view will identify long-running queries?

- A. DATA_TRANSFER_HISTORY
- B. TASK_HISTORY
- C. QUERY_HISTORY
- D. LOAD_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: C. QUERY_HISTORY includes execution time for every query, making it the source for identifying long-running queries.
</details>

---

### Question 1190
When sharing data among multiple Snowflake accounts, what charges are incurred by a data consumer when viewing shared data using their own compute?

- A. Cloud Services charges
- B. Compute charges
- C. Data storage charges
- D. Data egress charges

<details><summary>Show Answer</summary>
Correct Answer: B. The consumer pays for the compute (virtual warehouse) they use to query shared data; storage remains the provider's cost since no data is copied.
</details>

---

### Question 1191
What is the MINIMUM Snowflake edition required to use the query acceleration service?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: B. Query acceleration service requires Enterprise Edition or higher — confirmed current in 2026 documentation. Note: as of 2026, QAS is also enabled by default on new multi-cluster and Gen2 warehouses on eligible editions.
</details>

---

### Question 1192
Which objects can be cloned in Snowflake? (Choose two.)

- A. Virtual warehouses
- B. Internal named stages
- C. Databases
- D. Dynamic tables
- E. Schemas

<details><summary>Show Answer</summary>
Correct Answer: C, E. Databases and schemas are zero-copy cloneable containers. Virtual warehouses aren't data objects to clone, and dynamic tables/stages have their own separate handling.
</details>

---

### Question 1193
What happens to foreign key constraints when a table is cloned to another table?

- A. All referenced tables will be cloned.
- B. The cloned table will retain the key referencing the source table.
- C. The cloned table will lose all references to the primary key.
- D. The cloned table will lose all references to the foreign and primary keys.

<details><summary>Show Answer</summary>
Correct Answer: D. Cloning does not preserve foreign key or primary key constraint relationships — those need to be re-established on the clone if needed.
<br>
<b>Correction: B</b>
</details>

---

### Question 1194
What step must be taken to ensure that a user can only access Snowsight from a specific location, or when working from home?

- A. Use a company Virtual Private Network (VPN) connection.
- B. Use Multi-Factor Authentication (MFA).
- C. Use Single Sign-on (SSO).
- D. Add the user's IP address to the network policy allowed list.

<details><summary>Show Answer</summary>
Correct Answer: D. A network policy with an IP allow list is Snowflake's native mechanism for restricting where a user can connect from.
</details>

---

### Question 1195
What actions will trigger a data pipe to load? (Choose two.)

- A. Use of an INSERT statement
- B. Use of a COPY INTO [table] statement
- C. Use of the insertFiles REST endpoint
- D. Use of the insertReport REST endpoint
- E. Set the pipe parameter to auto-ingest

<details><summary>Show Answer</summary>
Correct Answer: C, E. A pipe loads via the insertFiles REST API call (classic Snowpipe) or automatically when AUTO_INGEST is enabled and a cloud storage event notification fires. Plain INSERT or COPY INTO statements bypass the pipe entirely.
</details>

---

### Question 1196
What does a Query profile metric that shows excessive spillage indicate?

- A. Poor query optimization
- B. A need for temporary tables
- C. Improper virtual warehouse sizing
- D. Improper Common Table Expressions (CTEs)

<details><summary>Show Answer</summary>
Correct Answer: C. Spilling to local or remote disk in the Query Profile means the warehouse doesn't have enough memory for the operation — i.e., it's undersized for that workload.
</details>

---

### Question 1197
A query is using more credits than expected. The Query Profile shows that a majority of the query execution is spent on remote disk I/O. How can this be prevented in the future?

- A. Convert the virtual warehouse to Maximized mode.
- B. Increase the size of the virtual warehouse.
- C. Increase the auto suspend time in the virtual warehouse.
- D. Increase the number of clusters in the virtual warehouse.

<details><summary>Show Answer</summary>
Correct Answer: B. A larger warehouse has more local SSD cache and memory, reducing reliance on slower remote disk I/O.
</details>

---

### Question 1198
In a SPLIT_PART function, what will the returned value be if the requested part is out of bounds?

- A. NULL
- B. An empty string
- C. The full string
- D. An error

<details><summary>Show Answer</summary>
Correct Answer: B. SPLIT_PART returns an empty string (not NULL or an error) when the requested part index doesn't exist.
</details>

---

### Question 1199
From which locations can data files be downloaded using the GET command? (Choose two.)

- A. External stage
- B. Table stage
- C. User stage
- D. Directory table
- E. Permanent table

<details><summary>Show Answer</summary>
Correct Answer: B, C. GET downloads files from Snowflake-managed internal stages — table stages and user stages. External stages are accessed via the cloud provider's own tools, and directory tables/permanent tables aren't stage locations.
</details>

---

### Question 1200
What Snowflake features are recommended to restrict unauthorized users from accessing Personal Identifiable Information (PII)?

- A. Dynamic Data Masking
- B. Transient tables
- C. Row access policies
- D. Multi-Factor Authentication (MFA)
- E. Data encryption

<details><summary>Show Answer</summary>
Correct Answer: A, C. Dynamic Data Masking controls column-level visibility of PII, and row access policies control which rows a role can see — together they're Snowflake's primary native tools for restricting PII access.
</details>

---



====================================================================================================
# SnowPro_1201-1300.md
====================================================================================================

# SnowPro Core Practice Questions — Batch 14 (Questions 1201–1300)

*Cleaned, reformatted, and cross-checked against current Snowflake documentation (as of July 2026). Click "Show Answer" to reveal each answer.*

---

### Question 1201
Which Snowflake keywords help retrieve data without the need to completely scan a table? (Choose two.)

- A. TOP [n]
- B. LIMIT
- C. FETCH
- D. SAMPLE
- E. TABLESAMPLE

<details><summary>Show Answer</summary>
Correct Answer: D, E. SAMPLE and TABLESAMPLE are synonymous commands that return a subset of rows without scanning the entire table; TOP/LIMIT/FETCH still scan (and then truncate) the result set.
</details>

---

### Question 1202
A security review identified several roles that are no longer being used. Which of the roles can be dropped?

- A. ACCOUNTADMIN
- B. USERADMIN
- C. FINANCEADMIN
- D. PUBLIC

<details><summary>Show Answer</summary>
Correct Answer: C. FINANCEADMIN is a custom role and can be dropped. ACCOUNTADMIN, USERADMIN, and PUBLIC are system-defined roles that cannot be dropped.
</details>

---

### Question 1203
A complex query has been running in Snowsight for more than one hour. At the same time, several other queries from other worksheets ran successfully. What is the FASTEST way to cancel the long-running query?

- A. Immediately suspend the virtual warehouse that the query is running on.
- B. Return to the worksheet and abort the query.
- C. Set auto_suspend virtual property to 0.
- D. Find the query in the query activity view and cancel the query.

<details><summary>Show Answer</summary>
Correct Answer: B. Aborting the query directly from its worksheet takes effect immediately — faster than suspending the entire warehouse or navigating to a separate activity view.
</details>

---

### Question 1204
How can a Snowflake user automate virtual warehouse operations for optimal credit consumption? (Choose two.)

- A. Auto-resume when a query is in a queue.
- B. Auto-resume after a set time period.
- C. Auto-resume when the query is being written.
- D. Auto-suspend after a set time period.
- E. Auto-suspend after a specified period of inactivity.

<details><summary>Show Answer</summary>
Correct Answer: A, E. Auto-resume on incoming queries plus auto-suspend after inactivity together minimize idle credit spend.
</details>

---

### Question 1205
Which data protection feature should only be used when all other data recovery options have been attempted?

- A. Time Travel
- B. Cloning
- C. Replication
- D. Fail-safe

<details><summary>Show Answer</summary>
Correct Answer: D. Fail-safe is a non-configurable, 7-day, Snowflake-Support-assisted recovery mechanism used only after Time Travel options are exhausted.
</details>

---

### Question 1206
A single cluster virtual warehouse has no free resources. What will happen to new queries that are run against this warehouse?

- A. The queries will be assigned to another virtual warehouse.
- B. The queries will be skipped.
- C. The queries will be placed in a queue.
- D. The warehouse will automatically resize and execute the queries.

<details><summary>Show Answer</summary>
Correct Answer: C. Without free capacity, incoming queries queue until resources become available.
</details>

---

### Question 1207
How does the search optimization service improve query performance?

- A. By clustering the tables.
- B. By creating a persistent data structure.
- C. By using caching.
- D. By optimizing the use of micro-partitions.

<details><summary>Show Answer</summary>
Correct Answer: B. Search Optimization Service builds and maintains a persistent search-access data structure alongside the table to speed up selective point-lookup queries.
</details>

---

### Question 1208
What parameter will allow files to be loaded even if the file metadata has expired?

- A. MATCH_BY_COLUMN_NAME = CASE_INSENSITIVE
- B. ENFORCE_LENGTH = TRUE
- C. PURGE = TRUE
- D. FORCE = TRUE

<details><summary>Show Answer</summary>
Correct Answer: D. FORCE = TRUE reloads files regardless of previous load history or expired metadata.
</details>

---

### Question 1209
How can a Data Exchange Administrator provide a user with account access to a Data Exchange?

- A. Grant the user the USERADMIN role.
- B. Add the user to the Data Exchange.
- C. Enable the IMPORT SHARE privilege and grant this privilege to the user.
- D. Create a new database for the Data Exchange and provide access to the user.

<details><summary>Show Answer</summary>
Correct Answer: C. Granting the IMPORT SHARE privilege lets a user consume data made available through a Data Exchange.
</details>

---

### Question 1210
Which features can be used with the Snowflake Standard edition? (Choose two.)

- A. Materialized Views
- B. External functions
- C. Multi-cluster virtual warehouses
- D. Fail-safe
- E. Row level security

<details><summary>Show Answer</summary>
Correct Answer: B, D. Per Snowflake's current edition feature matrix, external functions and Fail-safe are included in Standard Edition. Materialized views, multi-cluster warehouses, and row-level security (row access policies) all require Enterprise Edition or higher.
</details>

---

### Question 1211
Which function will generate a URL that can be accessed by a non-Snowflake user?

- A. GET_STAGE_URL
- B. GET_PRESIGNED_URL
- C. BUILD_SCOPED_FILE_URL
- D. GET_ABSOLUTE_PATH

<details><summary>Show Answer</summary>
Correct Answer: B. GET_PRESIGNED_URL generates a temporary, self-authenticating URL usable outside of a Snowflake session.
</details>

---

### Question 1212
What are valid values for the FIELD_OPTIONALLY_ENCLOSED_BY option in the COPY INTO [location] command used during data unloading? (Choose two.)

- A. Single quote character ('')
- B. NULL
- C. 'NULL'
- D. NONE
- E. 'NONE'

<details><summary>Show Answer</summary>
Correct Answer: A, D.

⚠ **Updated:** The source material labeled this option "NULL_IF," but the listed answer choices (single quote character and NONE) actually describe the **FIELD_OPTIONALLY_ENCLOSED_BY** option, which per current documentation accepts only `NONE`, a single quote character (`'`), or a double quote character (`"`). The NULL_IF option works differently — it takes a parenthesized list of quoted string literals (e.g., `NULL_IF = ('NULL', '')`) and does not accept a bare, unquoted `NONE` value. The question has been retitled to match the answer choices provided.
</details>

---

### Question 1213
What identifiers are supported when creating a Snowflake account hostname? (Choose two.)

- A. Cloud region
- B. Snowflake domain
- C. Account name
- D. Account locator

<details><summary>Show Answer</summary>
Correct Answer: C, D. A Snowflake account hostname is built from either the account name (paired with the organization name) or the legacy account locator, combined with region/cloud/domain information.
</details>

---

### Question 1214
Which virtual warehouse auto-suspend configurations will result in a warehouse that runs continually, 24 hours a day, 7 days a week? (Choose two.)

- A. 0
- B. 3600
- C. FALSE
- D. 172800
- E. NULL

<details><summary>Show Answer</summary>
Correct Answer: A, E. Setting auto_suspend to 0 or NULL disables auto-suspend entirely, keeping the warehouse running continuously.
</details>

---

### Question 1215
What kind of value does a User-Defined Function (UDF) return? (Choose two.)

- A. List
- B. Array
- C. Object
- D. Scalar
- E. Tabular

<details><summary>Show Answer</summary>
Correct Answer: D, E. A UDF returns either a single scalar value or a tabular result set (in the case of a UDTF).
</details>

---

### Question 1216
Which command can be performed on a Snowflake secure view?

- A. SELECT
- B. INSERT
- C. UPDATE
- D. DELETE

<details><summary>Show Answer</summary>
Correct Answer: A. Views (secure or otherwise) are read-only; SELECT is the only supported operation, since DML must target the underlying base table(s).
</details>

---

### Question 1217
Which database objects can be shared with Secure Data Sharing? (Choose two.)

- A. Views
- B. Materialized views
- C. External Stages
- D. External tables
- E. Secure views

<details><summary>Show Answer</summary>
Correct Answer: D, E.

⚠ **Updated:** The original answer key selected B and E (Materialized views, Secure views). Current Snowflake documentation lists shareable objects as: tables, dynamic tables, **external tables**, Iceberg/Delta Lake tables, secure views, **secure** materialized views, secure UDFs, and models. External Stages are never shareable. Because plain "Materialized Views" (option B) must specifically be defined as *secure* materialized views to be shared, **External tables (D)** is the more directly and unambiguously correct pairing with **Secure views (E)**.
</details>

---

### Question 1218
When a transient table in Snowflake is dropped, what happens to the table?

- A. The table is no longer available.
- B. The table can be undropped using Fail-safe.
- C. The table can be recovered for 1 day only and after that it is no longer available.
- D. The table can be recovered only with the assistance of Snowflake Support.

<details><summary>Show Answer</summary>
Correct Answer: C. Transient tables have a maximum 1-day Time Travel window and no Fail-safe, so recovery is only possible within that window.
</details>

---

### Question 1219
A data provider needs to securely collaborate with data consumers who do not reside in the same region. What Snowflake sharing mechanism should be used?

- A. Direct share
- B. Data Exchange
- C. Data replication
- D. Listing

<details><summary>Show Answer</summary>
Correct Answer: C. Standard shares only work within the same region and cloud platform; cross-region/cross-cloud sharing requires replicating the database to an account in the consumer's region first.
</details>

---

### Question 1220
A user needs to know the maximum of a date field in a table, and runs the following: `SELECT MAX(date_field) FROM ORDERS;`. Which part of Snowflake architecture will this query use?

- A. Database Storage
- B. Query processing
- C. Cloud Services
- D. Compute

<details><summary>Show Answer</summary>
Correct Answer: C. Simple aggregates like MAX() over clustered/pruned metadata can sometimes be answered directly from metadata maintained by the Cloud Services layer, without spinning up compute.
</details>

---

### Question 1221
A Snowflake user accidentally deleted a table. The table no longer exists but the session is within the data retention period. How can the table be restored using the LEAST amount of operational overhead?

- A. Clone the table schema as it existed before the table was dropped.
- B. Clone the database as it existed before the table was dropped.
- C. Recreate the table and reload the data.
- D. Run the UNDROP command against the table.

<details><summary>Show Answer</summary>
Correct Answer: D. UNDROP restores the object instantly from within the Time Travel window with a single command — the least operational overhead.
</details>

---

### Question 1222
When cloning a schema, which Snowflake object will not be included in the clone?

- A. External stage
- B. A named internal stage
- C. A task
- D. A User-Defined Function (UDF)

<details><summary>Show Answer</summary>
Correct Answer: B. Named internal stages are not copied when cloning a schema/database (their file contents aren't duplicated); external stages, tasks (created suspended), and UDFs are included.
</details>

---

### Question 1223
Which command will change the name of database role r1 to r4?

- A. ALTER ROLE d1_r1 RENAME TO d1_r4;
- B. ALTER ROLE d1.r1 RENAME TO r4;
- C. ALTER DATABASE ROLE d1.r1 RENAME TO r4;
- D. ALTER DATABASE ROLE d1_r1 RENAME TO r4;

<details><summary>Show Answer</summary>
Correct Answer: C. Database roles are renamed with `ALTER DATABASE ROLE <db>.<role> RENAME TO <new_name>`.
</details>

---

### Question 1224
What does the Remote Disk I/O statistic in the Query Profile indicate?

- A. Time spent reading from the result cache.
- B. Time spent reading from the virtual warehouse cache.
- C. Time when the query processing was blocked by remote disk access.
- D. The level of network activity between the Cloud Services layer and the virtual warehouse.

<details><summary>Show Answer</summary>
Correct Answer: C. This statistic reflects time the query was blocked waiting on remote (cloud storage) disk I/O.
</details>

---

### Question 1225
Use of which virtual warehouse or warehouse configuration will improve the performance of workloads that have large memory requirements, such as Machine Learning (ML) training using a stored procedure?

- A. Snowpark-optimized warehouse
- B. Standard warehouse
- C. Multi-cluster warehouse
- D. Compute

<details><summary>Show Answer</summary>
Correct Answer: A. Snowpark-optimized warehouses provide significantly more memory per node, suited to memory-intensive ML training and similar workloads.
</details>

---

### Question 1226
Which role has the privileges to describe a share?

- A. ORGADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. ACCOUNTADMIN

<details><summary>Show Answer</summary>
Correct Answer: D. ACCOUNTADMIN holds default privileges to manage and describe shares.
</details>

---

### Question 1227
The following command is executed: `CREATE TABLE new_table CLONE existing_table COPY GRANTS;`. What will happen to the privileges of the cloned object?

- A. The clone will only inherit SELECT privileges from the source object.
- B. The clone will inherit all privileges, including OWNERSHIP, from the source object.
- C. The clone will inherit all privileges except OWNERSHIP from the source object.
- D. The clone will inherit no privileges.

<details><summary>Show Answer</summary>
Correct Answer: C. COPY GRANTS carries over the source object's existing privilege grants, but the clone's OWNERSHIP is always assigned to the role that ran the CLONE statement.
</details>

---

### Question 1228
Where does Snowflake store the data output from a query that was executed in the past 24 hours?

- A. In a remote disk
- B. In the virtual warehouse cache
- C. In the result cache layer
- D. In the local disk cache

<details><summary>Show Answer</summary>
Correct Answer: C. Query results are persisted in the result cache for 24 hours (refreshed with each reuse), enabling instant retrieval of identical queries.
</details>

---

### Question 1229
What is the default authenticator while using the JDBC driver connection in Snowflake?

- A. externalbrowser
- B. snowflake
- C. oauth
- D. okta

<details><summary>Show Answer</summary>
Correct Answer: B. The JDBC driver defaults to standard username/password ("snowflake") authentication unless another authenticator is explicitly specified.
</details>

---

### Question 1230
When will Snowflake charge credits for the use of the Cloud Services layer?

- A. Credits will be charged whenever the Cloud Services layer is used.
- B. Credits will be charged only when running a Snowflake-provisioned compute warehouse COMPUTE_WH.
- C. Credits will be charged when the daily consumption of cloud services resources exceeds 10% of the daily warehouse usage.
- D. Credits will be charged only when a virtual warehouse consumes serverless compute services.

<details><summary>Show Answer</summary>
Correct Answer: C. Cloud Services usage is free up to 10% of that day's total compute (warehouse) credit consumption; only the excess is billed.
</details>

---

### Question 1231
What is the primary purpose of using a masking policy in Snowflake?

- A. To protect sensitive data from unauthorized access when queries are executed.
- B. To automatically encrypt sensitive data when data is stored in Snowflake.
- C. To protect multiple columns that have different data types in a given table.
- D. To protect both column-level and row-level data.

<details><summary>Show Answer</summary>
Correct Answer: A. Masking policies dynamically obscure column values from unauthorized roles at query runtime.
</details>

---

### Question 1232
How can the performance of point lookup queries run on tables be optimized?

- A. Cluster the tables
- B. Create materialized views on the tables
- C. Use the metadata cache
- D. Enable the Search Optimization Service

<details><summary>Show Answer</summary>
Correct Answer: D. Search Optimization Service is purpose-built to accelerate highly selective point-lookup queries.
</details>

---

### Question 1233
What are the recommended alternative data types in Snowflake for unsupported large object data types such as BLOB and CLOB? (Choose two.)

- A. VARIANT
- B. ARRAY
- C. BINARY
- D. OBJECT
- E. VARCHAR

<details><summary>Show Answer</summary>
Correct Answer: C, E. BINARY is the recommended substitute for BLOB, and VARCHAR is the recommended substitute for CLOB.
</details>

---

### Question 1234
A network policy set at which level will override all other network policies?

- A. Account
- B. User
- C. Security integration
- D. Database

<details><summary>Show Answer</summary>
Correct Answer: B. A user-level network policy takes precedence over an account-level (or any other) network policy for that specific user.
</details>

---

### Question 1235
A company wants to share sales data with multiple marketing agency partners. Which Snowflake data share mechanism is recommended for this use case?

- A. A shared Amazon S3 bucket
- B. Direct share
- C. A reader account
- D. Data Exchange

<details><summary>Show Answer</summary>
Correct Answer: D. Data Exchange lets a provider publish data once as listings that many partners can discover and subscribe to, rather than managing individual direct shares with each partner.
</details>

---

### Question 1236
Which role can create and manage Snowflake accounts?

- A. SYSADMIN
- B. ACCOUNTADMIN
- C. ORGADMIN
- D. SECURITYADMIN

<details><summary>Show Answer</summary>
Correct Answer: C. ORGADMIN manages account creation and other organization-wide account operations.
</details>

---

### Question 1237
Which security feature is available in all Snowflake editions?

- A. Data masking policies
- B. Object level access control
- C. Object tagging
- D. Customer-managed encryption keys

<details><summary>Show Answer</summary>
Correct Answer: B. Object-level access control (role-based access control) is included in every edition, including Standard.
</details>

---

### Question 1238
A table named car_sales contains a single VARIANT column named SRC. Below is the output of the query `SELECT * FROM car_sales;`
`{"address" : "San Francisco, CA", "phone": "16504378989", "date": "2017-04-28", "dealership": "Valley View Auto Sales"}`
Which queries will return the element "phone" from the data? (Choose two.)

- A. SELECT SRC:phone FROM car_sales;
- B. SELECT SRC['phone'] FROM car_sales;
- C. SELECT SRC.phone FROM car_sales;
- D. SELECT SRC.customer.phone FROM car_sales;
- E. SELECT SRC[0].phone FROM car_sales;

<details><summary>Show Answer</summary>
Correct Answer: A, B. Both colon notation (`SRC:phone`) and bracket notation (`SRC['phone']`) retrieve a top-level key from a VARIANT/OBJECT column.
</details>

---

### Question 1239
Which strings will be converted to TRUE using the TO_BOOLEAN or CAST() functions when unloading data? (Choose two.)

- A. 'T'
- B. '1'
- C. 'Y'
- D. 'true'
- E. 'yes'

<details><summary>Show Answer</summary>
Correct Answer: D, E. TO_BOOLEAN/CAST recognize case-insensitive strings such as 'true' and 'yes' as TRUE.
</details>

---

### Question 1240
Which authentication method requires access to a secure file that is only stored on the user's local device?

- A. Password
- B. Key-pair authentication
- C. Multi-Factor Authentication (MFA)
- D. Federated authentication

<details><summary>Show Answer</summary>
Correct Answer: B. Key-pair authentication depends on a private key file that must be securely stored on the user's local device.
</details>

---

### Question 1241
Which drivers or connectors are supported by Snowflake? (Choose two.)

- A. Perl Connector
- B. MongoDB Rust Driver
- C. Go Snowflake Driver
- D. Cobol Driver
- E. Snowflake Connector for Python

<details><summary>Show Answer</summary>
Correct Answer: C, E. The Go Snowflake Driver and the Snowflake Connector for Python are official, Snowflake-supported drivers.
</details>

---

### Question 1242
If a source table is updated while cloning is in progress, what data will be included in the cloned table?

- A. All data from the timestamp when the user runs the query.
- B. All data from the timestamp when the user session was created.
- C. All data from the timestamp when the clone statement was initiated.
- D. All data from the timestamp when the clone statement was completed.

<details><summary>Show Answer</summary>
Correct Answer: C. Cloning captures a consistent snapshot as of the moment the CREATE ... CLONE statement began.
</details>

---

### Question 1243
The CUSTOMER table in the T1 database is accidentally dropped. Which privileges are required to restore this table? (Choose two.)

- A. SELECT privilege on the CUSTOMER table
- B. OWNERSHIP privilege on the CUSTOMER table
- C. All privileges on the CUSTOMER table
- D. All privileges on the T1 database
- E. CREATE TABLE privilege on the schema

<details><summary>Show Answer</summary>
Correct Answer: B, E. Restoring a dropped table with UNDROP requires OWNERSHIP on the table and CREATE TABLE privilege on the containing schema.
</details>

---

### Question 1244
Which ACCOUNT_USAGE view can be used to identify the masking policy assigned to an object?

- A. ACCESS_HISTORY
- B. OBJECT_DEPENDENCIES
- C. POLICY_REFERENCES
- D. TAG_REFERENCES

<details><summary>Show Answer</summary>
Correct Answer: C. POLICY_REFERENCES lists which masking (or row access) policies are assigned to which objects/columns.
</details>

---

### Question 1245
A stream object will advance its offset when it is used in which statement?

- A. SELECT
- B. INSERT
- C. CREATE
- D. COPY INTO [location]

<details><summary>Show Answer</summary>
Correct Answer: B. A stream's offset advances only when it is consumed within a DML statement (such as an INSERT ... SELECT from the stream) inside an explicit or implicit transaction; a plain SELECT does not advance the offset.
</details>

---

### Question 1246
Where is metadata management handled in Snowflake?

- A. Cloud Services
- B. Compute
- C. Database Storage
- D. Query Processing

<details><summary>Show Answer</summary>
Correct Answer: A. The Cloud Services layer handles metadata management, along with security, transactions, and query optimization.
</details>

---

### Question 1247
What does an integration between Snowflake and Microsoft Private Link or AWS PrivateLink support?

- A. The isolation of data within a Snowflake account.
- B. Secure Data Sharing among Snowflake accounts.
- C. A Virtual Private Network (VPN) between a user and Snowflake.
- D. A secure, direct connection to Snowflake that does not use the public internet.

<details><summary>Show Answer</summary>
Correct Answer: D. PrivateLink/Private Link provides a private network path to Snowflake, bypassing the public internet.
</details>

---

### Question 1248
Which type of URL gives permanent access to files in Cloud Storage?

- A. Stage URL
- B. Account URL
- C. Scoped URL
- D. File URL

<details><summary>Show Answer</summary>
Correct Answer: D. A File URL is a stable, permanent reference to a specific staged file (access still requires appropriate role privileges).
</details>

---

### Question 1249
Which Snowflake data governance feature supports resource usage monitoring?

- A. Data Classification
- B. Column lineage
- C. Access history
- D. Object tagging

<details><summary>Show Answer</summary>
Correct Answer: C. Access History tracks query and object access patterns, supporting usage-monitoring and governance use cases.
</details>

---

### Question 1250
Which steps will help optimize query performance? (Choose two.)

- A. Using the query acceleration service
- B. Clustering a table
- C. Indexing a column
- D. Increasing the size of the micro-partitions
- E. Decreasing the size of the virtual warehouse

<details><summary>Show Answer</summary>
Correct Answer: A, B. Query Acceleration Service offloads eligible scan-heavy work; clustering improves micro-partition pruning. (Snowflake has no traditional column indexes.)
</details>

---

### Question 1251
Which functions can be used to identify the data type stored in a VARIANT column? (Choose two.)

- A. IS_GEOGRAPHY
- B. IS_OBJECT
- C. IS_ARRAY
- D. IS_XML
- E. IS_JSON

<details><summary>Show Answer</summary>
Correct Answer: B, E. IS_OBJECT and IS_JSON are among the family of IS_* functions used to test the type of value held in a VARIANT.
</details>

---

### Question 1252
What is the MINIMUM Snowflake edition that supports data sharing?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: A. Secure Data Sharing is available starting at Standard Edition.
</details>

---

### Question 1253
Who can access the data published in a Data Exchange?

- A. Only the data provider who published the data
- B. Any Snowflake user, regardless of their role or permissions
- C. Any user who has a unique Data Exchange URL
- D. Only the users that the data provider has invited to the Data Exchange

<details><summary>Show Answer</summary>
Correct Answer: D. Access to a (private) Data Exchange is restricted to accounts/users the provider has explicitly invited.
</details>

---

### Question 1254
How can data be shared between users who have different Snowflake accounts?

- A. Create a share with the same name as the original database.
- B. Create a Share and ensure the proper role is assigned.
- C. Ensure both users' accounts are using the same cloud provider and region.
- D. Use the PUT command to create a shared account.

<details><summary>Show Answer</summary>
Correct Answer: B. Cross-account sharing is done by creating a share and granting/assigning the correct privileges/roles to manage and consume it.
</details>

---

### Question 1255
Which view will show the MOST recent information about table-level storage utilization?

- A. The TABLES view in a Snowflake data Share
- B. The STORAGE_USAGE view in the ACCOUNT_USAGE schema
- C. The TABLE_STORAGE_METRICS view in the INFORMATION_SCHEMA
- D. The TABLES view in the INFORMATION_SCHEMA

<details><summary>Show Answer</summary>
Correct Answer: C. INFORMATION_SCHEMA.TABLE_STORAGE_METRICS reflects real-time storage statistics, whereas ACCOUNT_USAGE views are refreshed periodically with latency.
</details>

---

### Question 1256
A user executed a SELECT query in Snowsight which returned a 1 GB result set. The user then downloads the files. What will occur?

- A. The result set will be successfully downloaded from Snowsight.
- B. The result set will be paginated and the data will be downloaded as individual files.
- C. The download will fail because the result set needs to be broken up into files no greater than 50 MB before downloading.
- D. The download will result in an error because the filters of the SELECT query need to be changed so that Snowsight returns a smaller result.

<details><summary>Show Answer</summary>
Correct Answer: A. Snowsight supports downloading result sets of this size without requiring the user to manually split or filter the data first.
</details>

---

### Question 1257
Which command can be used to unload data into an external named stage in Snowflake?

- A. PUT
- B. CREATE STAGE
- C. COPY INTO [table]
- D. COPY INTO [location]

<details><summary>Show Answer</summary>
Correct Answer: D. COPY INTO <location> unloads table/query results into files at a stage.
</details>

---

### Question 1258
Which file format option should be used when unloading data into a stage to create a CSV or a JSON file?

- A. PARSE_HEADER
- B. TRIM_SPACE
- C. FILE_EXTENSION
- D. SKIP_HEADER

<details><summary>Show Answer</summary>
Correct Answer: C. FILE_EXTENSION explicitly sets the extension (e.g., .csv, .json) applied to unloaded files.
</details>

---

### Question 1259
When creating a virtual warehouse, what setting should be used to avoid both over-provisioning resources and auto-scaling when there is increased load?

- A. WAREHOUSE_SIZE = LARGE
- B. WAREHOUSE_TYPE = SNOWPARK-OPTIMIZED
- C. Set MIN_CLUSTER_COUNT and MAX_CLUSTER_COUNT to the same value (Maximized mode)
- D. WAIT_FOR_COMPLETION = TRUE

<details><summary>Show Answer</summary>
Correct Answer: C. Fixing MIN_CLUSTER_COUNT = MAX_CLUSTER_COUNT locks the warehouse at a set cluster count ("Maximized" mode) so it neither autoscales nor is left over-provisioned beyond that fixed size.
</details>

---

### Question 1260
What is the MINIMUM Snowflake edition required to add masking policies to selectively mask plain-text data in a table or in view columns at query time?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: B. Column-level Security (masking policies) requires Enterprise Edition or higher.
</details>

---

### Question 1261
Which command can be used to determine if data from a file has been previously loaded?

- A. COPY_HISTORY view or VALIDATE function
- B. DESCRIBE STAGE
- C. SHOW FILES
- D. LIST_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: A. COPY_HISTORY (Account Usage/table function) or the VALIDATE function can confirm whether/when a specific file was already loaded.
</details>

---

### Question 1262
What does Snowflake recommend when configuring the auto-suspend parameter for a virtual warehouse?

- A. Set auto-suspend to the maximum possible duration for optimal resource utilization.
- B. Enable auto-suspend to a high value to maximize warehouse availability.
- C. Enable a low value to minimize credit consumption during inactivity.
- D. Disable auto-suspend to ensure continuous availability of the warehouse.

<details><summary>Show Answer</summary>
Correct Answer: C. A low auto-suspend value quickly releases idle compute, minimizing wasted credits.
</details>

---

### Question 1263
Which URL identifies the database, schema, stage, and file path to a set of files for accessing the unstructured data files in Snowflake?

- A. Scoped URL
- B. File URL
- C. Pre-signed URL
- D. HTTPS URL

<details><summary>Show Answer</summary>
Correct Answer: B. A File URL fully identifies the database/schema/stage/path needed to access a specific unstructured file.
</details>

---

### Question 1264
Which Snowflake feature or service is primarily used for managing and monitoring data and user activities?

- A. Snowsight
- B. SnowSQL
- C. Marketplace
- D. Streamlit

<details><summary>Show Answer</summary>
Correct Answer: A. Snowsight is Snowflake's primary web UI for monitoring queries, warehouses, and user/data activity.
</details>

---

### Question 1265
Which URL should be used for custom applications that need to access unstructured data files without Snowflake authentication?

- A. Scoped URL
- B. File URL
- C. Pre-signed URL
- D. Relative URL

<details><summary>Show Answer</summary>
Correct Answer: C. Pre-signed URLs grant temporary, authentication-free access, suitable for external custom applications.
</details>

---

### Question 1266
When would creating and using a Standard View be preferable to using a Materialized View?

- A. The underlying query takes a lot of time to execute.
- B. The underlying query of the view is resource-intensive.
- C. The underlying query of the view is run on large data sets.
- D. The view results change often.

<details><summary>Show Answer</summary>
Correct Answer: D. Standard views recompute on every query, making them a better fit than materialized views when the underlying data changes frequently (avoiding materialized-view maintenance overhead/staleness).
</details>

---

### Question 1267
When using a direct share, what privileges does a role need to control access to the objects that are in a share that is using database roles? (Choose two.)

- A. CREATE PIPE
- B. CREATE STREAM
- C. CREATE TASK
- D. CREATE SHARE
- E. CREATE DATABASE

<details><summary>Show Answer</summary>
Correct Answer: D, E. Creating and controlling a share that segments access via database roles requires the global CREATE SHARE and CREATE DATABASE privileges.
</details>

---

### Question 1268
What actions can be performed by consumers of shared databases? (Choose two.)

- A. Create a clone of the database.
- B. Edit the comments for the database.
- C. Use Time Travel data on the database.
- D. Create streams on objects in the database.
- E. Query data from the objects in the database.

<details><summary>Show Answer</summary>
Correct Answer: D, E. Consumers can query shared objects and create their own streams on shared tables/views; they cannot clone, comment on, or use Time Travel against someone else's shared database.
</details>

---

### Question 1269
A Snowflake user is actively logged into Snowflake when a user-level network policy is assigned to that user. What will Snowflake do if the user's IP address does not match the user-level network policy rules?

- A. Log the user out immediately.
- B. Deactivate the network policy.
- C. Prevent the user from executing additional queries.
- D. Allow the user to continue until the session or login token expires.

<details><summary>Show Answer</summary>
Correct Answer: C. The user is blocked from executing further queries once their IP no longer matches the policy, though the current session isn't forcibly terminated.
</details>

---

### Question 1270
At what level is the DATA_RETENTION_TIME_IN_DAYS parameter configurable in Snowflake?

- A. User
- B. Session
- C. Account, Database, Schema, Table
- D. Virtual warehouse

<details><summary>Show Answer</summary>
Correct Answer: C. DATA_RETENTION_TIME_IN_DAYS can be set at the account, database, schema, or table level.
</details>

---

### Question 1271
How can data be securely shared across regions and cloud platforms in Snowflake?

- A. Use Cross-Cloud Auto-fulfillment.
- B. Use database replication.
- C. Use the CREATE SHARE command.
- D. Use the GRANT command to share selected objects.

<details><summary>Show Answer</summary>
Correct Answer: B. Standard shares only work within a single region/cloud; cross-region/cross-cloud sharing requires replicating the database first.
</details>

---

### Question 1272
What factors affect how many credits will be charged for virtual warehouse usage? (Choose two.)

- A. Number of queries being executed
- B. Number of users running queries
- C. Snowflake edition being used
- D. Size of the warehouse
- E. Length of time the warehouse runs

<details><summary>Show Answer</summary>
Correct Answer: D, E. Warehouse credit cost scales with warehouse size and how long it runs — not directly with query or user count.
</details>

---

### Question 1273
What privilege is required to view the load statistics on a virtual warehouse?

- A. MODIFY
- B. OPERATE
- C. MONITOR
- D. USAGE

<details><summary>Show Answer</summary>
Correct Answer: C. The MONITOR privilege allows a role to view a warehouse's usage/load statistics.
</details>

---

### Question 1274
Which command will indicate whether a materialized view is being used in a query?

- A. SHOW
- B. DESCRIBE
- C. EXPLAIN
- D. USE

<details><summary>Show Answer</summary>
Correct Answer: C. EXPLAIN reveals the query execution plan, including whether the optimizer rewrote the query to use a materialized view.
</details>

---

### Question 1275
A size X-Small Virtual warehouse ran for 90 seconds and was shut down. The warehouse was then run for another 30 seconds before being shut down again. How many seconds will be billed?

- A. 90 seconds
- B. 120 seconds
- C. 150 seconds
- D. 180 seconds

<details><summary>Show Answer</summary>
Correct Answer: C. Each warehouse resume incurs a 60-second minimum charge. First run: 90 sec (already over the minimum). Second run: only 30 sec of actual use, but billed for the 60-second minimum. Total: 90 + 60 = 150 seconds.
</details>

---

### Question 1276
Which virtual warehouse configuration is recommended specifically for a steady workload that has no execution lag?

- A. AUTO_RESUME = FALSE
- B. AUTO_SUSPEND = 0 (or FALSE)
- C. STATEMENT_TIMEOUT_IN_SECONDS = 3600
- D. MAX_CLUSTER_COUNT = 1

<details><summary>Show Answer</summary>
Correct Answer: B. Disabling auto-suspend keeps the warehouse continuously available, appropriate for a steady, uninterrupted workload.
</details>

---

### Question 1277
Which role allows a Snowflake user to view table-level storage utilization information from the ACCOUNT_USAGE view by default?

- A. ACCOUNTADMIN
- B. SECURITYADMIN
- C. SYSADMIN
- D. USERADMIN

<details><summary>Show Answer</summary>
Correct Answer: A. Only ACCOUNTADMIN has default access to ACCOUNT_USAGE views, including storage-utilization data, unless additional grants are made.
</details>

---

### Question 1278
This statement is run: `SELECT mycolumn FROM table;`. What notations will retrieve the 'value' from the VARIANT column assuming the structure is `{"key": {"subkey": "value"}}`? (Choose two.)

- A. mycolumn:key[0]
- B. mycolumn:key.subkey
- C. mycolumn.key.subkey
- D. mycolumn['key'].subkey
- E. mycolumn['key']['subkey']

<details><summary>Show Answer</summary>
Correct Answer: B, E. Both chained colon/dot notation and full bracket notation can traverse nested VARIANT/OBJECT keys.
</details>

---

### Question 1279
Which multi-cluster virtual warehouse setting will help process queued queries as quickly as possible?

- A. An economy scaling policy
- B. A standard scaling policy
- C. Maximized mode
- D. Auto-scale mode

<details><summary>Show Answer</summary>
Correct Answer: B. The standard scaling policy starts additional clusters more aggressively to clear queued queries quickly, at the cost of using more credits than the economy policy.
</details>

---

### Question 1280
Which Snowflake tool provides detailed execution statistics of a query with no cost to the user?

- A. Query Profile
- B. Query history
- C. Visualization chart
- D. Query acceleration service

<details><summary>Show Answer</summary>
Correct Answer: A. Query Profile is a free, built-in visual breakdown of a query's execution steps and statistics.
</details>

---

### Question 1281
How can a Snowflake user access near real-time metrics that can be used to identify queries affected by disk spilling?

- A. Use a load monitoring chart.
- B. Review the history section of the Query Profile.
- C. Implement a Snowsight dashboard.
- D. Use a worksheet.

<details><summary>Show Answer</summary>
Correct Answer: B. The Query History/Query Profile surfaces near real-time execution metrics, including bytes spilled to local or remote storage.
</details>

---

### Question 1282
Which table type is used in the file processing pipeline to expose unstructured data?

- A. Directory table
- B. External table
- C. Standard table
- D. Transient table

<details><summary>Show Answer</summary>
Correct Answer: A. A directory table stores file-level metadata (including URLs) for unstructured files staged in Snowflake.
</details>

---

### Question 1283
Which metrics in the QUERY_HISTORY Account_Usage View can be used to assess the pruning efficiency of a query? (Choose two.)

- A. EXECUTION_TIME
- B. PARTITIONS_TOTAL
- C. COMPILATION_TIME
- D. BYTES_SCANNED
- E. PARTITIONS_SCANNED

<details><summary>Show Answer</summary>
Correct Answer: B, E. Comparing PARTITIONS_SCANNED to PARTITIONS_TOTAL directly shows how effectively a query pruned micro-partitions.
</details>

---

### Question 1284
How should a data provider securely share Snowflake objects with a data consumer who does not have a Snowflake account?

- A. Give the consumer owner rights on the provider's Snowflake account.
- B. Unload the data into the consumer's Cloud Storage.
- C. Create a reader account for the consumer.
- D. Create and replicate a share, then give the consumer access to the replication.

<details><summary>Show Answer</summary>
Correct Answer: C. A reader account lets a provider give a non-Snowflake consumer secure, managed access to shared data, with all costs billed to the provider.
</details>

---

### Question 1285
When unloading Snowflake relational data to a parquet file format, why should the PARTITION BY clause be used?

- A. It will provide a mechanism to encrypt each micro-partition with a unique key.
- B. It will guarantee data integrity by splitting the data into smaller, manageable chunks.
- C. It will increase storage efficiency by automatically compressing data based on access patterns.
- D. It will optimize query performance by filtering relevant partitions without scanning the entire dataset.

<details><summary>Show Answer</summary>
Correct Answer: D. PARTITION BY groups unloaded Parquet output into logical partitions so downstream tools/queries can skip irrelevant files.
</details>

---

### Question 1286
How can a user access information about a query execution plan without consuming virtual warehouse compute resources?

- A. Use the EXPLAIN function.
- B. Review the Query Profile metrics.
- C. Review the data in the Account_Usage view.
- D. Use the Snowsight dashboard.

<details><summary>Show Answer</summary>
Correct Answer: A. EXPLAIN returns the query plan without actually executing the query, so no warehouse compute is consumed.
</details>

---

### Question 1287
If a query is being used to unload a 1 TB table into a stage, which DML operator will be shown in the Query Profile?

- A. INSERT
- B. UNLOAD
- C. COPY
- D. UPDATE

<details><summary>Show Answer</summary>
Correct Answer: C. Unload operations appear as a COPY operator in the Query Profile.
</details>

---

### Question 1288
At what levels can network policies be defined in Snowflake? (Choose two.)

- A. User
- B. Account
- C. Table
- D. Schema
- E. Database

<details><summary>Show Answer</summary>
Correct Answer: A, B. Network policies can be attached at the account level or to individual users.
</details>

---

### Question 1289
A Snowflake table that is loaded using a Kafka connector has a schema consisting of which two VARIANT columns? (Choose two.)

- A. RECORD_TIMESTAMP
- B. RECORD_CONTENT
- C. RECORD_KEY
- D. RECORD_PARTITION
- E. RECORD_METADATA

<details><summary>Show Answer</summary>
Correct Answer: B, E. Kafka connector tables store the raw message as RECORD_CONTENT and Kafka message metadata as RECORD_METADATA, both VARIANT columns.
</details>

---

### Question 1290
When working with table MY_TABLE that contains 10 rows, which sampling query will always return exactly 5 rows?

- A. SELECT * FROM MY_TABLE SAMPLE SYSTEM (50);
- B. SELECT * FROM MY_TABLE SAMPLE BERNOULLI (50);
- C. SELECT * FROM MY_TABLE SAMPLE (5 ROWS);
- D. SELECT * FROM MY_TABLE SAMPLE SYSTEM (1) SEED 1;

<details><summary>Show Answer</summary>
Correct Answer: C. SAMPLE (n ROWS) is a fixed-size (non-probabilistic) sampling method that always returns exactly n rows from a single table; percentage-based SYSTEM/BERNOULLI sampling is probabilistic and not guaranteed to hit an exact count.
</details>

---

### Question 1291
How can files in a Stage be loaded after the file metadata has expired? (Choose two.)

- A. Set the RETURN_FAILED_ONLY parameter to TRUE.
- B. Remove the files from the stage and reload them.
- C. Set the FORCE parameter to TRUE.
- D. Truncate the target table and reload the files.
- E. Use the ALTER command.

<details><summary>Show Answer</summary>
Correct Answer: B, C. Either re-adding the files to the stage or forcing the load with FORCE = TRUE bypasses the load-history/metadata check.
</details>

---

### Question 1292
How should a Snowflake user access a third-party SaaS service to process unstructured data?

- A. Use internal functions.
- B. Use external functions.
- C. Use process functions.
- D. Use an API gateway natively.

<details><summary>Show Answer</summary>
Correct Answer: B. External functions let Snowflake SQL call out to external services (e.g., a third-party SaaS API) for processing.
</details>

---

### Question 1293
What statement describes Snowflake data architecture?

- A. NOSQL warehouse as a service
- B. Single-node, isolated data
- C. Multi-cluster, Shared data
- D. Centralized data storage and processing

<details><summary>Show Answer</summary>
Correct Answer: C. Snowflake uses a multi-cluster, shared-data architecture that separates storage, compute, and cloud services while sharing a single copy of data across clusters.
</details>

---

### Question 1294
Which command will list all of the dropped accounts in an organization that have been deleted?

- A. SHOW MANAGED ACCOUNTS;
- B. SHOW ORGANIZATION ACCOUNTS;
- C. SHOW ORGANIZATION ACCOUNTS HISTORY;
- D. SHOW ORGANIZATION ACCOUNTS LIKE 'dropped%';

<details><summary>Show Answer</summary>
Correct Answer: C. SHOW ORGANIZATION ACCOUNTS HISTORY lists all accounts in the organization, including ones that have been dropped.
</details>

---

### Question 1295
What privileges are required to activate a network policy for an individual user within a Snowflake account?

- A. A role that has been granted the global ATTACH POLICY privilege
- B. A role that has been granted the CREATE SESSION POLICY privilege
- C. A role that has been granted the CREATE NETWORK POLICY privilege
- D. A role that has been granted the OWNERSHIP privilege on both the user and the network policy

<details><summary>Show Answer</summary>
Correct Answer: D. Attaching a network policy to a specific user requires OWNERSHIP on both the user object and the network policy.
</details>

---

### Question 1296
How does Snowflake use Multi-Factor Authentication (MFA)?

- A. MFA is an integrated feature powered by the Duo service.
- B. MFA is enabled by default for any user having the ACCOUNTADMIN role.
- C. An MFA login is designed to log in to Snowflake only through Snowsight.
- D. MFA is enabled by default for each user and does not require activation.

<details><summary>Show Answer</summary>
Correct Answer: A. Snowflake's built-in MFA is powered by the Duo Security service.
</details>

---

### Question 1297
Which command is used to download data from Snowflake to a client machine?

- A. COPY INTO [location]
- B. EXPORT
- C. DROP
- D. GET

<details><summary>Show Answer</summary>
Correct Answer: D. GET downloads files from an internal stage to the local client machine.
</details>

---

### Question 1298
Which function, when added to a SELECT statement, will return a randomly-selected, specified number of rows from a table?

- A. AVERAGE([num] ROWS)
- B. RANDOM([num] ROWS)
- C. SAMPLE([num] ROWS)
- D. LIMIT([num] ROWS)

<details><summary>Show Answer</summary>
Correct Answer: C. SAMPLE([num] ROWS) (or its TABLESAMPLE alias) returns a specified number of rows sampled from the table.
</details>

---

### Question 1299
Which data governance feature supports the tracking of sensitive data for compliance, discovery, and resource usage?

- A. Row access policies
- B. Data Classification
- C. Object dependencies
- D. Object tagging

<details><summary>Show Answer</summary>
Correct Answer: D. Object tagging is Snowflake's mechanism for tracking sensitive data and resource usage to support compliance and discovery.
</details>

---

### Question 1300
When an ACCOUNTADMIN gives a user a Custom role, what privilege is provided by default?

- A. All privileges that have been granted to the ACCOUNTADMIN
- B. All objects allowed by the custom role
- C. Access to the PUBLIC role
- D. Access to all the objects by the USERADMIN role

<details><summary>Show Answer</summary>
Correct Answer: C. Every role automatically has the PUBLIC role (and whatever it's been granted) available to it by default.
</details>

---



====================================================================================================
# snowpro_1301-1352.md
====================================================================================================

# SnowPro Core Practice Questions — 1301 to 1352

*Formatted and cross-checked against current Snowflake documentation (July 2026). Answers are hidden in collapsible blocks — click "Show Answer" to reveal. Corrections to the original answer key are flagged with ⚠ Updated.*

---

### Question 1301
Which query metric can be used to monitor the health of a large table?

- A. Clustering depth
- B. Clustering key
- C. Total partition count
- D. Total number of rows

<details><summary>Show Answer</summary>
Correct Answer: A. Clustering depth measures how well-clustered a table's micro-partitions are; a lower depth means better pruning efficiency.
</details>

---

### Question 1302
What function should be used to convert JSON NULL values to SQL NULL values when loading data into a Snowflake table?

- A. TRY_CAST
- B. STRIP_NULL_VALUE
- C. FLATTEN
- D. PARSE_JSON

<details><summary>Show Answer</summary>
Correct Answer: B. STRIP_NULL_VALUE converts a JSON "null" value to a true SQL NULL.
</details>

---

### Question 1303
What is the recommended way to insert a VARIANT value into a Snowflake table?

- A. Use a SELECT statement to convert data to a VARIANT data type before inserting it.
- B. Use the TO_VARIANT function in the INSERT statement.
- C. Cast the data to a VARIANT data type within the INSERT statement.
- D. Use a subquery to convert the data to a VARIANT data type and then insert it.

<details><summary>Show Answer</summary>
Correct Answer: A. Use a SELECT statement (e.g., `INSERT INTO table SELECT PARSE_JSON(...)` or `INSERT INTO table SELECT TO_VARIANT(...)`) to convert the value to VARIANT before it lands in the table.

**⚠ Updated:** The original key listed B. Current Snowflake documentation explicitly states that the TO_VARIANT function cannot be used directly in an INSERT ... VALUES statement — it must be used inside an INSERT INTO ... SELECT. A is the documented recommended pattern.
</details>

---

### Question 1304
Which process does Snowflake follow when a stored procedure with owner's rights is called within a session?

- A. The procedure will be run with the privileges of the caller.
- B. The procedure is run with the privileges of the owner.
- C. The procedure will inherit the caller's current virtual warehouse.
- D. The owner can set the caller's session variables.

<details><summary>Show Answer</summary>
Correct Answer: B. Owner's rights stored procedures execute with the privileges of the role that owns the procedure, not the caller.
</details>

---

### Question 1305
Which view can be used to track the read and write operations that have been performed on a table?

- A. COPY_HISTORY
- B. ACCESS_HISTORY
- C. QUERY_HISTORY
- D. TASK_HISTORY

<details><summary>Show Answer</summary>
Correct Answer: B. ACCESS_HISTORY records read and write access to table and column-level objects.
</details>

---

### Question 1306
What object does Snowflake recommend using when planning to unload similarly-formatted data on a regular basis?

- A. Stream
- B. Task
- C. Storage integration
- D. Named file format

<details><summary>Show Answer</summary>
Correct Answer: D. A named file format lets you define the format once and reuse it across repeated COPY INTO operations.
</details>

---

### Question 1307
How should a table function be called?

- A. SELECT DUAL;
- B. SELECT [function];
- C. SELECT * FROM TABLE([function]);
- D. SELECT * by [function];

<details><summary>Show Answer</summary>
Correct Answer: C. Table functions must be called from the FROM clause, wrapped in the TABLE(...) syntax.
</details>

---

### Question 1308
Which of the following functions will retrieve a valid SQL NULL?

- A. SELECT NULL;
- B. SELECT 'NULL';
- C. SELECT NULL('l');
- D. SELECT parse_json('null');

<details><summary>Show Answer</summary>
Correct Answer: A. SELECT NULL; returns an actual SQL NULL. 'NULL' (B) is a string, and PARSE_JSON('null') (D) returns a JSON null stored as VARIANT, not a SQL NULL.
</details>

---

### Question 1309
What is the MINIMUM Snowflake edition that supports the periodic rekeying of encrypted data?

- A. Standard
- B. Enterprise
- C. Business Critical
- D. Virtual Private Snowflake (VPS)

<details><summary>Show Answer</summary>
Correct Answer: B. Periodic rekeying requires Enterprise Edition or higher (confirmed current as of July 2026).
</details>

---

### Question 1310
While preparing to unload data in Snowflake, the file format option can be specified in which commands? (Choose two.)

- A. GET
- B. CREATE STAGE
- C. PUT
- D. COPY INTO [location]
- E. CREATE PIPE

<details><summary>Show Answer</summary>
Correct Answer: B, D. FILE_FORMAT can be defined on a stage (CREATE STAGE) or specified directly in a COPY INTO statement.
</details>

---

### Question 1311
Which Query Profile operator provides information on pruning efficiency?

- A. TableScan
- B. InternalObject
- C. Join
- D. Generator

<details><summary>Show Answer</summary>
Correct Answer: A. The TableScan operator shows partitions scanned vs. total partitions, which reflects pruning efficiency.
</details>

---

### Question 1312
What metadata is stored for each micro-partition? (Choose two.)

- A. The number of distinct values
- B. The clustering key used in the table
- C. The average depth of values for each of the columns
- D. The range of values for each of the columns in the full table
- E. The minimum and maximum values for each of the columns

<details><summary>Show Answer</summary>
Correct Answer: A, E. Snowflake stores the number of distinct values and the min/max range per column, scoped to that individual micro-partition (not the full table, which rules out D as worded).
</details>

---

### Question 1313
Which role has the HIGHEST precedence among roles that will serve as the owners of securable objects?

- A. USERADMIN
- B. SYSADMIN
- C. SECURITYADMIN
- D. ACCOUNTADMIN

<details><summary>Show Answer</summary>
Correct Answer: D. ACCOUNTADMIN sits at the top of the default role hierarchy.
</details>

---

### Question 1314
How is data protected in transit and at rest throughout its lifecycle? (Choose two.)

- A. Users are responsible for encrypting data before uploading to Snowflake.
- B. Snowflake automatically tags and masks Personal Identifiable Information (PII).
- C. Snowflake automatically encrypts data before copying the data to the cloud over an encrypted connection.
- D. Snowflake automatically rotates key pairs regularly, using a hierarchical key model stored in a hardware security module.
- E. Users are responsible for uploading and configuring key pair rotation schedules and key sizes to encrypt stored data.

<details><summary>Show Answer</summary>
Correct Answer: C, D. Encryption in transit/at rest and automatic key rotation via a hierarchical key model (backed by an HSM) are both handled automatically by Snowflake — no user configuration required.
</details>

---

### Question 1315
Which Snowflake virtual warehouse configuration enables horizontal scaling?

- A. Increasing the WAREHOUSE_SIZE
- B. Increasing the MAX_CLUSTER_COUNT
- C. Increasing the MIN_CLUSTER_COUNT
- D. Increasing the STATEMENT_TIMEOUT_IN_SECONDS

<details><summary>Show Answer</summary>
Correct Answer: B. Increasing WAREHOUSE_SIZE is vertical scaling; increasing MAX_CLUSTER_COUNT (multi-cluster warehouses) is horizontal scaling.
</details>

---

### Question 1316
Which Snowflake objects can execute both DDL and DML statements?

- A. External functions
- B. Stored procedures
- C. User-Defined Functions (UDFs)
- D. Table Functions

<details><summary>Show Answer</summary>
Correct Answer: B. Stored procedures can execute both DDL and DML; UDFs cannot execute DDL.
</details>

---

### Question 1317
Which object consumes Snowflake credits for its maintenance?

- A. Materialized view
- B. View
- C. External table
- D. Table

<details><summary>Show Answer</summary>
Correct Answer: A. Materialized views consume compute credits for the automatic background maintenance service that keeps them in sync with the base table.
</details>

---

### Question 1318
To log into Snowflake using SnowSQL, what are methods to explicitly specify the connection parameters? (Choose two.)

- A. Use public and private key pair authentication
- B. Run a web-based authorization
- C. Use an auth token
- D. Enter through an interactive prompt
- E. Specify using SNOWSQL_PWD and environment variables

<details><summary>Show Answer</summary>
Correct Answer: D, E. Connection parameters can be entered interactively at the prompt or supplied via environment variables like SNOWSQL_PWD.
</details>

---

### Question 1319
A team is developing a machine learning model by training on the latest Snowflake features. The training is taking much longer than expected to complete. Which step will accelerate the model training?

- A. Increase the size of the virtual warehouse.
- B. Add additional clusters to the virtual warehouse.
- C. Use a Snowpark-optimized virtual warehouse.
- D. Enable the query acceleration service.

<details><summary>Show Answer</summary>
Correct Answer: C. Snowpark-optimized warehouses provide the higher memory-to-core ratio needed for memory-intensive ML training workloads.
</details>

---

### Question 1320
Which object can be shared using Secure Data Sharing?

- A. Secure view
- B. Materialized view
- C. External function
- D. User-Defined Function (UDF)

<details><summary>Show Answer</summary>
Correct Answer: A. Secure views are directly shareable. Standard (non-secure) materialized views and UDFs are not shareable as listed here.
</details>

---

### Question 1321
How is Single Sign-on (SSO) authentication used in Snowflake?

- A. SSO is an authentication method which uses a pair of keys, a public key and a private key, to verify the identity of a user.
- B. SSO is an authentication method that uses a username and password in the API request header.
- C. SSO is an authentication method that allows a user to sign into multiple applications with a single set of credentials.
- D. SSO is an integrated Snowflake feature, managed entirely by Snowflake natively.

<details><summary>Show Answer</summary>
Correct Answer: C. SSO lets a user authenticate once with an external identity provider and access multiple applications, including Snowflake, without re-entering credentials.
</details>

---

### Question 1322
Which clause is used to define a function that may return different values for different rows?

- A. IMMUTABLE
- B. RETURNS
- C. COMMENT
- D. VOLATILE

<details><summary>Show Answer</summary>
Correct Answer: D. VOLATILE indicates the function's output can vary between calls, even with the same input.
</details>

---

### Question 1323
In Snowflake, how can query pruning information statistics be identified?

- A. Partitions scanned
- B. Bytes scanned
- C. Bytes spilled to remote storage
- D. Percentage scanned from cache

<details><summary>Show Answer</summary>
Correct Answer: A. "Partitions scanned" vs. "partitions total" in the Query Profile directly reflects pruning effectiveness.
</details>

---

### Question 1324
How does the authorization associated with a URL for an unstructured file work?

- A. Anyone who has the URL can access the referenced file for the life of the token.
- B. Only the user who created the URL can use it to access the referenced file.
- C. Only the users who have roles with sufficient privileges on the URL can access the referenced file.
- D. The role specified in the GET REST API call must have sufficient privileges on the stage to access the referenced file using the URL.

<details><summary>Show Answer</summary>
Correct Answer: D. Confirmed current: for a (non-scoped, non-presigned) file URL, Snowflake authenticates the caller and verifies the active role has sufficient privileges on the stage before serving the file.
</details>

---

### Question 1325
What will happen if the volume of data stored in Snowflake increases over time?

- A. Snowflake will automatically increase the size of the virtual warehouse used to run queries against the storage data.
- B. The number of clusters in the active virtual warehouse being used will scale automatically to accommodate the increased storage data volume.
- C. As the stored data volume increases, the warehouse performance will decline.
- D. The warehouse performance and size will not be affected when the volume of stored data increases.

<details><summary>Show Answer</summary>
Correct Answer: D. Storage and compute are independently scaled in Snowflake, so growing storage volume alone does not affect warehouse size or performance.
</details>

---

### Question 1326
What can a reader account user do when accessing shared data? (Choose two.)

- A. Insert new data using the COPY INTO [location] command
- B. Execute secure User-Defined Functions (UDFs)
- C. Remove records using the DELETE command
- D. Select data from secure views
- E. Modify records using the UPDATE and MERGE commands

<details><summary>Show Answer</summary>
Correct Answer: B, D. Reader accounts have read-only access — they can query secure views and call secure UDFs, but cannot insert, update, or delete shared data.
</details>

---

### Question 1327
What is a fundamental characteristic of Snowflake micro-partitions?

- A. They can be read directly as files.
- B. They serve as an index for Snowflake tables.
- C. They are sized based on Time Travel requirements.
- D. Once established, they cannot be changed (they are immutable).

<details><summary>Show Answer</summary>
Correct Answer: D. Micro-partitions are immutable; any update rewrites the affected partitions rather than modifying them in place.
</details>

---

### Question 1328
What happens when a multi-cluster virtual warehouse is resized?

- A. The auto-suspend feature is automatically enabled for inactive clusters.
- B. The scaling policy of the warehouse is updated.
- C. The new size applies to all clusters within that configuration.
- D. The minimum and maximum number of clusters is automatically adjusted.

<details><summary>Show Answer</summary>
Correct Answer: C. Resizing a multi-cluster warehouse changes the size uniformly across every cluster in that warehouse.
</details>

---

### Question 1329
Using which copy option when unloading data allows users to include a Universally Unique Identifier (UUID) in the names of unloaded files?

- A. VALIDATION_MODE
- B. SINGLE = TRUE
- C. HEADER = TRUE
- D. INCLUDE_QUERY_ID

<details><summary>Show Answer</summary>
Correct Answer: D. INCLUDE_QUERY_ID = TRUE embeds the query ID (a UUID) into the unloaded file names.
</details>

---

### Question 1330
Which Snowflake objects use storage? (Choose two.)

- A. Regular table
- B. Regular view
- C. Cached query result
- D. Materialized view
- E. External table

<details><summary>Show Answer</summary>
Correct Answer: A, D. Regular tables and materialized views both persist data and consume Snowflake storage. Views don't store data, and external tables reference data that lives outside Snowflake's storage layer.
</details>

---

### Question 1331
What type of access control states that each object within Snowflake has a unique owner who can grant access to that object?

- A. Role-Based Access Control (RBAC)
- B. Discretionary Access Control (DAC)
- C. Mandatory Access Control (MAC)
- D. Rule-Based Access Control (RuBAC)

<details><summary>Show Answer</summary>
Correct Answer: B. Snowflake combines RBAC (privileges assigned to roles) with DAC (every object has an owner who can grant access to it).
</details>

---

### Question 1332
Which Snowflake multi-cluster virtual warehouse scaling policy or mode will MINIMIZE query queuing by prioritizing the startup of additional clusters?

- A. Custom policy
- B. Standard policy
- C. Economy mode
- D. Maximized mode

<details><summary>Show Answer</summary>
Correct Answer: B. Standard scaling policy favors starting additional clusters quickly to avoid queuing, at the cost of potentially higher credit usage. Economy mode favors conserving credits and tolerates more queuing.
</details>

---

### Question 1333
Which default warehouse configuration has the highest precedence whenever a new session is created by a user?

- A. Default warehouse for the user
- B. Default warehouse in the configuration file of the client utilities
- C. Default warehouse specified on a CLI or in drivers/connectors parameters
- D. Default warehouse of the role assigned to the user

<details><summary>Show Answer</summary>
Correct Answer: C. An explicit warehouse parameter passed via CLI/driver/connector at connection time overrides the user-level and role-level defaults.
</details>

---

### Question 1334
What type of authentication is recommended when creating a Snowflake service account that will connect to a third-party application?

- A. Username and password
- B. Key-pair authentication
- C. Multi-Factor Authentication (MFA)
- D. Single Sign-on (SSO)

<details><summary>Show Answer</summary>
Correct Answer: B. Key-pair authentication is the recommended method for programmatic/service accounts. This holds even more firmly now — Snowflake deprecated single-factor username/password authentication for such use cases in late 2025, pushing service accounts toward key-pair or OAuth.
</details>

---

### Question 1335
Which type of query would benefit from enabling the query acceleration service on the virtual warehouse?

- A. Queries with no filters or aggregation
- B. Queries that are queued in the warehouse
- C. Queries that use more resources than the typical query
- D. Queries that contain a high cardinality GROUP BY expression

<details><summary>Show Answer</summary>
Correct Answer: C. QAS is designed to accelerate "outlier" queries — ones that consume more resources than the warehouse's typical query — by offloading part of the scan/aggregation work to shared serverless compute.

**⚠ Updated:** The original source garbled option C to "less memory than the typical query" and marked D as correct. Both are wrong: Snowflake's documentation explicitly states outlier queries are defined as those using *more* resources than typical, and a *high-cardinality* GROUP BY is actually listed as a common reason a query becomes **ineligible** for acceleration — the opposite of a benefit.
</details>

---

### Question 1336
Which table function will return the output of a previously-run command?

- A. FLATTEN
- B. QUERY_HISTORY
- C. TASK_HISTORY
- D. RESULT_SCAN

<details><summary>Show Answer</summary>
Correct Answer: D. RESULT_SCAN(query_id) returns the result set of a previously executed query.
</details>

---

### Question 1337
How can a relational table be unloaded into a JSON file?

- A. Use the OBJECT_CONSTRUCT function in conjunction with the COPY INTO command.
- B. Use the COPY INTO [location] command with the file_format set to JSON.
- C. Use the PUT command with the format set as JSON.
- D. Use the GET command with the file format set as JSON.

<details><summary>Show Answer</summary>
Correct Answer: A. A relational table's rows must first be converted into VARIANT objects with OBJECT_CONSTRUCT before COPY INTO can unload them as JSON.
</details>

---

### Question 1338
When do Snowflake object owners lose their ability to make grant decisions?

- A. When the object owner has been granted a database role.
- B. When the object owner has been granted an account role.
- C. When the object is part of a managed access schema.
- D. When the object is part of a regular schema.

<details><summary>Show Answer</summary>
Correct Answer: C. In a managed access schema, grant decisions are centralized to the schema owner (or a role with MANAGE GRANTS), stripping individual object owners of that ability.
</details>

---

### Question 1339
Which command allows a user to unload data from a Snowflake database table into one or more files in a Snowflake external stage?

- A. GET
- B. LIST
- C. PUT
- D. COPY INTO [location]

<details><summary>Show Answer</summary>
Correct Answer: D. COPY INTO <location> unloads table data into stage files. PUT is used to upload local files to an internal stage instead.
</details>

---

### Question 1340
Which Snowflake feature enables loading data from Cloud Storage as files are available in a Stage?

- A. COPY INTO [location] command
- B. Data replication
- C. Snowpipe
- D. Direct Share

<details><summary>Show Answer</summary>
Correct Answer: C. Snowpipe continuously loads data as new files land in a stage, using event notifications or REST calls.
</details>

---

### Question 1341
Which JSON paths are considered to be equivalent in Snowflake? (Choose two.)

- A. src:Customer['EMAIL']
- B. SRC:Customer.Email
- C. src['customer']['email']
- D. src:customer.email
- E. SRC:customer.email

<details><summary>Show Answer</summary>
Correct Answer: D, E. The column/table alias portion of a path (src vs. SRC) is case-insensitive when unquoted, but the JSON element names after the colon are case-sensitive — so D and E match while A, B, and C reference different casing of the actual keys.
</details>

---

### Question 1342
Which privilege is required for a user to be able to view a resource monitor?

- A. USAGE
- B. SELECT
- C. MONITOR
- D. OPERATE

<details><summary>Show Answer</summary>
Correct Answer: C. MONITOR grants visibility into a resource monitor's configuration and usage.
</details>

---

### Question 1343
What happens when a table or schema with a standard retention period is dropped?

- A. The object is immediately removed from the system.
- B. The object is instantaneously moved to Fail-safe.
- C. The object is retained but all associated data is immediately purged.
- D. The object is retained in Time Travel for the data retention period.

<details><summary>Show Answer</summary>
Correct Answer: D. A dropped object remains recoverable via Time Travel (UNDROP) for its configured retention period before moving to Fail-safe.
</details>

---

### Question 1344
When cloning tables, which INFORMATION_SCHEMA view will show different columns for owned storage and referenced storage?

- A. TABLES
- B. TABLE_HISTORY
- C. TABLE_STORAGE_METRICS
- D. STORAGE_USAGE

<details><summary>Show Answer</summary>
Correct Answer: C. TABLE_STORAGE_METRICS breaks out storage into columns like ACTIVE_BYTES vs. bytes still referenced from clone source tables.
</details>

---

### Question 1345
Based on a review of a Query Profile, which scenarios will benefit the MOST from the use of a data clustering key? (Choose two.)

- A. A column that appears most frequently in ORDER BY operations
- B. A column that appears most frequently in WHERE operations
- C. A column that is used most frequently in GROUP BY operations
- D. A column that appears most frequently in AGGREGATE operations
- E. A column that appears most frequently in JOIN operations

<details><summary>Show Answer</summary>
Correct Answer: B, E. Clustering keys most improve performance for columns used heavily in filters (WHERE) and joins, since these drive micro-partition pruning.
</details>

---

### Question 1346
When working with dimension tables that change frequently, what is the recommended way to manage costs?

- A. Keep the Time Travel retention period on the dimension tables to 1 day or less.
- B. Make the dimension tables transient with a retention period of 0 days, and backup the table daily to a permanent table. Delete all but the latest backup.
- C. Make the dimension tables transient and back-up the data daily into a permanent table using cloning.
- D. Make the dimension tables permanent with a retention period of 7 days. Replicate the database to a secondary database once a week.

<details><summary>Show Answer</summary>
Correct Answer: B. This matches Snowflake's published storage-cost guidance for high-churn dimension tables: set them to transient with 0-day retention, periodically copy contents to a permanent table for backup, and delete older backups when a new one is created.
</details>

---

### Question 1347
What Snowflake privilege should be granted to allow a non-ACCOUNTADMIN to access billing and credit usage?

- A. OPERATE
- B. MONITOR USAGE
- C. OWNERSHIP
- D. USAGE

<details><summary>Show Answer</summary>
Correct Answer: B. The MONITOR USAGE global privilege exposes billing, credit consumption, and usage data to roles other than ACCOUNTADMIN.
</details>

---

### Question 1348
A stream can be created on which Snowflake objects to record data manipulation language (DML) changes? (Choose two.)

- A. Databases
- B. Standard tables
- C. Standard views
- D. Schemas
- E. Pipes

<details><summary>Show Answer</summary>
Correct Answer: B, C. Streams can be created on standard tables and standard (as well as secure) views to track row-level DML changes. Databases, schemas, and pipes are not streamable objects.
</details>

---

### Question 1349
When creating a file format to load JSON data into Snowflake, what command will remove brackets from the data array structure?

- A. REMOVE_BRACKETS = TRUE
- B. TRIM_SPACE = TRUE
- C. IGNORE_UTF8_ERRORS = TRUE
- D. STRIP_OUTER_ARRAY = TRUE

<details><summary>Show Answer</summary>
Correct Answer: D. STRIP_OUTER_ARRAY = TRUE removes the outer brackets [ ] and loads each element of the array as a separate row.
</details>

---

### Question 1350
Which virtual warehouse feature setting will reduce the performance impact when running larger-than-average queries, offloading portions of the query processing work to shared compute resources?

- A. Using a multi-cluster virtual warehouse
- B. Using the query acceleration service
- C. Using the search optimization service
- D. Disabling auto-suspend

<details><summary>Show Answer</summary>
Correct Answer: B. This is the defining behavior of the Query Acceleration Service — offloading portions of outlier query processing to serverless shared compute.
</details>

---

### Question 1351
Which schema-level objects allow the user to periodically perform an action under specific conditions, based on data within Snowflake?

- A. Alerts
- B. External tables
- C. Secure Views
- D. Materialized views

<details><summary>Show Answer</summary>
Correct Answer: A. Alerts run a defined condition check on a schedule and trigger an action (e.g., a notification or SQL statement) when that condition is met.
</details>

---

### Question 1352
Which privilege must be granted to show data categories in a Data Exchange?

- A. MONITOR PRIVILEGE
- B. USAGE PRIVILEGE
- C. OWNERSHIP PRIVILEGE
- D. IMPORTED PRIVILEGES

<details><summary>Show Answer</summary>
Correct Answer: D. IMPORTED PRIVILEGES on a Data Exchange delegates administrative tasks — including showing data categories, approving listings, and managing members — to roles other than ACCOUNTADMIN. Confirmed still current as of July 2026; Data Exchange remains a distinct feature alongside Snowflake Marketplace.
</details>

---

*(End of document — Questions 1301–1352)*


