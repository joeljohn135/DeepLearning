# Spark
## This file consists of everything you need to know about Spark.
### What is Spark?
Spark is a general-purpose distributed data processing engine that is suitable for use in a wide range of circumstances. It provides in-memory computing capabilities to deliver speed, a generalized execution model to support a wide variety of applications, and Java, Scala, and Python APIs for ease of development. It also supports a rich set of higher-level tools including Spark SQL for SQL and structured data processing, MLlib for machine learning, GraphX for graph processing, and Spark Streaming.
### What is the difference between Spark and Hadoop?
Spark is a data processing engine that can read and write data to various data sources. Hadoop is a distributed file system that can store data in HDFS. Spark can run on top of Hadoop and read and write data to HDFS. Spark can also run without Hadoop. Spark can read and write data to other data sources like Amazon S3, Cassandra, etc.
### What is the difference between Spark and MapReduce?
Spark is a data processing engine that can read and write data to various data sources. MapReduce is a programming model for processing large data sets with a parallel, distributed algorithm on a cluster. Spark can run on top of Hadoop and read and write data to HDFS. Spark can also run without Hadoop. Spark can read and write data to other data sources like Amazon S3, Cassandra, etc. MapReduce can only read and write data to HDFS.

### I will be using Pyspark for this documentation
### What is Pyspark?
Pyspark is the Python API for Spark. It is a Python library that can be used to interact with Spark. It is a high-level API that provides a lot of abstraction to programmers. It is easier to use than the Scala API provided by Spark. It is also easier to learn than Scala. 
### How to install Pyspark?
Pyspark is installed as part of the Spark installation. You can download Spark from the following link: https://spark.apache.org/downloads.html
or you can use the following command to install Spark on your machine:
```
pip install pyspark
```
### How to use Pyspark?
Pyspark can be used in two ways:
1. Using the Pyspark shell
2. Using a Jupyter notebook
#### Using the Pyspark shell
The Pyspark shell can be used to run Pyspark code. It can be started by running the following command:
```
pyspark
```
### How to use Pyspark in a Jupyter notebook?
Pyspark can be used in a Jupyter notebook by using the following code:
```
import findspark
findspark.init()
import pyspark
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("Spark").getOrCreate()
```
