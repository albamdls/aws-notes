# 🗃️ **Module 8 - Databases**  

## 3️⃣ **Section 3: Nonrelational Databases on AWS**

### 🟠 **Introduction**

Not all data fits neatly into tables with rows and columns.  
Modern applications often require more flexibility, speed, and scalability than traditional relational databases can provide.

**Nonrelational databases (NoSQL)** handle **unstructured** and **semi-structured** data, making them ideal for high-performance, distributed applications like mobile, gaming, IoT, and real-time analytics.

AWS offers several **fully managed nonrelational database services**, each designed for a specific data model and use case.

---

### 💡 **Key Characteristics of Nonrelational Databases**

- **Flexible schema** — data structure can evolve over time.  
- **Horizontal scalability** — scale out easily across multiple nodes.  
- **High performance** — optimized for millisecond or microsecond latency.  
- **Designed for modern workloads** — such as social apps, IoT telemetry, or personalized recommendations.  

---

### ⚡ **Amazon DynamoDB (Key-Value and Document Database)**

**Amazon DynamoDB** is a **serverless**, **key-value** and **document** database designed for high availability, performance, and scalability.

#### 🧩 **Core Features**
- Fully managed and serverless — no provisioning or maintenance.  
- **Single-digit millisecond latency** at any scale.  
- **Automatic scaling** — adjusts read/write capacity based on demand.  
- **Multi-Region replication** for global applications.  
- **Built-in encryption**, **backup**, and **point-in-time recovery (PITR)**.  
- Integrates with **AWS Lambda** and **API Gateway** for serverless architectures.

#### ⚙️ **Performance Options**
| **Mode** | **Description** |
|-----------|-----------------|
| **On-Demand Capacity** | Automatically scales up/down; pay per request. |
| **Provisioned Capacity** | Predefine read/write throughput; ideal for predictable workloads. |
| **DAX (DynamoDB Accelerator)** | In-memory cache delivering microsecond response times. |

🧠 *Example:* Gaming leaderboards, IoT device data, and e-commerce shopping carts use DynamoDB for rapid, scalable access.

---

### 📄 **Amazon DocumentDB (with MongoDB Compatibility)**

**Amazon DocumentDB** is a **managed document database** service compatible with **MongoDB APIs**.  
It stores data in flexible **JSON-like documents**, allowing for nested structures and varied attributes.

#### ⚙️ **Key Features**
- Schema flexibility — no predefined table structure.  
- Compatible with existing MongoDB drivers and tools.  
- **Scales storage automatically** up to 64 TB.  
- **Multi-AZ replication** for high availability.  
- **Continuous backups** to Amazon S3.  
- Integrated **encryption** and **VPC isolation**.

🧠 *Use Cases:* Content management, mobile user profiles, catalogs, and configuration data.

---

### ⚙️ **Amazon ElastiCache (In-Memory Data Store)**

**Amazon ElastiCache** accelerates application performance by storing frequently accessed data **in memory**, reducing database load and latency.

#### 🧠 **Key Features**
- Sub-millisecond response times.  
- Compatible with **Redis** and **Memcached** engines.  
- Fully managed with automated failover, patching, and backups.  
- Scales horizontally using clustering.  
- Commonly used as a **caching layer** in front of databases like RDS or DynamoDB.

🧠 *Example:* Caching API responses, session storage, gaming leaderboards, and analytics dashboards.

---

### 🕸️ **Amazon Neptune (Graph Database)**

**Amazon Neptune** is a **fully managed graph database** optimized for storing and querying relationships between data points.

#### 🧩 **Core Characteristics**
- Supports both **Property Graph** and **RDF (Resource Description Framework)** models.  
- Query languages: **Gremlin** and **SPARQL**.  
- Highly available with **Multi-AZ replication** and continuous backup to S3.  
- Fast queries for complex relationship data — billions of connections in milliseconds.  
- Fully managed with encryption, monitoring, and scaling.

#### 💡 **Common Use Cases**
- Social networks (connections, followers).  
- Fraud detection (pattern analysis).  
- Recommendation engines.  
- Knowledge graphs.

🧠 *Example:* Detecting related accounts or suspicious connections in financial transactions.

---

### 🧮 **Amazon Timestream (Time Series Database)**

**Amazon Timestream** is a **purpose-built time series database** optimized for time-stamped data.

#### ⚙️ **Key Features**
- Automatically stores and organizes data by time intervals.  
- Handles trillions of events per day.  
- Built-in analytics functions (averages, rates, interpolations).  
- Data lifecycle management — moves data automatically from memory to lower-cost storage.  
- Serverless and auto-scaling.

#### 💡 **Use Cases**
- IoT sensor data.  
- Application performance monitoring.  
- Industrial telemetry and metrics dashboards.

🧠 *Example:* Monitoring CPU utilization metrics across thousands of EC2 instances.

---

### 🔐 **Amazon QLDB (Quantum Ledger Database)**

**Amazon QLDB** is a **ledger database** that provides a transparent, immutable, and cryptographically verifiable transaction log.

#### 🧠 **Key Features**
- Records every change in an append-only journal.  
- Provides **cryptographic verification** of data integrity.  
- Fully managed and serverless.  
- Integrated with **IAM**, **KMS**, and **CloudWatch**.  
- ACID-compliant (Atomicity, Consistency, Isolation, Durability).

#### 💡 **Use Cases**
- Financial transactions and audit trails.  
- Supply chain tracking.  
- Insurance claims management.  
- Regulatory compliance systems.

🧠 *Example:* QLDB ensures every transaction is permanent and verifiable, ideal for compliance-critical environments.

---

### 📊 **Amazon Redshift (Data Warehousing)**

Although technically not a NoSQL database, **Amazon Redshift** is often used in conjunction with nonrelational systems for analytics.

#### ⚙️ **Key Features**
- Petabyte-scale **data warehouse** for **analytical queries**.  
- Uses **columnar storage** and **massively parallel processing (MPP)** for speed.  
- Integrates with **S3 (Redshift Spectrum)** to query data directly from S3 without loading.  
- Integrates with BI tools like QuickSight, Tableau, and Looker.  
- **Elastic Resize** and **Concurrency Scaling** for performance optimization.

🧠 *Use Cases:* Business intelligence, analytics, and reporting across large datasets.

---

### 🧠 **Key Takeaways**

- **Nonrelational databases** handle **unstructured or semi-structured** data with flexible schemas and scalable performance.  
- **DynamoDB** → Key-value & document workloads; serverless and high performance.  
- **DocumentDB** → JSON document model; compatible with MongoDB.  
- **ElastiCache** → In-memory caching; microsecond latency for speed-critical workloads.  
- **Neptune** → Graph database for connected data (social, fraud, recommendations).  
- **Timestream** → Time series workloads; IoT and telemetry.  
- **QLDB** → Immutable ledger for auditing and traceability.  
- **Redshift** → Analytical workloads and large-scale data warehousing.  
- AWS databases are **purpose-built** — use the right one for the right job.  
