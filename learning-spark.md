# Learning Spark - Second Edition

## Lightning-Fast Data Analytics

> JS Damji, B. Wenig, T. Das, D. Lee

## Introduction

- Spark started in 2009 at UC Berkeley
- *De facto* big data unified processing engine
- Data Engineers
  - Use Spark's Structured API
    - Complex data exploration and analysis
    - Spark SQL for interactive queries
    - Built-in and external data sources
      - Read
      - Refine
      - Write
      - ETL
    - Build reliable Data Lakes with Spark and Delta Lake
  - Data Science
    - MLlib
    - Deploy on MLflow

## 1: Introduction to Apache Spark - Unified Analytics Engine

- Origins of some big data techniques start with googles early efforts to index the web
- New Tools
  - Google File System (GFS)
  - MapReduce (MR)
  - Bigtable
- Yahoo
  - Hadoop
- Some challenges with map reduce - cumbersome, verbose, not fault tolerant
- UC Berkely sought to improve with Spark project 2009
- 10-20 x faster than Hadoop / MR
- By 2013, Spark donated and founders formed Databricks company


**Apache Spark is a unified engine designed for large-scale distributed data processing, on premises in data centers or in the cloud.**

- Design philosophy
  - Speed
    - Price and performance of CPUs and memory
    - Efficient, multithread parallel processing
    - Directed acyclic graph (DAG)
      - Scheduler and query optimizer decomposes tasks executed in parallel
  - Ease of use
    - Fundamental abstraction of a simple logical data structure
      - Resilient Distributed Dataset (RDD)
    - All other abstractions (Dataframes / datasets) derived from there
    - Transformations and actions as operations - simple programming model
  - Modularity
    - Many types of workloads
    - Many languages
      - Java, Scala, Python, SQL, R
    - Unified libraries
    - Well-documented APIs
      - Spark SQL
      - Spark Structured Streaming
      - Spark MLlib
      - GraphX
  - Extensibility
    - Focus on fast, parallel computing, not storage
    - Decoupled
    - Many sources
      - Apache Hadoop
      - Apache Cassandra
      - Apache HBase
      - MongoDB
      - Apache Hive
      - RDBMSs
      - Apache Kafka
      - Kinesis
      - Azure Storage
      - Amazon S3
  - Large third-party ecosystem

### Unified Analytics

s