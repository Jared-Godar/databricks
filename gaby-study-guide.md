# Databricks Study Guide

> Certified Associate Developer for Apache Spark 3.0 Exam

## EXAM FORMAT

- The exam has 60 multiple choice questions.
- You just need to get 42 of them correct to pass.
- You have a total of 120 minutes.
- The two main categories the exam tests you on is:
  - Spark Architecture
  - and the Spark DataFrame API.
- Very basic SQL syntax is needed; for example, some of the questions ask you to select from code that’s in the format `spark.sql(“SELECT * FROM tbl WHERE…”)`
  - but it’s very basic, so no need to study SQL for the exam.
- You **DO** need to study the documentation of the Spark Python API, though.
- About 50 of the questions ask you questions on how to write the correct syntax using that API.

>*Note: Structured Streaming and MLlib are not on this exam, so don’t waste time studying for those topics.*

## SPARK ARCHITECTUR

- This section is broken into two subsets:
  - one is theory based just knowing how the Spark architecture is set up
  - the other is making optimal decisions based on your knowledge of the Spark architecture. (I wouldn’t focus too much on this part of the test though. There were only about 10 questions from this category.)

- As for the basics of the Spark architecture, the following concepts are assessed by this exam (~17%):
  - Cluster architecture: nodes, drivers, workers, executors, slots, etc
  - Spark execution hierarchy: applications, jobs, stages, tasks, etc
  - Shuffling
  - Partitioning
  - Lazy evaluation
  - Transformations vs. action
  - Narrow vs. wide transformation
  - Spark UI
- In addition, candidates are asked to apply their knowledge of the following to make optimal decisions when working with Spark (~11%):
  - Execution deployment modes
  - Stability
  - Garbage collection
  - Out-of-memory errors
  - Storage levels
  - Repartitioning
  - Coalescing
  - Broadcasting
  - DataFrames

### Self-assessment on Spark Architecture

- This is just a list of examples of topics that could show up on your exam. There could be more.
The following statements relate to Spark’s architecture:
  - [ ] Describe the difference between a Spark driver and Spark executor.
  - [ ] Form a hierarchy of Spark jobs, tasks, stages, and applications.
  - [ ] Describe what causes data to shuffle.
  - [ ] Describe the difference between local and cluster execution modes.
  - [ ] Determine what happens to the Spark application if the driver shuts down.
  - [ ] Describe garbage collection strategies in Spark.
  - [ ] Describe the advantages and disadvantages of caching data at various storage levels.
  - [ ] Describe how DataFrames are repartitioned.

## SPARK DATAFRAME API

> **SPEND MOST OF YOUR STUDYING FOR THIS SECTION OF THE EXAM.**

- The information from the website says this will be 72% of the test, but I had about 50 questions on these types of questions.
- Really be familiar with the syntax of each method/function in the Spark API.
- The exam is really nit-picky about when to use quotes and parentheses as well as knowing the order of arguments passed into a built-in Spark API function.
- However, you will have access to a pdf of the documentation during the test as well so you can look at it for confirmation, but it’s super small and you cannot do ctrl-f to find and the document is super long, so it’s good to just be really familiar with the most commonly used functions and know how to write the correct syntax to use them.
- Ex:
  - `.withColumn()`
  - `where()`
  - `.filter()`
  - `.groupBy()`
  - `.agg().`

- As for the basics of the Spark DataFrame API, candidates will be assessed in their ability to apply the DataFrame API to complete the following tasks (~72%):
  - Subsetting DataFrames (select, filter, etc.)
  - Column manipulation (casting, creating columns, manipulating existing columns, complex column types)
  - String manipulation (Splitting strings, regular expressions)
  - Performance-based operations (repartitioning, shuffle partitions, caching)
  - Combining DataFrames (joins (inner/outer, left/right), broadcasting, unions, etc.)
  - Reading/writing DataFrames (schemas, overwriting)
  - Working with dates (extraction, formatting, etc.)
  - Aggregations
  - Miscellaneous (sorting, missing values, typed UDFs, value extraction, sampling)

### Self-assessment on Spark DataFrame API

- The following statements are related to the Spark DataFrame API:
  - Select a subset of columns from a DataFrame.
  - Filter a subset of rows from a DataFrame based on two logical filtering criteria.
  - Cast a column from a numeric type to a string type.
  - Create a new DataFrame column by mathematically combining two existing columns.
  - Split a string DataFrame column into two columns based on a regular expression.
  - Cache a DataFrame to a specific storage level.
  - Aggregate data to find the mean of a column by group.
  - Write a DataFrame to disk.
  - Extract the month from a DataFrame column of date type.
  - Create a UDF to use in a Spark SQL statement.

---

## RESOURCES

- [PySpark API documentation](https://spark.apache.org/docs/latest/api/python/pyspark.sql.html)
- What I recommend you do to study is to either install Spark using “pip install pyspark” from terminal, and run Spark on your local computer.
- If you need help, just message me and I can help you get it set up.
- You can also create a Databricks Community Edition account and run code on these free clusters, however, they’re really slow and configuring the environment is sort of a hassle.
- [Link to the Community Edition Login](https://community.cloud.databricks.com/login.html)
- Matt: An easy way to test different commands is to use Jupyter Lab.
  - Use “pip install Jupyterlab” to install in Command Prompt. 
  - Then, you can run a Jupyter notebook by entering “Jupyter Lab” in command prompt.
  - You can also use Google Colab through your google drive!

### Books

- [ ] Chapters 1-7 of Learning Spark 2nd Edition – Learning Spark 2.0
- [ ] Parts I, II, and IV of Spark The Definitive Guide Big Data Processing Made Simple

> Ordered both 05AUG22

### Repos

- [x] [Learning Spark 2.0](https://github.com/databricks/LearningSparkV2/tree/master/databricks-datasets/learning-spark-v2)
- [x] [Spark The Definitive Guide](https://github.com/databricks/Spark-The-Definitive-Guide/tree/master/data)

---

## USEFUL NOTES/THINGS TO KNOW FOR THE EXAM

- Here is a list of notes that I’ve written down in my notebook to help me ingest all of the information about the Spark architecture and DataFrame API:
  - Know each term and how they relate to each other:
    - Spark Application
    - Spark Driver
    - Spark Session
    - Spark Executor
    - Cluster Manger
    - Nodes
    - Cores
    - Partitions
  - Driver / Job / Stage / Task
  - **Transformation vs Actions** – Spark is a “lazy evaluator” meaning the engine will not perform and actual transformations on a dataframe until an action method is called.
  - Dataframes are immutable, every transformation (you can link multiple transactions in one command, this is called pipelining) creates a new dataframe.
  - **Transformations:**
    - `orderBy()`
    - `groupBy()`
    - `filter()`
    - `select()`
    - `join()`
  - **Actions:**
    - `show()`
    - `take()`
    - `count()`
    - `collect()`
    - `save()`
  - Transformations are either “Narrow dependencies” or “Wide dependencies”:
    - Narrow – single output partition can be computed by single input partition, no shuffling of data between partitions
    - filter(), select(), cast(), union()
    - Wide – data has to be shuffled across multiple partitions to get an output
    - `groupyBy()`, `orderBy()`, `agg()`, `distinct()`, `sort()`, `join()`
  - Be familiar with how the catalyst optimizer works
  - Usually 1 partition per core by default
  - For DataFrameReader and DataFrameWriter, if you use the `.format()` function, you also have to append the `.load()` or `.save()` function for the function to be invoked.
  - Know how to create a dataframe from a python list using a schema
  - `df.cache()` or `df.persist()` will cache a dataframe but it won’t actually do it until you call an action on that df.
    - The difference between `cache()` and `persist()` is that `cache(`) will cache the df to the default storage level, which is “MEMORY_AND_DISK” (meaning it’ll cache the entire data frame up until the memory limit, and if there is still some df to be cached, it’ll be written to disk, and `persist()` you can specify the storage level you wish to cache the dataframe to. Look this up in the documentation.
      - `df.unpersist()` uncaches dataframe
      - Or you can call `spark.catalog.clearCache()` to clear all dataframe caches
  - **Partitioning:** there is the `df.repartition(n)` method which allows you to re-partition your datarame into n partitions. Use this if you want to get more partitions. This is will require shuffling of the data inside your cluster.
  - There is also the `df.coalesce(n)` method that combines your df into a smaller number of partitions. This will not result in a shuffle so use this is you want to combine partitions.
  - Broadcasting dataframes came up on the test. It’s just basically Spark will broadcast a small sized dataframe to all nodes in the cluster so that there doesn’t need to be shuffling of data to do a join. There’s a config parameter you can set for spark to decide when to auto-broadcast a df when it’s joined. If the dataframe size is smaller than this threshold, Spark will broadcast the dataframe
    - You can set this by “`park.conf.set(spark.sql.autoBroadcastJoinThreshold, threshold)`
  - Know the difference between `spark.sql.shuffle.partitions` and `spark.default.parallelism`
  - [Referance](https://intellipaat.com/community/25208/what-is-the-difference-between-spark-sql-shuffle-partitions-and-spark-default-parallelism)
  - Know the execution modes (Chapter 15 in The Definitive Guide explains these pretty well):
    - Local
    - Cluster
    - Client