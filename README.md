![Kafka_Internals_004](https://github.com/user-attachments/assets/d6185adf-c6f6-432d-9d18-49107b9a102a)
## Terraform Module - Apache Kafka | 🚀🚀🚀 
Kafka is open-source distributed streaming platform, designed to handle large amounts of real-time data by providing scalable, fault-tolerant, low-latency platform for processing in real-time.

🎯 Features
```
✅ Kafka Cluster:
A Kafka cluster is a distributed system composed of multiple Kafka brokers working together to handle the storage and processing of real-time streaming data. It provides fault tolerance, scalability, and high availability for efficient data streaming and messaging in large-scale applications.
✅ Brokers:
Brokers are the servers that form the Kafka cluster. Each broker is responsible for receiving, storing, and serving data. They handle the read and write operations from producers and consumers. Brokers also manage the replication of data to ensure fault tolerance
✅ Topics and Partitions:
Data in Kafka is organized into topics, which are logical channels to which producers send data and from which consumers read data. Each topic is divided into partitions, which are the basic unit of parallelism in Kafka. Partitions allow Kafka to scale horizontally by distributing data across multiple brokers.
✅ Producers:
Producers are client applications that publish (write) data to Kafka topics. They send records to the appropriate topic and partition based on the partitioning strategy, which can be key-based or round-robin.
✅ Consumers:
Consumers are client applications that subscribe to Kafka topics and process the data. They read records from the topics and can be part of a consumer group, which allows for load balancing and fault tolerance. Each consumer in a group reads data from a unique set of partitions. 
✅ ZooKeeper:
ZooKeeper is a centralized service for maintaining configuration information, naming, providing distributed synchronization, and providing group services. In Kafka, ZooKeeper is used to manage and coordinate the Kafka brokers. ZooKeeper is shown as a separate component interacting with the Kafka cluster.
✅ Offsets:
Offsets are unique identifiers assigned to each message in a partition. Consumers will use these offsets to track their progress in consuming messages from a topic.
```

🔨 Example : Config

```

---

```
