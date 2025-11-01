# 🗃️ **Module 8 - Databases**  

## 2️⃣ **Section 2: Relational Databases on AWS (Amazon RDS and Amazon Aurora)**

### 🟠 **Introduction**

**Relational databases** store data in structured tables that are related through primary and foreign keys.  
They use **SQL (Structured Query Language)** for defining, querying, and managing data.

AWS provides **fully managed relational database services** that automate setup, operation, and scaling — eliminating the need to manually maintain database servers.

The two primary relational database services on AWS are:
- **Amazon Relational Database Service (Amazon RDS)**  
- **Amazon Aurora** (a high-performance, cloud-native relational database engine)

---

### 🧩 **Relational Database Concepts**

| **Concept** | **Description** |
|--------------|-----------------|
| **Table** | A collection of rows and columns (similar to a spreadsheet). |
| **Primary Key** | A unique identifier for each row in a table. |
| **Foreign Key** | A reference that links one table to another. |
| **SQL** | The standard language for interacting with relational databases. |

🧠 *Example:*  
In an e-commerce app, a “Customers” table and an “Orders” table are related via a customer ID key.

---

### 💡 **Amazon Relational Database Service (RDS)**

**Amazon RDS** is a **fully managed service** for setting up, operating, and scaling relational databases in the cloud.

RDS supports multiple popular database engines:
- **Amazon Aurora**
- **PostgreSQL**
- **MySQL**
- **MariaDB**
- **Oracle**
- **Microsoft SQL Server**

---

### ⚙️ **RDS Key Features**

| **Feature** | **Description** |
|--------------|----------------|
| **Automated Provisioning** | AWS handles instance creation, OS installation, and database configuration. |
| **Automated Backups** | Daily backups, transaction logs, and user-defined retention periods. |
| **High Availability** | Multi-AZ deployments provide automatic failover between Availability Zones. |
| **Scalability** | Storage and compute can be scaled up or down with minimal downtime. |
| **Security** | Integrated with IAM, VPC, and KMS for authentication and encryption. |
| **Monitoring** | CloudWatch metrics, enhanced monitoring, and performance insights. |
| **Maintenance** | Automated software patching and updates. |

🧠 *Tip:* RDS frees developers from database administration tasks so they can focus on application logic.

---

### 🧱 **RDS Deployment Options**

| **Deployment** | **Description** | **Use Case** |
|-----------------|------------------|---------------|
| **Single-AZ** | Database instance hosted in one Availability Zone. | Development and testing environments. |
| **Multi-AZ** | Primary instance with a synchronous standby replica in another AZ for failover. | Production workloads requiring high availability. |
| **Read Replicas** | Asynchronous replicas for scaling read-heavy workloads. | Reporting and analytics workloads. |

---

### 🔐 **RDS Security**

- Databases run inside your **Amazon VPC**, isolated from other networks.  
- **Encryption at rest** using **AWS KMS** and **encryption in transit** using SSL/TLS.  
- Control access using:
  - **IAM authentication** (temporary tokens instead of passwords).  
  - **Security groups** (define inbound/outbound rules).  
  - **Database-level credentials and roles.**

🧠 *Best Practice:* Use IAM authentication and enforce SSL connections for secure access.

---

### ⚡ **Amazon Aurora**

**Amazon Aurora** is a **relational database engine** built for the cloud, fully compatible with **MySQL** and **PostgreSQL**.  
It offers the performance and availability of high-end commercial databases at a fraction of the cost.

#### 🌟 **Aurora Highlights**
- Up to **5x faster than MySQL** and **3x faster than PostgreSQL** on the same hardware.  
- Fully managed by RDS (so you get automation, backups, and monitoring).  
- Designed for **high availability** with automatic replication across **three Availability Zones**.  
- **Self-healing storage** that automatically detects and repairs corruption.  
- Automatically scales storage (up to **128 TB per database**).  
- **Serverless** option for on-demand scaling based on workload.

---

### 🧮 **Aurora Architecture**

Aurora separates **compute** and **storage layers**:
- **Compute layer:** database instances (read/write).  
- **Storage layer:** distributed, fault-tolerant storage replicated six times across three AZs.  

This separation allows for:
- Faster recovery and scaling.  
- Continuous backups to Amazon S3.  
- Low-latency reads using **Aurora Replicas** (up to 15 replicas).  

🧠 *Example:* Aurora automatically detects failures and promotes a read replica to primary within seconds.

---

### 🧰 **Aurora Deployment Options**

| **Option** | **Description** |
|-------------|----------------|
| **Aurora Provisioned** | Fixed instance capacity with manual scaling. |
| **Aurora Serverless v2** | Automatically adjusts compute capacity in fine-grained increments for variable workloads. |
| **Global Database** | Replicates data across multiple Regions with sub-second latency for global applications. |

---

### 💰 **Pricing and Cost Efficiency**

- Pay for instance hours, storage, and I/O requests.  
- Aurora’s **auto-scaling** and **serverless options** optimize cost for unpredictable workloads.  
- Use **Reserved Instances** or **Savings Plans** for predictable long-term workloads.  

---

### 🧠 **Key Takeaways**

- **Amazon RDS** automates management of relational databases, supporting multiple engines like MySQL, PostgreSQL, and Oracle.  
- **Amazon Aurora** delivers **enterprise-grade performance and availability**, built for the cloud.  
- Use **Multi-AZ deployments** for fault tolerance and **read replicas** for scaling read-heavy workloads.  
- RDS and Aurora integrate with **IAM, KMS, and VPC** for strong security.  
- **Aurora Serverless** is ideal for variable workloads — it scales automatically to meet demand.  
- Both services reduce operational burden and simplify high availability, scaling, and backups.  