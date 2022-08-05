# Certification Overview: Databricks Certified Associate Developer for Apache Spark Exam

## Objectives

[ ] Learning context, format, and structure behind the exam
[ ] Topics covered in the exam
[ ] Different types of questions
[ ] Resources to learn the material

- **Does not teach actual content assessed.**

---

## Certification Exam Overview

- LEarnign context, structure, and format
- Target audience is broad
  - Any role that regularly uses dataframe API
  - Data engineer
  - ML Engineer
  - Data Scientist
  - Associate-level certification
  - Level equivalent to **six months experience** with Apache Spark DataFrame API
- Expectations
  - Understand the basics of Spark architecture
  - Adaptive Query Execution
  - Apply API to complete individual data manipulation tasks including:
    - Selecting, renaming and manipulating columns
    - Foltering, dropping, sorting, and aggregating rows
    - Joining, reading, writing and partitioning DataFrames
    - Woeking with user defined functions (UDFs) and Spark SQL functions
- Out of scope:
  - SQL
  - Tuning and optimizations
  - Structured Streaming
  - Data Lake
  - Spark MLib and Spark ML

### [Exam Details](https://databricks.com/certification/apache-spark-developer-associate)

## Exam Logistics

- Offered through Kryterion Webassessor platform
- [Exam registration](https://webassessor.com/databricks)
- Proctored by webcam
- PDF of Apache Spark documentation (not searchable)
- Automatically graded
- Receive pass/fail and topic-level percentages scores immediately
- Certificate awarded via credentials.databricks.com
  - PDF
  - Linked-in
- Receive within 24 hours after taking the exam

## Exam Details

- 120 minutes alloted
- 70% to pass
- $200 Fee
- 60 questions
- [Databricks academy FAQ](http://files.training.databricks.com/lms/docebo/databricks-academy-faq.pdf)

---

## Certification Exam Topics

### Apache Spark Architecture Concepts (17%)

- Understand the basics of Apache Spark architecture
  - Clusters (nodes, executors, slots)
  - Execution hierarchy (application, jobs, stages, tasks)
  - Distribution (shuffles, partitions)
  - Execution pattern (lazy evaluation, transformations, actions)
- Clusters
  - Nodes
    - Driver nodes
    - Worker nodes
  - Executors
    - Relationship with worker nodes
    - Relationship with the JVM
  - Slots
    - Description
    - Purpose
- Execution Hierarchy
  - Application
  - Jobs
  - Stages
    - What separates a job into multiple stages
  - Tasks
- Distribution
  - Shuffles
    - Description
    - Operations that result in a shuffle
    - Configurations prone to a lot of shuffling
  - Partitions
    - Description
    - Configurations affecting partitioning
- Execution Patterns
  - Lazy Evaluation
    - Description
    - Advantages
    - Operations that trigger evaluation
  - Transformations
    - Description
    - Narrow vs wide
  - Actions
    - Description

### Self-assesment

- [ ] COmpare and contrast driver nodes from worker nodes
- [ ] Describe the purpose of slots
- [ ] Describe each level of the Spark execution hierarchy
- [ ] Identify when a Spark job will require a shuffle
- [ ] Compare and contrast wide and narrow transformations
- [ ] Describe why certain operations are classified as actions

### Spark Architecture Applications (11%)

- Make correct decisions about sSpark architecture configurations and applications including:
  - Clusters (execution and deployment modes, fault tolerance, and stability)
  - Storage (caching, storage levels, out-of-memory errors, garbage collection)
  - Partitioning (repartitioning, coalescing, data skew, AQE skew handling)
  - Structures (DataFrame)
  - Broadcasting (broadcast variables, broadcast joins, AQE broadcasting)
- Clusters - deploy applications on efficient, reliable clusters
  - Execution and Deployment modes
    - Purpose of driver and executor setup
    - Types of deployment modes
      - Cluster
      - Client
      - Local
  - Fault Tolerance and Stability
    - Reasons a Spark application will fail
    - Fault-tolerant cluster setups
- Storage - describe how Spark stores its data during processing
  - Caching
    - How Spark caches data
    - When to cache DataFrames
  - Storage Levels
    - Types of storage levels
    - Default storage levels
    - When to use each storage level
  - Out-of-memory errors
    - How Spark handles out-of-memory errors
      - Why out of memory errors occur
      - Strategies for reducing out-of--memory errors
    - Garbage Collection
      - Purpose
      - Efficient garbage collection configurations
- Partitioning
  - Repartitioning
    - How to repartition a DataFrame
  - Coalescing
    - How to coalesce a DataFrame
    - Relationship with repartitioning a DataFrame
  - Data Skew
    - Describe
    - General strategies for avoiding data skew
  - AQE Skew Handling
    - Configuration needed for automatic skew handling
- DataFrame - Deploying Spark applications on efficient, reliable clusters
  - Basics
    - Description of spark DataFrames
    - Spark class used as base for DataFrames
  - Types and Execution
    - Possible column types
    - Parallel execution
- Broadcasting - how to broadcast objects for efficient processing
  - Variables
    - How to broadcast a variable
    - What it means to broadcast an object
  - Joins
    - Configurations for automatic broadcast joins
    - When broadcast joins are advantageous
  - AQE
    - How to set up spark to automatically handle broadcast joins using AQE

- [ ] Compare and contrast the cluster, client, and local deployment modes
- [ ] Identify reasons that a Spark application will fail
- [ ] Compare and contrast each storage level option
- [ ] Identify a difference between repartitioning and coalescing
- [ ] Identity the class that a Dataframe is built on top of
- [ ] Describe the idea of broadcasting a variable

### Apache Spark DataFrame API Applications (72%)

- Be able to apply the Apache Spark DataFrame API to complete individual data manipulation tasks, including:
  - Selecting, renaming, and manipulating columns
  - Filtering, dropping, sorting, and aggregating rows
  - Joining, reading, writing, and partitioning DataFrames
  - Working with pandas UDFd and Apache Spark SQL functions
- Colum-level manipulations
  - Subsetting
    - Select columns
    - Drop columns
  - Rename existing columns
  - Manipulating
    - Cast column types
    - Create a constant column
    - Split an existing string column
    - Explode an array column
    - Date manipulations
    - Mathematical operations
- Row-level manipulations
  - Filtering
    - Single-condition
    - Multiple-conditions
  - Dropping
    - Drop duplicates
    - Sampling
  - Sorting
    - Order by one column
    - Change column order
  - Aggregating
    - Summary Descriptions
    - Single/multi-column aggregations
    - Grouped aggregations
- Miscellaneous other common tasks
  - Combining data
    - Joins
    - Broadcast joins
    - Unions
  - I/O
    - Reading and writing
    - Write by partitions
    - Read schemas
    - Persist/caching
  - Partitioning
    -Coalescing
    -Repartitioning

- [ ] Select a subset of columns from a DataFrame
- [ ] Filter a subset of rows from a DataFrame based on two logical criteria
- [ ] Cast a column from a numeric type to a string type
- [ ] Create a new DataFrame column by mathematically combining two existing columns
- [ ] Split a string DataFrame column into multiple new columns based on a regular expression
- [ ] Cache a DataFrame to a specific storage level
- [ ] Aggregate data to find the mean of a column by group
- [ ] Write a DataFrame to disk
- [ ] Extract the month from a DataFrame column of date type
- [ ] Create a UDF to use in a Spark SQL statement

## Certification Exam Questions

- [Practice Exam](https://databricks.com/learn/certification/apache-spark-associate-developer)
- Which of the following describes a shuffle?
  - **A. A shuffle is the process by which data is compared across partitions**
  - B. A shuffle is the process by which data is compared across executors
  - C. A shuffle is the process by which partitions are allocated to tasks
  - D. A shuffle is the process by which partitions are ordered for write
  - E. A shuffle is the process by which tasks are ordered for execution
- Which of the following operations is most likely to introduce a skew in the size of your data's partitions?
  - A. `DataFrame.collect()`
  - B. `DataFrame.cache()`
  - C. `DataFrame.repartition(n)`
  - **D. `DataFrame.coalesce(n)`**
  - E. `DataFrame.persist()`
- Which of the following code blocks returns the sum of the values in column `sqft` in DataFrame `storesDF` grouped by distinct value in column `division`?
  - A. `storesDF.groupBy.agg(sum(col("sqft")))`
  - B. `storesDF.groupBy("division"0.sum(sol("sqft)))`
  - C. `storesDF.agg(groupBY("division").sum(col("sqft")))`
  - D. `storesDF.groupby.agg(sum(col("sqft")))`
  - **E. `storesDF.groupBy("division").agg(sum(col("sqft")))`**

## Certification Exam Preparation

- Apache Spark Learning Pathway
- *Apache Spark Programming With Databricks*
- Take course
- Covers everything you need to know for exam