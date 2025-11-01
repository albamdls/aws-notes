# 🗄️ **Module 7 - Storage**

## 3️⃣ **Section 3: Amazon Elastic Block Store (Amazon EBS) and Instance Store**

### 🟠 **Introduction**

Applications running on **Amazon EC2** instances often require low-latency, high-performance, and persistent storage.  
AWS provides two main block storage options for EC2 instances:

- **Amazon Elastic Block Store (EBS)** – Persistent, durable block storage that remains even after an instance is stopped or terminated.  
- **Instance Store** – Temporary, physically attached storage that is deleted when the instance stops or terminates.

---

### 💽 **Amazon Elastic Block Store (EBS)**

**Amazon EBS** provides **persistent block-level storage volumes** for EC2 instances.  
Each volume is automatically replicated within its Availability Zone to protect against hardware failure.

EBS volumes behave like raw, unformatted block devices that you can format and mount as file systems or use for databases and applications.

---

### ⚙️ **EBS Volume Features**

| **Feature** | **Description** |
|--------------|-----------------|
| **Durability** | Data is automatically replicated within an Availability Zone. |
| **Persistence** | EBS volumes persist independently from EC2 instances. |
| **Performance** | Supports different volume types for various IOPS and throughput needs. |
| **Scalability** | Volumes can be dynamically resized or reconfigured. |
| **Backup** | Snapshots can be created and stored in Amazon S3. |
| **Encryption** | Supports encryption at rest using AWS KMS, and encryption in transit. |

---

### 🧮 **EBS Volume Types**

AWS offers several EBS volume types optimized for **performance** and **cost**:

| **Type** | **Category** | **Use Case** | **Performance** |
|-----------|---------------|--------------|-----------------|
| **gp3** | General Purpose SSD | Default for most workloads; balance of price and performance. | Baseline: 3,000 IOPS (independent of volume size). |
| **gp2** | General Purpose SSD (legacy) | Boot volumes, small databases, dev/test environments. | Performance scales with volume size (3 IOPS/GB). |
| **io2 / io2 Block Express** | Provisioned IOPS SSD | Critical databases or workloads requiring sustained IOPS. | Up to 256,000 IOPS and single-digit millisecond latency. |
| **st1** | Throughput Optimized HDD | Big data, data warehouses, and log processing. | High throughput, lower cost; not for random I/O. |
| **sc1** | Cold HDD | Infrequently accessed data with lowest cost. | Lowest performance; sequential I/O workloads only. |

🧠 *Tip:* For most general workloads, **gp3** is the recommended default volume type.

---

### 📦 **EBS Snapshots**

**Snapshots** provide point-in-time backups of EBS volumes, stored in **Amazon S3**.

- Incremental: only changed blocks are saved, reducing time and cost.  
- Can be used to:
  - Create new volumes.  
  - Restore data after failure.  
  - Copy to another Region for disaster recovery.  
- Support **Fast Snapshot Restore (FSR)** for faster initialization.

🧠 *Example:* Use snapshots for backup automation or as golden images for deployment pipelines.

---

### 🔄 **Elastic Volumes**

EBS allows you to modify volume characteristics **without downtime**:
- Increase volume size.
- Change type (e.g., gp2 → gp3).
- Adjust performance (IOPS, throughput).

This enables real-time optimization of storage performance and cost.

---

### 🔐 **EBS Encryption**

EBS integrates with **AWS Key Management Service (KMS)** to provide encryption capabilities.

**Encryption benefits:**
- Protects data at rest, in transit, and in snapshots.  
- Automatically encrypts data moving between volume and instance.  
- Snapshots of encrypted volumes are automatically encrypted.  
- Copying encrypted snapshots retains encryption.  

You can also use **customer-managed keys (CMKs)** for tighter security control.

---

### ⚡ **Performance and Monitoring**

EBS performance depends on:
- **Volume type and size**
- **Instance type and network bandwidth**
- **Queue depth** (number of I/O operations in progress)

Use **Amazon CloudWatch metrics** to monitor:
- Volume read/write IOPS  
- Throughput  
- Latency  
- Burst balance metrics  

🧠 *Tip:* Use **EBS-optimized instances** to ensure dedicated bandwidth for storage traffic.

---

### 🧩 **Instance Store (Ephemeral Storage)**

**Instance Store** provides **temporary block-level storage** physically attached to the EC2 host machine.

**Characteristics:**
- Very high I/O performance (because it’s local).  
- Data is **lost** when the instance stops, hibernates, or terminates.  
- Cannot be detached or backed up.  
- No redundancy (hardware failure means data loss).  
- Available only for certain instance types (e.g., i3, d2, h1, etc.).

**Use cases:**
- Temporary caches or buffers.  
- Scratch data or intermediate processing.  
- Replicated, stateless architectures where data loss is acceptable.

🧠 *Best Practice:* Never store critical data on Instance Store without replication or backup.

---

### 🧠 **Key Takeaways**

- **Amazon EBS** provides **persistent**, durable, and flexible block storage for EC2 instances.  
- Choose the right **volume type** based on performance (IOPS, throughput) and cost requirements.  
- **Snapshots** and **encryption** (via KMS) ensure data protection and compliance.  
- **Elastic Volumes** allow dynamic scaling without downtime.  
- **Instance Store** offers **temporary**, high-performance storage — ideal for caches or transient workloads.  
- Monitor performance using **CloudWatch** and use **EBS-optimized** instances for consistent throughput.  
