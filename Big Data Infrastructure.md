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
lec 8

#### 2. Data Storage Layer ####
	