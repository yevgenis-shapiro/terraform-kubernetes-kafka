![kafka](https://github.com/user-attachments/assets/6e63c064-2a32-4813-9708-4aa55e3f0b89)

## Terraform Module - Apache Kafka | 🚀🚀🚀 
Kafka is open-source distributed streaming platform, designed to handle large amounts of real-time data by providing scalable, fault-tolerant, low-latency platform for processing in real-time.

🎯 Key Features of Kafka
```
✅ High Throughput and Low Latency: Kafka is designed to handle high volumes of data with low latency. It can process millions of messages per second with latencies as low as 10 milliseconds.
✅ Fault Tolerance: Kafka achieves fault tolerance through data replication. Each partition can have multiple replicas, and Kafka ensures that data is replicated across multiple brokers. 
✅ Durability: Kafka ensures data durability by persisting data to disk. Data is stored in a log-structured format, which allows for efficient sequential reads and writes.
✅ Scalability: Kafka's distributed architecture allows it to scale horizontally by adding more brokers to the cluster. This enables Kafka to handle increasing amounts of data without downtime.
✅ Real-Time Processing: Kafka supports real-time data processing through its Streams API and ksqlDB, a streaming database that allows for SQL-like queries on streaming data.

```

🔨 Core Components:
```
1. Kafka Cluster: A Kafka cluster is a distributed system composed of multiple Kafka brokers working together to handle the storage and processing of real-time streaming data. It provides fault tolerance, scalability, and high availability for efficient data streaming and messaging in large-scale applications.
2. Brokers: Brokers are the servers that form the Kafka cluster. Each broker is responsible for receiving, storing, and serving data. They handle the read and write operations from producers and consumers. Brokers also manage the replication of data to ensure fault tolerance
3. Topics and Partitions: Data in Kafka is organized into topics, which are logical channels to which producers send data and from which consumers read data. Each topic is divided into partitions, which are the basic unit of parallelism in Kafka. Partitions allow Kafka to scale horizontally by distributing data across multiple brokers.
4. Producers: Producers are client applications that publish (write) data to Kafka topics. They send records to the appropriate topic and partition based on the partitioning strategy, which can be key-based or round-robin.
5. Consumers: Consumers are client applications that subscribe to Kafka topics and process the data. They read records from the topics and can be part of a consumer group, which allows for load balancing and fault tolerance. Each consumer in a group reads data from a unique set of partitions.
6. ZooKeeper: ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. In Kafka, ZooKeeper is used to manage and coordinate the Kafka brokers. ZooKeeper is shown as a separate component interacting with the Kafka cluster.
7. Offsets: Offsets are unique identifiers assigned to each message in a partition. Consumers will use these offsets to track their progress in consuming messages from a topic.
```

Example:
```
module "kafka" {
  source                                   = "yevgenis-shapiro/kafka/kubernetes"
  version                                  = "1.1.0"
  kafka_config = {
      metrics_enabled                      = true
      heap_size_option                     = "-Xmx1024m -Xms1024m"
      storage_class_name                   = "gp2"
      kafka_pv_volume_size                 = "10Gi"
      kafka_node_replica_count             = 2
      default_partition_per_topic          = 1
      default_replication_factor_per_topic = 1
      zookeeper_enabled                    = true
      zookeper_pv_volume_size              = "10Gi"
      zookeper_node_replica_count          = 2
      sasl_inter_broker_password           = ""
      values_yaml                          = file("./config/values.yaml")
  }
}
```
