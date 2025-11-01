# 🗄️ **Module 7 - Storage**

## 5️⃣ **Section 5: Hybrid and Data Transfer Services**

### 🟠 **Introduction**

Not all workloads begin in the cloud.  
Many organizations still store large amounts of data **on-premises** or in **edge locations**.  
AWS provides multiple services to **move, extend, or integrate** on-premises storage with the AWS Cloud — ensuring flexibility, speed, and security.

This section focuses on:
- **Hybrid storage** (integrating on-prem environments with AWS).  
- **Data migration** and **transfer services** for online and offline use cases.  

---

### 🏠 **AWS Storage Gateway**

**AWS Storage Gateway** is a **hybrid cloud storage service** that connects on-premises environments with AWS cloud storage.  
It enables seamless use of AWS storage for backup, archiving, and disaster recovery, while maintaining local performance.

#### 🔧 **Types of Gateways**

| **Type** | **Protocol** | **Backed by** | **Use Case** |
|-----------|---------------|----------------|---------------|
| **File Gateway** | NFS / SMB | Amazon S3 | Store and retrieve files as S3 objects using local cache for fast access. |
| **Volume Gateway** | iSCSI | Amazon EBS snapshots | Present block storage volumes to on-prem servers; asynchronously back up to AWS. |
| **Tape Gateway** | Virtual Tape Library (VTL) | Amazon S3 / Glacier | Replace physical tape infrastructure for cost-effective, durable cloud backups. |

#### ⚙️ **Key Features**
- **Local caching** for low-latency access.  
- **Secure, encrypted transfer** to AWS.  
- **Integration with AWS Backup** for centralized management.  
- **Compression and deduplication** to optimize bandwidth.

🧠 *Tip:* Use Storage Gateway for **hybrid workloads**, **tape replacement**, and **data replication** without changing existing applications.

---

### ❄️ **AWS Snow Family**

The **AWS Snow Family** provides **physical devices** to move or process data in environments with limited or no Internet connectivity.  
These devices are shipped to customers, filled with data, and returned to AWS for ingestion into the cloud.

#### 📦 **Snow Family Devices**

| **Device** | **Capacity** | **Use Case** |
|-------------|---------------|---------------|
| **AWS Snowcone** | Up to 8 TB (small, portable) | Edge computing, IoT, remote data collection. |
| **AWS Snowball Edge (Storage / Compute Optimized)** | 80 TB–210 TB | Large-scale data transfer or local compute in disconnected environments. |
| **AWS Snowmobile** | Up to 100 PB (semi-truck size) | Massive data migrations (e.g., entire data centers). |

#### ⚙️ **Key Features**
- **Offline data transfer** for petabyte-scale migrations.  
- **Edge compute capability** (Snowcone, Snowball Edge) using AWS IoT Greengrass or EC2-compatible instances.  
- **Ruggedized** for harsh or remote environments.  
- **Encryption** using AWS Key Management Service (KMS).

🧠 *Example:* A research vessel uses **Snowcone** to collect and process ocean data before syncing to S3 once back online.

---

### ⚡ **AWS DataSync**

**AWS DataSync** is an **online data transfer service** that simplifies, automates, and accelerates moving large amounts of data between on-premises systems and AWS storage.

#### 🔧 **Key Capabilities**
- Transfers data **10x faster** than traditional tools (e.g., rsync).  
- Supports data transfer between:
  - On-premises storage → **Amazon S3**, **EFS**, or **FSx**.  
  - AWS services → between Regions or Accounts.  
- Handles **encryption, scheduling, verification**, and **monitoring** automatically.

#### 🧰 **Use Cases**
- Cloud migration and hybrid data synchronization.  
- Data replication for analytics or backup.  
- Automated movement of data between environments.

🧠 *Tip:* Use **DataSync** when you need continuous, secure, and fast **online** data transfer at scale.

---

### 🔁 **AWS Transfer Family**

**AWS Transfer Family** provides **fully managed file transfer protocols** to move files into and out of AWS storage services.

#### ⚙️ **Supported Protocols**
- **SFTP (Secure File Transfer Protocol)**  
- **FTPS (File Transfer Protocol Secure)**  
- **FTP (File Transfer Protocol)**  

#### 💾 **Key Features**
- Fully managed — no infrastructure to deploy or manage.  
- Integrates with **Amazon S3** or **Amazon EFS** as storage backends.  
- Supports **IAM**, **CloudWatch**, and **AWS Secrets Manager** for security and monitoring.  
- Ideal for **business-to-business (B2B)** or **legacy file transfer** integrations.

🧠 *Example:* Replace on-prem SFTP servers with AWS Transfer Family to send data directly to S3.

---

### 🧭 **Choosing the Right Data Transfer Option**

| **Service** | **Transfer Type** | **Best For** | **Connectivity** |
|--------------|------------------|---------------|------------------|
| **Storage Gateway** | Hybrid (online) | Continuous integration with on-prem systems | Online |
| **DataSync** | Online | Fast, automated migration and sync jobs | Online |
| **Transfer Family** | Online | Secure file transfer via SFTP/FTP | Online |
| **Snow Family** | Offline | Large-scale data migrations or edge processing | Offline |

🧠 *Decision tip:*  
If you have **continuous, high-speed connectivity**, use **DataSync** or **Storage Gateway**.  
If you operate in **disconnected or high-latency environments**, use **Snow Family** devices.

---

### 🔒 **Security and Monitoring**

All hybrid and transfer services integrate with AWS’s security and management ecosystem:
- **Encryption in transit and at rest** (TLS, KMS).  
- **IAM roles and policies** for fine-grained access control.  
- **AWS CloudTrail** for API-level logging.  
- **Amazon CloudWatch** for real-time metrics and alerts.  
- **AWS Backup** for centralized management of hybrid backup workflows.

---

### 🧠 **Key Takeaways**

- **Hybrid storage services** bridge on-prem and cloud environments seamlessly.  
- **AWS Storage Gateway** connects existing systems to AWS using file, block, or tape interfaces.  
- **AWS Snow Family** enables **offline**, petabyte-scale transfers and **edge computing**.  
- **AWS DataSync** automates **online, high-speed** data transfers between environments.  
- **AWS Transfer Family** provides **SFTP/FTPS/FTP** endpoints for managed file transfer directly to **S3/EFS**.  
- Choose the service based on **connectivity**, **data volume**, and **migration frequency**.  
- All services integrate with **KMS, IAM, CloudWatch, and CloudTrail** for security and governance.  