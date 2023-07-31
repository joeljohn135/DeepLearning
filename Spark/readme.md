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
### Create a spark session
A spark session can be created by using the following code:
```
from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("Spark").getOrCreate()
```
### read a csv file
A csv file can be read by using the following code:
```
spark.read.option("header",True).csv("file.csv",inferSchema=True)
```
### read a json file
A json file can be read by using the following code:
```
spark.read.option("multiline",True).json("file.json")
```
### read a parquet file
A parquet file can be read by using the following code:
```
spark.read.parquet("file.parquet")
```
### read a text file
A text file can be read by using the following code:
```
spark.read.text("file.txt")
```
### read a xml file
A xml file can be read by using the following code:
```
spark.read.format("com.databricks.spark.xml").option("rowTag","tag").load("file.xml")
```
### read a avro file
A avro file can be read by using the following code:
```
spark.read.format("avro").load("file.avro")
```
### read a orc file
A orc file can be read by using the following code:
```
spark.read.orc("file.orc")
```
### Print schema
The schema of a dataframe can be printed by using the following code:
```
df.printSchema()
```
### print column names
The column names of a dataframe can be printed by using the following code:
```
df.columns
```
### print first n rows
The first n rows of a dataframe can be printed by using the following code:
```
df.show(n)
```
### print first n rows in a tabular format
The first n rows of a dataframe can be printed in a tabular format by using the following code:
```
df.show(n,False)
```
### select columns
The columns of a dataframe can be selected by using the following code:
```
df.select("col1","col2")
or
df.select(col1,col2).show()
```
### Other operations
Other operations that can be performed on a dataframe are:
1. describe
```
df.describe().show()
```
2. distinct
```
df.distinct().show()
```
3. drop
```
df.drop("col1","col2")
```
4. dropDuplicates
```
df.dropDuplicates().show()
```
5. dropna
```
df.dropna()
```
6. fillna
```
df.fillna(0)
```

```
df.na.drop(how="any",thresh=2,subset=["col1","col2"])
```
7. filter

8. groupBy
9. join
10. orderBy
11. selectExpr
12. union
13. rename
```
df.withColumnRenamed("col1","col2")
```
14. Drop a column
```
df.drop("col1")
```

etc.. same as pandas

### Adding a column in a dataframe
A column can be added to a dataframe by using the following code:
```
df.withColumn("col3",df.col1+df.col2)
```
### Imputer in Pyspark
Imputer can be used to fill missing values in a dataframe. It can be used by using the following code:
```
from pyspark.ml.feature import Imputer
imputer = Imputer(inputCols=["col1","col2"],outputCols=["col1","col2"])
imputer.fit(df).transform(df)
```
