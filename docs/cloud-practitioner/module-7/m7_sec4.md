# 🗄️ **Module 7 - Storage**

## 4️⃣ **Section 4: File Storage – Amazon EFS and Amazon FSx**

### 🟠 **Introduction**

While object and block storage are excellent for many workloads, some applications require **shared access** to files using standard file system protocols.  
AWS provides fully managed **file storage services** that deliver scalability, availability, and performance for both Linux and Windows workloads.

The two primary services are:
- **Amazon Elastic File System (Amazon EFS)** – NFS-based, serverless file storage for Linux workloads.  
- **Amazon FSx** – Managed file systems built on popular enterprise technologies like Windows File Server, Lustre, and NetApp ONTAP.

---

### 📁 **Amazon Elastic File System (EFS)**

**Amazon EFS** provides **scalable, elastic, NFS-based file storage** that can be shared across multiple EC2 instances and Availability Zones.

#### ⚙️ **Core Characteristics**
- **Fully managed** — no provisioning or capacity planning.  
- **Elastic** — automatically grows and shrinks as you add or remove files.  
- **Accessible across multiple AZs** in a Region.  
- **POSIX-compliant**, ideal for Linux-based applications.  
- Provides **low-latency** file access with **high availability**.

#### 🧩 **Architecture Overview**
EFS stores data redundantly across multiple Availability Zones, providing high durability.  
Each instance mounts the same file system using a standard **NFS (Network File System)** protocol.

---

### ⚙️ **EFS Performance and Storage Classes**

EFS offers performance and storage options to balance cost and speed.

| **Mode / Class** | **Description** | **Use Case** |
|------------------|------------------|---------------|
| **Performance Modes** |  |  |
| General Purpose | Default mode for most workloads. | Web servers, CMS, development environments. |
| Max I/O | Optimized for highly parallel workloads. | Big data analytics, HPC, media processing. |
| **Throughput Modes** |  |  |
| Bursting | Automatically scales throughput based on file size. | General-purpose workloads. |
| Provisioned | Set fixed throughput independent of storage size. | Workloads needing consistent throughput. |
| Elastic | Automatically adjusts throughput for unpredictable workloads. | Dynamic applications. |
| **Storage Classes** |  |  |
| EFS Standard | Multi-AZ, high-performance storage. | Frequently accessed data. |
| EFS Infrequent Access (IA) | Lower-cost tier for less frequently used files. | Backups, archived data. |

🧠 *Tip:* You can use **EFS Lifecycle Management** to automatically move files to **IA storage** after a set period of inactivity.

---

### 🔐 **Security in EFS**

- **IAM policies** and **resource-based permissions** control access.  
- **VPC security groups** and **network ACLs** restrict traffic.  
- **Encryption at rest** using AWS KMS.  
- **Encryption in transit** using TLS.  
- Integration with **AWS Backup** for automated backups.

🧠 *Best Practice:* Combine **IAM + NFS permissions** for layered security.

---

### 💰 **EFS Cost Optimization**

- Pay only for the **storage used** (no minimums).  
- Save up to **90%** with **EFS Infrequent Access (IA)**.  
- Enable **Lifecycle Policies** to transition inactive files automatically.  
- Use **Access Points** to simplify multi-application management.

---

### 🪟 **Amazon FSx Family**

AWS FSx provides **fully managed file systems** built on **popular enterprise and HPC technologies**.  
Each FSx service is optimized for a specific workload or platform.

| **Service** | **Description** | **Ideal For** |
|--------------|------------------|----------------|
| **Amazon FSx for Windows File Server** | Native Windows file system using **SMB** protocol and integrated with **Microsoft Active Directory**. Supports user quotas, shadow copies, and DFS namespaces. | Windows applications, home directories, lift-and-shift migrations. |
| **Amazon FSx for Lustre** | High-performance, POSIX-compliant file system for compute-intensive workloads. Can link directly to Amazon S3 buckets for fast data access. | Machine learning, financial modeling, big data, media processing. |
| **Amazon FSx for NetApp ONTAP** | Enterprise-grade file system supporting **multi-protocol (NFS, SMB, iSCSI)**, cloning, snapshots, and tiering to S3. | Enterprise workloads needing advanced storage management. |
| **Amazon FSx for OpenZFS** | Open-source file system offering low-latency performance and snapshot capabilities. | Low-latency, Linux workloads, and open-source environments. |

---

### 🔐 **Security and Integration in FSx**

**Amazon FSx** integrates with several AWS services for security and management:

- **Active Directory (AD)** integration for access control.  
- **IAM** and **AWS Key Management Service (KMS)** for encryption and access policies.  
- **VPC** integration for secure network isolation.  
- **AWS Backup** support for centralized backups.  
- **Monitoring** with CloudWatch for file system metrics.  

🧠 *Tip:* Choose FSx based on your existing environment — Windows, Linux, HPC, or enterprise data management.

---

### 🧠 **Comparing EFS and FSx**

| **Feature** | **Amazon EFS** | **Amazon FSx** |
|--------------|----------------|----------------|
| **Protocol** | NFS | SMB, NFS, Lustre, iSCSI (depends on FSx type) |
| **OS Compatibility** | Linux | Windows and Linux (depending on variant) |
| **Scalability** | Automatically scales | Fixed or provisioned based on service |
| **Use Cases** | Shared Linux workloads, container storage, web apps | Windows apps, HPC, analytics, enterprise workloads |
| **Cost Optimization** | Lifecycle management, IA tiering | Tiering to S3 (FSx ONTAP, FSx Lustre) |
| **Availability** | Multi-AZ | Varies (Multi-AZ or single-AZ options) |

---

### 🧠 **Key Takeaways**

- **Amazon EFS** provides **elastic, NFS-based file storage** for Linux workloads — automatically scales, multi-AZ, and pay-for-what-you-use.  
- **Amazon FSx** offers **managed file systems** built on **Windows File Server, Lustre, NetApp ONTAP, and OpenZFS**.  
- Use **EFS** for Linux web apps, analytics, and content sharing.  
- Use **FSx** for Windows, HPC, or enterprise file workloads.  
- Both integrate with **IAM**, **KMS**, **VPC**, and **AWS Backup** for security and data protection.  
- Apply **lifecycle policies** or **tiering to S3** to reduce storage costs.  