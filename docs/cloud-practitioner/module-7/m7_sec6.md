# 🗄️ **Module 7 - Storage**

## 6️⃣ **Section 6: Backup, Archive, and Data Protection**

### 🟠 **Introduction**

Data protection is critical to maintaining business continuity, compliance, and security.  
AWS offers several services to help customers **back up**, **archive**, and **protect** their data automatically — across Regions and storage classes.

This section covers:
- **AWS Backup**
- **Amazon S3 Object Lock**
- **Data archiving options (S3 Glacier classes)**
- **Disaster recovery and replication strategies**

---

### 💾 **AWS Backup**

**AWS Backup** is a **fully managed, centralized backup service** that automates and manages data protection across AWS services and on-premises environments.

#### ⚙️ **Key Capabilities**
- **Automated backups** of supported AWS services:
  - EBS, EFS, FSx, RDS, DynamoDB, EC2, Aurora, and Storage Gateway.  
- **Centralized backup policies** for compliance and governance.  
- **Cross-Region and cross-account backup copies** for disaster recovery.  
- **Lifecycle policies** to move older backups to **cold storage tiers** automatically.  
- **Integration** with **AWS Organizations** for multi-account management.  
- **Point-in-time restore (PITR)** for supported services.

#### 🧰 **How It Works**
1. Define a **backup plan** (frequency, retention, lifecycle).  
2. Assign **resources** (EC2, EFS, RDS, DynamoDB, etc.).  
3. AWS Backup executes backups and stores them in **Backup Vaults**.  
4. Optionally, enable **Vault Lock** for compliance enforcement.

🧠 *Example:* Back up all EBS and RDS volumes nightly, with 30-day retention and cross-Region replication.

---

### 🔒 **AWS Backup Vaults and Vault Lock**

**Backup Vaults** are logical containers where AWS Backup stores recovery points.  
Each vault:
- Is encrypted with **AWS KMS**.  
- Supports **resource tagging** for cost and organization.  
- Can enforce **access policies** using IAM.

**Vault Lock** enables **WORM (Write Once, Read Many)** protection for immutable backups.  
Once set, Vault Lock prevents deletion or modification of backups before their retention period expires — critical for regulatory compliance (e.g., financial, healthcare data).

---

### 🧊 **Archiving with Amazon S3 Glacier**

AWS provides multiple **S3 Glacier storage classes** designed for long-term archival and compliance storage.

| **Storage Class** | **Retrieval Time** | **Cost** | **Use Case** |
|--------------------|--------------------|-----------|----------------|
| **S3 Glacier Instant Retrieval** | Milliseconds | Low | Archival data that must be accessed quickly. |
| **S3 Glacier Flexible Retrieval** | Minutes–hours | Lower | Data rarely accessed but occasionally needed. |
| **S3 Glacier Deep Archive** | 12–48 hours | Lowest | Long-term retention, compliance, or historical archives. |

#### 💡 **Key Benefits**
- 11 9s durability across multiple AZs.  
- Lifecycle integration — automatically move aging data from S3 Standard or IA to Glacier.  
- Encryption at rest and in transit.  
- Ideal for **regulatory**, **scientific**, and **media archive** workloads.

---

### 🧱 **S3 Object Lock**

**Amazon S3 Object Lock** provides **immutability** at the object level.  
It prevents objects from being deleted or overwritten for a fixed retention period or indefinitely.

#### 🔧 **Modes**
| **Mode** | **Description** |
|-----------|----------------|
| **Governance Mode** | Users can’t overwrite or delete objects unless they have special permissions. |
| **Compliance Mode** | No one (including the root user) can delete or modify the object until retention expires. |

#### 🧰 **Use Cases**
- Legal holds and audit compliance.  
- Protection against ransomware or accidental deletions.  
- Meeting regulatory requirements (e.g., SEC Rule 17a-4, HIPAA).  

🧠 *Tip:* Combine Object Lock with **S3 Versioning** for complete data protection and rollback capability.

---

### 🌍 **Disaster Recovery and Replication**

AWS provides several built-in features and strategies for **disaster recovery (DR)**:

| **Strategy** | **Description** | **Recovery Time Objective (RTO)** | **Example Service** |
|---------------|------------------|----------------------------------|---------------------|
| **Backup and Restore** | Store backups in another Region and restore when needed. | Hours–Days | AWS Backup with cross-Region copy. |
| **Pilot Light** | Keep minimal core infrastructure always running. | Minutes–Hours | Replicate databases with RDS or DynamoDB global tables. |
| **Warm Standby** | Keep scaled-down full environment active. | Minutes | Auto Scaling to scale up when needed. |
| **Multi-Site (Active/Active)** | Fully redundant environment across Regions. | Seconds | Route 53 with Global Accelerator or cross-Region load balancing. |

#### 💡 **Replication Tools**
- **S3 Cross-Region Replication (CRR)**  
- **EBS Snapshot Copy**  
- **RDS Read Replicas / Cross-Region Replicas**  
- **DynamoDB Global Tables**

🧠 *Tip:* Use multiple strategies depending on workload criticality — e.g., CRR for S3 data and Pilot Light for EC2 infrastructure.

---

### 🔐 **Data Encryption and Compliance**

AWS ensures protection of stored and backed-up data using **encryption**, **access control**, and **auditing**:

- **Encryption at rest** using **AWS KMS**, **SSE-S3**, or **SSE-KMS**.  
- **Encryption in transit** using **TLS/SSL**.  
- **IAM** for fine-grained access control.  
- **CloudTrail** to audit backup operations and API calls.  
- **AWS Config** to monitor compliance with internal data protection policies.  

---

### 🧠 **Key Takeaways**

- **AWS Backup** provides a **centralized, automated** backup solution for AWS and hybrid workloads.  
- **Backup Vaults** and **Vault Lock** enforce **immutability** and compliance retention.  
- Use **S3 Glacier classes** for **long-term, low-cost** archival storage.  
- **S3 Object Lock** ensures **WORM protection** for compliance and ransomware defense.  
- Implement **DR strategies** (Backup & Restore, Pilot Light, Warm Standby, Multi-Site) based on recovery time goals.  
- Use **encryption, IAM, and CloudTrail** to secure and audit backup operations.  