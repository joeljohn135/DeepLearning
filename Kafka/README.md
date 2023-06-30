Note: Apache Kafka is suitable for Linux mainly services provided by confluent might be tricky its better to use a VM on windows and install kafka on it.

However if you want to install kafka on windows follow the below steps: [Click here](# Installation of Apache Kafka on Windows)
# Installation of Apache Kafka on Linux
## Prerequisites
- Java 8 or higher
- Zookeeper
## Installation
### Download Apache Kafka
Download the latest version of Apache Kafka from the official website: https://kafka.apache.org/downloads
### Extract the archive
Extract the archive to the desired location. In this example, the archive is extracted to the /opt directory.
```
tar -xzf kafka_2.12-2.3.0.tgz -C /opt
```
### Start Zookeeper
Start Zookeeper using the following command:
```
bin/zookeeper-server-start.sh config/zookeeper.properties
```
### Start Kafka
Start Kafka using the following command:
```
bin/kafka-server-start.sh config/server.properties
```
### Create a topic
Create a topic named "test" with a single partition and only one replica:
```
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1 --topic test
```
### Send some messages
Run the producer and then type a few messages into the console to send to the server.
```
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test
```
### Start a consumer
Kafka also has a command line consumer that will dump out messages to standard output.
```
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test --from-beginning
```
### Start a multi-broker cluster
In addition to ZooKeeper, you need to have a separate Kafka server instance running on each machine that is part of the cluster.
```
bin/kafka-server-start.sh config/server.properties
```
### Create a new topic
Create a new topic named "test2" with a replication factor of three:
```
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 3 --partitions 1 --topic test2
```
### List all topics
List all available topics:
```
bin/kafka-topics.sh --list --bootstrap-server localhost:9092
```
### Describe a topic
Describe the topic "test2":
```
bin/kafka-topics.sh --describe --bootstrap-server localhost:9092 --topic test2
```
### Delete a topic
Delete the topic "test2":
```
bin/kafka-topics.sh --delete --bootstrap-server localhost:9092 --topic test2
```
### Alter a topic
Increase the number of partitions of the topic "test2" to 5:
```
bin/kafka-topics.sh --alter --bootstrap-server localhost:9092 --topic test2 --partitions 5
```
### Send messages to a topic
Send some messages to the topic "test2":
```
bin/kafka-console-producer.sh --broker-list localhost:9092 --topic test2
```
### Consume messages from a topic
Consume messages from the topic "test2":
```
bin/kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic test2 --from-beginning
```
### Delete records from a topic
Delete all messages from the topic "test2" before the given offset:
```
bin/kafka-delete-records.sh --bootstrap-server localhost:9092 --topic test2 --offset-json-file delete.json
```
### Stop Kafka
Stop Kafka using the following command:
```
bin/kafka-server-stop.sh
```
### Stop Zookeeper
Stop Zookeeper using the following command:
```
bin/zookeeper-server-stop.sh
```
### Remove Kafka
Remove Kafka using the following command:
```
rm -rf /opt/kafka_2.12-2.3.0
```
### Remove Zookeeper
Remove Zookeeper using the following command:
```
rm -rf /opt/zookeeper-3.5.5
```
# Installation of Apache Kafka on Windows
## Prerequisites
- Java 8 or higher
- Zookeeper
## Installation
### Download Apache Kafka
Download the latest version of Apache Kafka from the official website: https://kafka.apache.org/downloads
### Extract the archive
Extract the archive to the desired location. In this example, the archive is extracted to the C:\kafka_2.12-2.3.0 directory.
### Add Kafka to the PATH environment variable
Add the C:\kafka_2.12-2.3.0\bin directory to the PATH environment variable.
### Edit the server.properties file
Edit the C:\kafka_2.12-2.3.0\config\server.properties file and set the following properties:
```
log.dirs=[Kafka folder path ]/kafka-logs   # Directory where the kafka folder is kept. eg log.dirs=C:/Kafka/kafka_2.12-2.3.0/kafka-logs
```
### Do the same for zookeeper.properties file
Edit the C:\kafka_2.12-2.3.0\config\zookeeper.properties file and set the following properties:
```
eg : dataDir=C:/Kafka/kafka_2.12-2.3.0/zookeeper
```
### Start Zookeeper
Start Zookeeper using the following command:
```
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
```
### Start Kafka
Start Kafka using the following command:
```
.\bin\windows\kafka-server-start.bat .\config\server.properties
```
### Create a topic
Create a topic named "test" with a single partition and only one replica:
```
.\bin\windows\kafka-topics.bat --create --bootstrap-server localhost:9092 --topic test
```
### Producer(open another terminal)
Run the producer and then type a few messages into the console to send to the server.
```
.\bin\windows\kafka-console-producer.bat --broker-list localhost:9092 --topic test
```
### Start a consumer(open another terminal)
Kafka also has a command line consumer that will dump out messages to standard output.
```
.\bin\windows\kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test 
``` 
