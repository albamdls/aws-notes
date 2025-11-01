# 🗄️ **Module 7 - Storage**
## 1️⃣ **Section 1: AWS Storage Overview**

### 🟠 **Introduction**

Storage is one of the foundational pillars of AWS cloud computing.  
AWS provides a variety of **storage services** that differ in how data is stored, accessed, managed, and priced.  

This section introduces the main **types of storage** in AWS and when to use each one.

---

### 💾 **Storage Categories**

AWS offers **three primary types of storage**:

| **Storage Type** | **Service Examples** | **Description** | **Typical Use Cases** |
|------------------|----------------------|------------------|------------------------|
| 🧩 **Object Storage** | Amazon S3, S3 Glacier | Stores data as *objects* (files + metadata) inside buckets. Optimized for scalability and durability. | Backups, media storage, static websites, analytics, archives. |
| 💽 **Block Storage** | Amazon EBS, Instance Store | Provides raw storage volumes that behave like physical hard drives. Low-latency access, ideal for databases. | Databases, operating systems, transactional workloads. |
| 📁 **File Storage** | Amazon EFS, Amazon FSx | Offers shared file systems with standard file protocols (NFS, SMB). | Shared applications, content management, enterprise workloads. |

---

### 🧩 **Object Storage: Amazon S3**

**Amazon Simple Storage Service (Amazon S3)** is AWS’s **object storage** service designed for **99.999999999% (11 9s)** durability and virtually unlimited scalability.

**Key characteristics:**
- Stores data as objects (each containing data, metadata, and a unique key).
- Organized into **buckets**, which act as top-level containers.
- Ideal for **write-once, read-many** scenarios.
- Accessed via **HTTPS** endpoints or **SDKs/APIs**.

**Benefits:**
- Elastic scalability.
- Designed for durability and high availability.
- Integration with AWS services like Lambda, CloudFront, and Glue.
- Multiple **storage classes** for cost optimization.

🧠 *Use case examples:*  
Backups, log storage, static website hosting, data lakes, and archival.

---

### 💽 **Block Storage: Amazon EBS**

**Amazon Elastic Block Store (EBS)** provides **persistent block-level storage volumes** for use with **Amazon EC2**.

**Key characteristics:**
- Data is stored in fixed-size blocks, similar to traditional disks.
- Low-latency access for read/write operations.
- Each volume is automatically replicated within its Availability Zone.
- Volumes can be attached to or detached from EC2 instances.

**Use cases:**
- Databases and transaction processing systems.
- File systems requiring consistent performance.
- Application data that must persist independently from EC2 instances.

🧠 *EBS vs. Instance Store:*  
- **EBS:** Persistent and survives instance stops/restarts.  
- **Instance Store:** Temporary and deleted when the instance stops or terminates.

---

### 📁 **File Storage: Amazon EFS and Amazon FSx**

#### 🗂️ **Amazon Elastic File System (EFS)**
- Fully managed, scalable **NFS** file system.
- Accessible concurrently by multiple EC2 instances across multiple Availability Zones.
- Automatically grows and shrinks as files are added or removed.
- Ideal for Linux-based workloads that require shared file access.

#### 🪟 **Amazon FSx Family**
Provides managed Windows and high-performance file systems:

| Service | Description |
|----------|-------------|
| **Amazon FSx for Windows File Server** | Fully managed Windows file system supporting SMB and Active Directory integration. |
| **Amazon FSx for Lustre** | High-performance file system for compute-intensive workloads (HPC, ML). |
| **Amazon FSx for NetApp ONTAP / OpenZFS** | Enterprise file systems with advanced data management features. |

🧠 *Use case examples:*  
EFS for Linux workloads, FSx for Windows or high-performance computing.

---

### 🌐 **Accessing Storage Services**

AWS storage services can be accessed in multiple ways:

| Access Method | Example |
|----------------|----------|
| **AWS Management Console** | Use graphical interface to create and manage resources. |
| **AWS CLI / SDKs / APIs** | Programmatic access for automation and integration. |
| **Mounting / Network Protocols** | NFS for EFS, SMB for FSx, HTTPS or SDKs for S3. |
| **Hybrid Services** | Storage Gateway, DataSync, or Snow Family devices. |

---

### 🔒 **Security and Compliance**

All AWS storage services integrate with **AWS Identity and Access Management (IAM)** for authentication and authorization.  

**Security features include:**
- Encryption **at rest** (SSE-S3, SSE-KMS, EBS encryption, etc.).  
- Encryption **in transit** (TLS).  
- **Bucket policies**, **Access Control Lists (ACLs)**, and **VPC endpoints** for network isolation.  
- Compliance with major frameworks such as **ISO 27001**, **SOC 1/2/3**, **PCI-DSS**, and **HIPAA**.

---

### 🧮 **Cost Considerations**

AWS storage pricing is **pay-as-you-go** and depends on:
- Amount of data stored.
- Type of storage (S3 class, EBS volume type, FSx configuration, etc.).
- Data access frequency (hot vs. cold).
- Data retrieval and transfer costs.
- Additional features (e.g., S3 replication or lifecycle transitions).

🧠 *Tip:*  
Use **AWS Cost Explorer** and **AWS Budgets** to monitor and optimize storage costs.

---

### 🧠 **Key Takeaways**

- AWS offers **three core storage types**: **Object (S3)**, **Block (EBS)**, and **File (EFS/FSx)**.  
- Choose storage based on **performance**, **durability**, **access patterns**, and **cost**.  
- **S3** excels in scalability and durability for general-purpose storage.  
- **EBS** provides low-latency block storage for EC2 instances.  
- **EFS/FSx** offer shared file systems for Linux and Windows workloads.  
- All storage services integrate with **IAM**, **encryption**, and **CloudWatch** for security and monitoring.  
- Always apply **cost optimization** strategies using appropriate storage classes and lifecycle policies.