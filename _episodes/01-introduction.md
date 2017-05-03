---
title: "Introduction"
teaching: 10
exercises: 0
questions:
- "What is Spark and what is it used for?"
objectives:
- "Understand the principles behind Spark."
- "Understand the terminology used by Spark."
keypoints:
- "Spark is a general purpose cluster computing framework."
- "Supports MapReduce but provides additional functionality."
- "Very useful for machine learning and optimization."
---
Any distributed computing framework needs to solve two problems: how to distribute data and how to distribute computation. 

One such framework is [Apache Hadoop](https://hadoop.apache.org/). Hadoop uses the *Hadoop Distributed Filesystem (HDFS)* to solve the distributed data 
problem and *MapReduce* as the programming paradigm that provides effective distributed computation.

[Apache Spark](https://spark.apache.org/) is a general purpose cluster computing framework that provides efficient in-memory computations for large data 
sets by distributing computation across multiple computers. Spark can utilize the Hadoop framework or run standalone.

Spark has a functional programming API in multiple languages that provides more operators than map and reduce, and does this via a distributed data 
framework called *resilient distributed datasets* or RDDs.

RDDs are essentially a programming abstraction that represents a read-only collection of objects that are partitioned across machines. RDDs are fault 
tolerant and are accessed via parallel operations.

Because RDDs can be cached in memory, Spark is extremely effective at iterative applications, where the data is being reused throughout the course of 
an algorithm. Most machine learning and optimization algorithms are iterative, making Spark an extremely effective tool for data science. 
Additionally, because Spark is so fast, it can be accessed in an interactive fashion via a command line prompt similar to the Python *read-eval-print
loop* (REPL).

The Spark library itself contains a lot of the application elements that have found their way into most Big Data applications including support for 
SQL-like querying of big data, machine learning and graph algorithms, and even support for live streaming data.

![Spark Stack]({{ page.root }}/fig/01-sparkstack.png "Spark Stack")

The core components of Apache Spark are:

Spark Core
: Contains the basic functionality of Spark; in particular the APIs that define RDDs and the operations and actions that can be undertaken
upon them. The rest of Spark's libraries are built on top of the RDD and Spark Core.

Spark SQL
: Provides APIs for interacting with Spark via the Apache Hive variant of SQL called Hive Query Language (HiveQL). Every database table 
is represented as an RDD and Spark SQL queries are transformed into Spark operations. For those that are familiar with Hive and HiveQL, Spark 
can act as a drop-in replacement.

Spark Streaming
: Enables the processing and manipulation of live streams of data in real time. Many streaming data libraries (such as Apache Storm) 
exist for handling real-time data. Spark Streaming enables programs to leverage this data similar to how you would interact with a normal RDD as 
data is flowing in.

MLlib
: A library of common machine learning algorithms implemented as Spark operations on RDDs. This library contains scalable learning algorithms 
like classifications, regressions, etc. that require iterative operations across large data sets. The Mahout library, formerly the Big Data machine 
learning library of choice, will move to Spark for its implementations in the future.

GraphX
: A collection of algorithms and tools for manipulating graphs and performing parallel graph operations and computations. GraphX extends 
the RDD API to include operations for manipulating graphs, creating subgraphs, or accessing all vertices in a path.

Because these components meet many Big Data requirements as well as the algorithmic and computational requirements of many data science tasks, 
Spark has been growing rapidly in popularity. Not only that, but Spark provides APIs in Scala, Java, and Python; meeting the needs for many 
different groups and allowing more data scientists to easily adopt Spark as their Big Data solution.
