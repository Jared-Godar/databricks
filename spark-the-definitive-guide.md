# Spark - The Definitive Guide

## Big Data Processing Made Simple

## Spark Applications

- *Driver* process and set of *executor* processes
  - Driver runs `main()` function
  - Sits on a node in the cluster
  - Performs three functions
    - Maintaining information about the Spark Application
    - Responding to a user's function or input
    - Analyzing, distributing, and scheduling work across executors
- *Executors* are responsible for actually cattying out the work that the driver assigns them
  - Responsible for only two things
    - Executing code assigned to it by the driver
    - Reporting the state of the computation on the executor back to the driver node
- Spark employs a *cluster manager* that keeps track of the resources available
- The driver process is responsible for executing the driver program's commands across the executors to complete a given task
- Executors always run Spark code
- Drivers can be driven through a variety of languages from Spark's language API

## Spark Language APIs

- *Scala* Spark is written in Scala. Default language.
- *Java* Can write spark code in Java
- *Python* supports nearly all constructs Scala can support
- *SQL* subset of ANSI SQL 2003 standard
- *R*  Two commonly used R libraries.
  - SparkR - part of Spark core
  - SparklyR - community-driven
- Write Python/R code that Spark translates into code that can run on executor JVMs

## Spark Session

- Control your Spark Application through a driver process called the Spark Session
- SparkSession instance is the way Spark executes user-defined manipulations across the cluster
- One to one correspondence between a SparkSession and a Spark Application

## DataFrames

- A DataFrame is the most common Structured API and simply represents a table of data with rows and columns
- Defined by a *schema*
- Like a spreadsheet with named columns
- Distributed across multiple machines
  - Too large to fit on one
  - Take too long to perform computations on one machine

## Partitions

- To allow every executor to perform work in parallel, Spark breaks up data into chunks called *partitions*
- A partition is a collection of rows that sits on one maching in your cluster
- Partitions represent how data is physically districuted across clusters of machines during execution

## Transformations

- In spark, the core data structures are *immutable*
- In order to modify, *transformations* must be performed
