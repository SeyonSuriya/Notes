---
share: true
---
Big data primarily refers to data sets that are too large or complex to be dealt with by traditional data-processing application software.

Also known as Modern Data Infrastructure

*Learning Outcomes*
- Describe different components of big data infrastructure
- Map and describe open source software for each component in the infrastructure and use cases.
- Define schemas to represent data for analytics.
- Evaluate roles of a big data analytics team.
- Explain data storage/processing architectures for handling big data.
- Setup parallel computing clusters to process big data.

Why we need to Store and Process Data?
- for decision making
- to analyze trends and patterns

Relational Database
	A relational database is a collection of information that organizes data in predefined relationships where data is stored in one or more tables (or "relations") of columns and rows, making it easy to see and understand how different data structures relate to each other.

Non-Relational Database
	A non-relational database is a database that does not use the tabular schema of rows and columns found in most traditional database systems. Instead, non-relational databases use a storage model that is optimized for the specific requirements of the type of data being stored.

Type of Data
	Structured
		data that has a standardized format for efficient access by software and humans alike
	Semi-structured
		data that is not captured or formatted in conventional ways
	Unstructured
		information that doesn't reside in a traditional row-column database

Traditional Data Infrastructure
- Stores primarily tabular data
- Fixed schema
- Mostly Batch Processing

-------------------------------------------------------------------------------

Horizontal Scaling
	adding more instances of machines without changing to existing specifications. By scaling out, can share the processing power and load balancing across multiple machines.

Sharding
	Sharding is a database architecture technique used to distribute data across multiple servers or databases, called shards. Each shard contains a portion of the total data, allowing for improved performance, scalability, and manageability. Instead of storing all data in a single database, sharding divides it based on a specific criterion, such as a range of values or a hash function. This approach helps in handling large datasets and high traffic by reducing the load on a single server and enabling parallel processing across multiple shards. Sharding is commonly used in large-scale distributed systems like NoSQL databases.

Content Delivery Network (CDN)
	A Content Delivery Network (CDN) is a network of distributed servers that work together to deliver web content, such as images, videos, and webpages, to users more efficiently. The main goal of a CDN is to reduce the latency and load time by caching and serving content from servers located closer to the end-user, rather than from a central origin server. CDNs help improve website performance, enhance user experience, and reduce the load on the origin server, making them essential for websites with a global audience or high traffic.
	*A CDN enhances scalability by offloading content delivery from the origin server to distributed edge servers, allowing a website to handle more traffic without requiring additional infrastructure. This distributed approach helps accommodate large spikes in traffic, enabling seamless scalability.*

Stateless Architecture
	Stateless architecture is a design pattern where each request from a client to a server is independent, with no session information stored on the server. Each request contains all the information needed to understand and process it, making the system scalable and resilient.

*Text files are unstructured data*

Batch Processing
	a data processing method where a large volume of data is collected, processed, and outputted at once, typically at scheduled times.
Real-Time Processing
	a data processing method where data is processed immediately as it is received, providing instant or near-instant results.

Parallel Computing
	Parallel processing involves taking a large task, dividing it into several smaller tasks, and then working on each of those smaller tasks simultaneously. The goal of this divide-and-conquer approach is to complete the larger task in less time than it would have taken to do it in one large chunk.

Distributed Computing
	Distributed computing is the method of making multiple computers work together to solve a common problem. It makes a computer network appear as a powerful single computer that provides large-scale resources to deal with complex challenges.
	Advantages:
		Performance
		Scalability
		Efficiency
		High availability through resilience and redundancy
	Disadvantages:
		Complexity
		High startup cost
		Hard to debug

-------------------------------------------------------------------------------
lec 3 & 4

Challenges in Storing and Processing Data in Modern World
	highly growing data volume

### Layers of a Big Data System ###
- Analytics / Presentation Layer
- Processing Layer
- Storage Layer
- Acquisition Layer

*course gonna proceed with above topics*

#### 1. Data Acquisition Layer ####
Data Processing Systems:
OLAP - Online Analytical Processing System
	- aggregates transactional data from a storage to transform it into a feasible form for analysis.
	- As a source of data, OLAP can use some type of unified storage like a data warehouse, data lake, or data mart, or simply any place you store the historical data.
	- used for complex data analysis
OLTP - Online Transactional Processing System
	- a type of data processing that consists of executing a number of transactions occurring concurrently—online banking, shopping, order entry, or sending text messages
	- optimized for transactional processing and real-time updates
	- enables the real-time execution of large numbers of database transactions by large numbers of people, typically over the internet

Data Denormalization:
	the process of introducing some redundancy into previously normalized databases with the aim of optimizing database query performance
	-
	Dimensional Data Modeling
		a data modeling technique used in data warehousing that allows businesses to structure data to optimize analysis and reporting
		In dimensional modeling, denormalization is achieved by structuring data into fact tables and dimension tables
		-
		Star Schema
			 a multi-dimensional data model used to organize data in a database so that it is easy to understand and analyze
			 a type of relational database schema that is composed of a single, central fact table that is surrounded by dimension tables
		Snowflake Schema
			 a multi-dimensional data model that is an extension of a star schema, where dimension tables are broken down into subdimensions
			 a multi-dimensional data model that is an extension of a star schema, where dimension tables are broken down into subdimensions
		Galaxy Schema
			 The Galaxy Data Warehouse Schema, also known as a Fact Constellation Schema, acts as the next iteration of the data warehouse schema. Unlike the Star Schema and Snowflake Schema, the Galaxy Schema uses multiple fact tables connected with shared normalized dimension tables


***sir mentioned there will be a question to write a query to extract particular data from the given database structure***

4Vs of Big Data
	help organizations understand the unique challenges of big data, guiding the design of systems and strategies to effectively manage, analyze, and extract value from large, fast, diverse, and sometimes uncertain datasets
	.
	Volume:
		Refers to the vast amount of data generated every second. Big data deals with massive datasets that can range from terabytes to petabytes and beyond. The large volume of data requires scalable storage solutions and advanced processing techniques
	Velocity:
		This refers to the speed at which data is generated, processed, and analyzed. With the rise of real-time data sources, such as social media streams, IoT devices, and financial transactions, big data systems must handle data at an unprecedented speed, often in real-time or near-real-time
	Variety:
		Big data comes in various formats, including structured data (like databases), unstructured data (like text and images), and semi-structured data (like JSON or XML files). The variety of data types necessitates flexible processing techniques to analyze and extract meaningful insights
	Veracity
		This refers to the uncertainty or trustworthiness of the data. Big data often comes from multiple sources, which can vary in quality, accuracy, and reliability. Managing veracity involves ensuring data quality and consistency so that the insights derived from the data are accurate and actionable

Data Lake
	- a centralized storage repository that allows organizations to store large volumes of raw data in its native format, whether structured, semi-structured, or unstructured. 
	- Unlike traditional databases or data warehouses, which typically store data in a highly organized, structured format, a data lake can hold a vast variety of data types, such as text, images, videos, and more, without requiring predefined schemas

Data Mesh
	* a decentralized approach to managing and accessing data, designed to address the challenges of scaling data in large, complex organizations. 
	* Unlike traditional data architectures that rely on centralized data lakes or warehouses, a data mesh treats data as a product and organizes it according to domain-specific ownership, where each domain (e.g., marketing, finance) is responsible for its own data


-------------------------------------------------------------------------------
lec 5

CRUD operation - Create, Update, Delete operation

Advantages of having Staging state in OLTP / OLAP
	To avoid the stress on the OLTP system
	Data could change because of the OLTPL system is lively updating it.
	Easier to debug

CAP Theorem
	Consistency, Availability and Partition Tolerance Theorem
	Consistency -
		Every read receives the most recent write.
		the state of data in which all copies or instances are the same across all systems and databases 
	Availability - 
		Every request receives a response, even if some nodes fail.
		the system's ability to ensure that every request to access data receives a response, even if some of the data nodes fail
	Partition Tolerance -
		The system continues to operate despite network partitions.
		a distributed system continues to operate even if there are network partitions that disrupt communication between different parts of the system
	.
	According to the CAP theorem, a distributed system can only achieve two out of these three properties at the same time, but not all three.

Pub-Sub system
	publish-subscribe system is  a messaging architecture or communication pattern used in distributed systems to facilitate the exchange of messages between different components or services.
	In a pub-sub system, there are typically three main actors; publishers, subscribers, and a message broker.
	.
	Message Queues
		- Components that temporarily store messages published by producers (publishers) until they can be delivered to consumers (subscribers).
		- Message queues ensure that messages are reliably delivered, even if subscribers are temporarily unavailable, allowing the system to handle asynchronous communication and decouple producers from consumers

-------------------------------------------------------------------------------
 lec 6

Apache Kafka
	a distributed streaming platform used for building real-time data pipelines and applications. It works as a high-throughput, fault-tolerant messaging system that lets you publish, store, and process streams of records in real time.
	**Key Features:**
	- **Topics**: Kafka organizes data into topics, where producers publish messages and consumers subscribe to them.
	- **Brokers**: Kafka runs on a cluster of servers called brokers, which store and manage the data.
	- **Scalability**: Kafka is designed to handle large volumes of data across multiple machines.
	- **Fault Tolerance**: Data in Kafka is replicated across multiple brokers, ensuring reliability even if some servers fail.
	..
	**Kafka Cluster:**
		a group of interconnected Kafka brokers (servers) that work together to manage and process large streams of data. The cluster handles the distribution of data across multiple brokers, ensuring scalability, fault tolerance, and high availability.
		Key components and concepts of a Kafka cluster include:
		**1. Brokers:**
			Each broker in the cluster is a server that stores and serves data. A Kafka cluster typically consists of multiple brokers to handle large volumes of data and provide redundancy.
		**2. Topics and Partitions:**
			Data in Kafka is organized into topics, and each topic is divided into partitions. Partitions allow data to be distributed across multiple brokers, enabling parallel processing and scalability.
		**3. Replication:**
			Partitions are replicated across multiple brokers in the cluster to ensure data durability and fault tolerance. If a broker fails, replicas on other brokers can take over.
		**4. Leader and Followers:**
			Each partition has a leader broker that handles all read and write requests. The other brokers with replicas of that partition act as followers, staying in sync with the leader.
		**5. ZooKeeper:**
			(In traditional Kafka setups) ZooKeeper manages the cluster's metadata, broker configurations, leader election, and health monitoring of brokers.
		**6. Producers and Consumers:**
			Producers send (publish) data to the cluster, while consumers read (subscribe to) data from the cluster. Producers and consumers can connect to any broker in the cluster, which then routes the data to the correct partition.

-------------------------------------------------------------------------------
lec 7 - docker practical
lec 8, lec 9

#### 2. Data Storage Layer ####
Storage layer of Big Data should be scalable, fault-tolerant, secure, performant and highly available.

**HDFS (Hadoop Distributed File System)**
	HDFS is a distributed storage system that is a core component of the Hadoop ecosystem. It is designed to store large files across multiple machines in a cluster, providing high throughput access to application data and fault tolerance.
	..
	**Architecture:** 
	HDFS follows a master-slave architecture with a NameNode managing the metadata (e.g., directory structure, file permissions) and DataNodes storing the actual data blocks.
	..
	**Fault Tolerance:** 
	Data is divided into blocks and replicated across multiple DataNodes to ensure data availability in case of hardware failures.
	..
	**Scalability:** 
	HDFS can scale out horizontally by adding more DataNodes, making it capable of handling large datasets.
	..
	**High Throughput:** 
	It is optimized for streaming large files rather than low-latency data access, making it suitable for batch processing workloads.
	..
	**Limitations:** 
	Not ideal for small files, as storing metadata for numerous small files can overwhelm the NameNode. It also has higher latency compared to traditional file systems.

	HDFS is widely used in big data environments for tasks like data warehousing, ETL
	processes, and large-scale data processing.

**Components of HDFS (Hadoop Distributed File System)**
	HDFS consists of several key components that work together to provide a reliable, scalable, and distributed storage system:
	.
	1. **NameNode**:
    - The master node responsible for managing the file system’s namespace and controlling access to files by clients.
    - It maintains the metadata, including the directory structure, file permissions, and the mapping of file blocks to DataNodes.
    - It does not store the actual data but keeps track of where all the data is stored across the cluster.
    - 
	2. **DataNode**:
    - The worker nodes that store the actual data blocks of the files.
    - DataNodes are responsible for serving read and write requests from clients, as well as performing block creation, deletion, and replication based on instructions from the NameNode.
    - Data is split into blocks (typically 128 MB) and stored across multiple DataNodes.
    - 
	3. **Secondary NameNode**:
    - A helper node that periodically merges the NameNode’s in-memory metadata with the persistent metadata stored on disk, creating a new checkpoint.
    - It is not a backup for the NameNode but helps reduce the NameNode’s startup time by keeping the metadata in a more manageable state.
    - 
	4. **HDFS Client**:
    - The interface through which users interact with HDFS.
    - Clients connect to the NameNode to obtain metadata and the location of data blocks and then interact with the appropriate DataNodes to read or write data.
    - 
	5. **Block**:
    - The smallest unit of data storage in HDFS, typically 128 MB by default.
    - Each file is split into one or more blocks, which are then distributed across different DataNodes to ensure fault tolerance and parallel processing.
    - 
	6. **Replication**:
    - HDFS ensures fault tolerance by replicating each data block across multiple DataNodes.
    - The replication factor (usually 3) determines how many copies of each block are stored across the cluster.
    - 
	These components work together to make HDFS a robust, scalable, and fault-tolerant system, capable of storing and processing massive amounts of data across distributed environments.
	
-------------------------------------------------------------------------------
lec 10

#### 3. Processing Layer ####
**Role of Apache Spark, MapReduce, and HDFS in Data Processing**

1. **Apache Spark**:
    - **Role**: Spark is a fast, in-memory data processing framework that supports batch processing, stream processing, and iterative algorithms.
    - **Function**: It allows for parallel processing of data across a distributed cluster, providing high-speed data processing by keeping data in memory, which reduces the time needed to read and write to disk.
    
2. **MapReduce**:
    - **Role**: MapReduce is a programming model used for processing large data sets with a distributed algorithm.
    - **Function**: It processes data in two steps:
        - **Map**: The input data is split into smaller chunks, processed in parallel across the cluster, and converted into key-value pairs.
        - **Reduce**: These key-value pairs are then aggregated and combined to produce the final result.
    - MapReduce is integral to Hadoop for handling large-scale data processing tasks.
    
3. **HDFS (Hadoop Distributed File System)**:
    - **Role**: HDFS is the storage system that underpins Hadoop, providing a reliable and distributed way to store large data sets.
    - **Function**: It divides data into blocks, replicates these blocks across multiple DataNodes, and allows for distributed data processing by enabling data locality (processing data close to where it is stored).

**How They Work Together:**
- **HDFS** stores large datasets in a distributed manner.
- **MapReduce** or **Spark** processes this data by reading it from HDFS, performing computations, and writing the results back to HDFS.
- Spark typically offers faster performance than MapReduce by processing data in memory rather than relying heavily on disk I/O.


#### 4. Analysis Layer ####
This is the layer where data is mined for business insights.
To draw insights from the data, it pulls data from the data storage layer or directly from the data source.
The analytical layer's design needs significant consideration and preparation.

Data Warehouses vs Data Lakes

| Characteristic      | Data Warehouse                                                                                                                                    | Data Lake                                                                                                      |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------- |
| Data                | Relational data from transactional systems, operational databases, and line of business applications.                                             | All data including structured, semi-structured and unstructured                                                |
| Schema              | Often designed prior to the data warehouse implementation but also can be written at the time of analysis.<br>(schema-on-write or schema-on-read) | Written at the time of analysis (schema-on-read)                                                               |
| Price / Performance | Fastest query results using local storage                                                                                                         | Query results getting faster using low-cost storage and decoupling of compute and storage                      |
| Data Quality        | High curated data that serves as the central version of the truth                                                                                 | Any data that may or may not be curated (i.e. raw data)                                                        |
| Users               | Business analysts, data scientists, and data developers                                                                                           | Business analysts (using curated data), data scientists, data developers, data engineers, and data architects. |
| Analytics           | Batch reporting, BI, and visualizations                                                                                                           | Machine learning, exploratory analytics, data discovery, streaming, operational analytics, and profiling       |

**Different Roles**
**1. Data Analyst**
	- **Focus**: Interpreting and analyzing data to provide actionable business insights.
	- **Role**:
	    - Examines data to generate reports, visualizations, and dashboards.
	    - Uses tools like SQL, Excel, and BI platforms (e.g., Tableau, Power BI) to identify trends, patterns, and correlations.
	- **Goal**: To help organizations make data-driven decisions.

**2. Data Scientist**
	- **Focus**: Advanced data analysis, including predictive modeling, machine learning, and statistical analysis.
	- **Role**:
	    - Develops algorithms and models to predict outcomes and uncover complex patterns in data.
	    - Uses programming languages like Python, R, and tools like TensorFlow, scikit-learn for sophisticated data processing.
	- **Goal**: To solve complex data problems and create models that can forecast trends or automate decision-making.

**3. Data Engineer**
	- **Focus**: Building and maintaining the infrastructure for data collection, storage, and processing.
	- **Role**:
	    - Designs, constructs, and optimizes data pipelines, databases, and data warehouses.
	    - Works with technologies like Hadoop, Spark, SQL, and ETL (Extract, Transform, Load) tools to ensure data is accessible and reliable.
	- **Goal**: To ensure that data flows smoothly and efficiently within the organization, making it usable for analysts and scientists.

**4. Data Architect**
	- **Focus**: Designing the overarching structure of data systems within an organization.
	- **Role**:
	    - Plans and oversees the implementation of data management frameworks, databases, and data integration processes.
	    - Establishes standards, best practices, and policies for data management and security.
	- **Goal**: To create a blueprint for data infrastructure that aligns with the organization’s business needs and future growth, ensuring data is organized, secure, and scalable.

-------------------------------------------------------------------------------
lec  11

### Common Big Data Architectures ###

#### Lambda Architecture ####
Lambda Architecture is a design pattern used to handle large-scale data processing by combining both batch and real-time data processing methods. It is commonly used in big data systems to achieve scalability, fault tolerance, and low-latency processing.

**Layers of Lambda Architecture**

1. **Batch Layer**:
    - **Purpose**: Manages the processing of large volumes of historical data (or "cold data").
    - **Function**: Ingests and processes data in batches. It produces a comprehensive and accurate view of the data by running complex, resource-intensive computations.
    - **Components**: Typically involves a distributed storage system (like HDFS) and a batch processing engine (like Hadoop MapReduce or Apache Spark).
    - **Output**: Generates batch views or precomputed results that are stored and later queried.
    
2. **Speed Layer / Stream Layer**:
    - **Purpose**: Handles real-time data processing (or "hot data") to provide low-latency updates.
    - **Function**: Processes data as it arrives, allowing for quick, approximate computations that can provide immediate insights.
    - **Components**: Often uses stream processing frameworks like Apache Storm, Apache Kafka Streams, or Apache Flink.
    - **Output**: Produces real-time views that are combined with the batch layer’s output to provide a complete picture.
    
3. **Serving Layer**:
    - **Purpose**: Combines and stores the results from both the batch and speed layers, making them available for querying.
    - **Function**: Merges the batch views with real-time updates to provide a unified, queryable view of the data.
    - **Components**: Typically involves a database or key-value store optimized for fast reads, such as Apache Cassandra, HBase, or Elasticsearch.
    - **Output**: Provides the final output that can be queried by users or applications for insights.

**Key Characteristics:**
- **Scalability**: 
  By separating the batch and real-time processing, the architecture can scale to handle large amounts of data.
- **Fault Tolerance**: 
  The batch layer ensures accuracy, while the speed layer provides resilience by offering real-time data even if the batch layer is delayed.
- **Low Latency**: 
  The speed layer allows for near-instant insights by processing data as it arrives.

**How it Works:**
- Data flows into both the batch layer and speed layer simultaneously.
- The batch layer processes data in large chunks, which can take longer but produces accurate, comprehensive results.
- The speed layer processes data immediately to produce fast, albeit possibly less accurate, results.
- The serving layer then merges the outputs from both layers, ensuring that queries can access the most up-to-date and accurate data.

**Advantages of Lambda Architecture**
	.
	1. **Scalability**:
	    - **Advantage**: The architecture can handle large volumes of data by leveraging distributed processing frameworks like Hadoop and Spark in the batch layer.
	2. **Fault Tolerance**:
	    - **Advantage**: By maintaining a batch layer that processes all data, the architecture ensures that even if real-time processing fails, the system can eventually produce accurate results.
	3. **Low Latency**:
	    - **Advantage**: The speed layer allows for near-real-time data processing, providing immediate insights from fresh data, which is crucial for time-sensitive applications.
	4. **Flexibility**:
	    - **Advantage**: It supports both real-time and batch processing, making it adaptable to a wide range of use cases, from analytics to event processing.
	5. **Accuracy**:
	    - **Advantage**: The batch layer ensures that the final data output is accurate and comprehensive, correcting any inaccuracies from the speed layer's approximate computations.
	6. **Resilience**:
	    - **Advantage**: By processing data in parallel through both batch and speed layers, the system is more resilient to failures and can continue operating even if one layer encounters issues.

**Disadvantages of Lambda Architecture**
	.
	1. **Complexity**:
	    - **Disadvantage**: Managing and maintaining two parallel processing paths (batch and speed) increases system complexity, making development and operational tasks more challenging.
	2. **Data Duplication**:
	    - **Disadvantage**: Since data is processed through both the batch and speed layers, there is inherent duplication of effort and resources, which can lead to increased costs and inefficiencies.
	3. **Consistency Issues**:
	    - **Disadvantage**: Ensuring consistency between the batch and speed layers can be difficult, especially when merging results in the serving layer, potentially leading to discrepancies.
	4. **Increased Maintenance**:
	    - **Disadvantage**: The need to manage and update multiple processing frameworks and storage systems can lead to higher maintenance overhead and longer development cycles.
	5. **Latency in Batch Layer**:
	    - **Disadvantage**: While the speed layer offers low latency, the batch layer can have significant delays in processing large datasets, meaning that accurate results might not be available immediately.
	6. **Complex Query Logic**:
	    - **Disadvantage**: Querying across both batch and real-time views in the serving layer can require complex logic, which increases the difficulty of writing and optimizing queries.

#### Kappa Architecture ####
Kappa Architecture simplifies the Lambda Architecture by focusing solely on stream processing, eliminating the need for a batch layer. It treats all data as a continuous stream, making it ideal for scenarios where real-time data processing is essential.

**Layers of Kappa Architecture**
	.
	1. **Data Ingestion Layer**:
	    - **Purpose**: Collects and ingests data from various sources in real-time.
	    - **Components**: Uses message brokers or stream ingestion tools like Apache Kafka or Amazon Kinesis.
	    - **Function**: Continuously captures data from different sources, such as IoT devices, logs, transactions, or user interactions, and feeds it into the processing layer.
	      .
	2. **Stream Processing Layer**:
	    - **Purpose**: The core processing layer where real-time data processing occurs.
	    - **Components**: Utilizes stream processing engines like Apache Flink, Apache Kafka Streams, or Apache Samza.
	    - **Function**: Processes data as it arrives, performing transformations, filtering, aggregations, and other operations to generate insights or trigger actions in real-time.
	      .
	***3. **Storage Layer**:
	    - **Purpose**: Stores processed data and state information, making it accessible for queries and further analysis.
	    - **Components**: Can include NoSQL databases (e.g., Cassandra, HBase), data lakes, or scalable storage solutions like Amazon S3.
	    - **Function**: Stores the output of the stream processing layer, along with any intermediate state or aggregation results. This layer supports both real-time and historical querying.*** 
	    (Not mentioned in slide)
	      .
	4. **Serving Layer / Query Layer**:
	    - **Purpose**: Exposes the processed data to end-users or applications for querying and visualization.
	    - **Components**: Can involve APIs, dashboards, or BI tools that interact with the storage layer.
	    - **Function**: Provides real-time or near-real-time access to processed data, enabling users to run queries, generate reports, and visualize data insights.

**How it Works:**
- **Data Stream**: 
  All data is treated as a stream, whether it's real-time data or reprocessed historical data.
- **Stream Processing Engine**: 
  Tools like Apache Kafka, Apache Flink, or Apache Samza are used to process this stream in real-time.
- **Storage**: 
  Intermediate results or final outputs can be stored in a scalable, low-latency storage system like a NoSQL database or a data lake for quick access and querying.


 **Advantages of Kappa Architecture**
	.
	1. **Simplified Architecture**:
	    - Reduces complexity by eliminating the batch layer, making the system easier to develop, manage, and maintain.
	      .
	2. **Real-Time Processing**:
	    - Ensures quick insights by processing all data in real-time, suitable for applications that require immediate responses.
	      .
	3. **Unified Code Base**:
	    - Streamlines development by using a single code base for all data processing tasks, reducing redundancy.
	      .
	4. **Lower Latency**:
	    - Provides consistently low-latency processing since there's no waiting for batch jobs to complete.
	      .
	5. **Scalability**:
	    - Efficiently handles large volumes of streaming data using distributed processing frameworks.
	      .
	6. **Flexibility in Reprocessing**:
	    - Allows reprocessing of data streams from the beginning using the same logic, eliminating the need for a separate batch system.

**Disadvantages of Kappa Architecture**
	.
	1. **Limited Use Cases**:
	    - Best suited for scenarios requiring real-time processing; may not be ideal for applications needing complex batch processing.
	      .
	2. **Reprocessing Complexity**:
	    - Reprocessing large volumes of data can be resource-intensive, increasing operational costs.
	      .
	3. **Potential for Data Loss**:
	    - Ensuring no data is lost or duplicated in a pure streaming environment can be challenging.
	      .
	4. **Tooling and Ecosystem**:
	    - The ecosystem for stream processing is less mature compared to batch processing, leading to potential integration challenges.
	      .
	5. **Less Mature for Complex Analytics**:
	    - May not be as well-suited for complex, long-running analytics typically handled by batch processing systems.
	      .
	6. **State Management**:
	    - Managing state in a streaming context can be more challenging, especially for long-term aggregations.