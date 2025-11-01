# 🗄️ **Module 7 - Storage**

## 7️⃣ **Section 7: Security, Compliance, and Cost Optimization in Storage**

### 🟠 **Introduction**

Security and cost optimization are essential when managing data in the cloud.  
AWS provides multiple tools and services to help you **secure**, **audit**, and **optimize** storage resources while ensuring compliance with regulations and internal policies.

This section covers:
- Storage security and encryption.  
- Compliance and governance.  
- Cost optimization strategies and tools.

---

### 🔐 **Security in AWS Storage**

AWS storage services are designed with **security as a shared responsibility**:

| **AWS Responsibility** | **Customer Responsibility** |
|--------------------------|-----------------------------|
| Protect the infrastructure (hardware, software, networking, and facilities). | Configure data access, encryption, and user permissions. |

---

### 🧱 **Security Controls Across Storage Services**

| **Security Layer** | **Description** | **Example** |
|--------------------|-----------------|--------------|
| **Identity and Access Management** | Use IAM policies, roles, and permissions to control access. | Grant an IAM role `s3:GetObject` for a specific bucket. |
| **Resource Policies** | Define access at the resource level (S3 bucket, EFS, FSx). | Bucket policy denying all public access. |
| **Network Security** | Use VPC endpoints and security groups for private communication. | Access S3 via Gateway Endpoint within a VPC. |
| **Encryption** | Protect data in transit (TLS) and at rest (SSE, KMS). | Enable SSE-KMS on an S3 bucket. |
| **Monitoring and Auditing** | Track usage and configuration changes. | CloudTrail, Config, and CloudWatch integration. |

🧠 *Best Practice:* Combine **IAM policies**, **encryption**, and **network isolation** for a layered security approach.

---

### 🧩 **Encryption Options by Service**

| **Service** | **Encryption Method** | **Notes** |
|--------------|------------------------|-----------|
| **Amazon S3** | SSE-S3 (managed keys), SSE-KMS (KMS-managed), SSE-C (customer-supplied), or client-side. | SSE-KMS supports granular access and audit logs. |
| **Amazon EBS** | AWS KMS integration for volume and snapshot encryption. | Encrypted data stays encrypted through snapshots and restores. |
| **Amazon EFS** | Encryption at rest (KMS) and in transit (TLS). | Configured at file system creation. |
| **Amazon FSx** | Encryption with KMS; supports SMB signing and encryption. | Integrates with Active Directory. |
| **AWS Backup** | Vault-level KMS encryption; Vault Lock for immutability. | Ensures secure and compliant backups. |

---

### 🧮 **Monitoring and Governance Tools**

AWS offers several tools to help ensure compliance and continuous monitoring:

| **Tool** | **Purpose** |
|-----------|--------------|
| **AWS CloudTrail** | Records all API calls and user actions for auditing. |
| **AWS Config** | Tracks configuration changes and evaluates them against compliance rules. |
| **AWS CloudWatch** | Monitors metrics (usage, errors, performance). |
| **AWS Trusted Advisor** | Provides cost optimization, security, and performance recommendations. |
| **AWS Artifact** | Access on-demand compliance reports and certifications (ISO, SOC, PCI, HIPAA). |
| **AWS Organizations** | Apply policies (SCPs) and manage compliance across accounts. |

🧠 *Tip:* Use **AWS Config + CloudTrail** to enforce compliance and detect unauthorized access or misconfiguration.

---

### ⚙️ **Compliance Programs**

AWS complies with hundreds of international and industry standards.  
These certifications help customers meet their regulatory requirements while storing data in AWS.

**Examples of major AWS compliance programs:**
- **ISO 27001 / 27017 / 27018**
- **SOC 1, SOC 2, SOC 3**
- **HIPAA** (Health Insurance Portability and Accountability Act)
- **PCI DSS** (Payment Card Industry Data Security Standard)
- **FedRAMP**
- **GDPR (EU General Data Protection Regulation)**

🧠 *Customer role:* You’re responsible for **data classification**, **access control**, and **meeting specific compliance objectives** within your AWS environment.

---

### 💰 **Cost Optimization in AWS Storage**

Effective cost management ensures you only pay for what you truly need while maintaining required performance and availability.

#### 🧾 **Key Cost Drivers**
- Storage amount (GB/TB).  
- Storage class or volume type (e.g., S3 Standard vs. Glacier Deep Archive).  
- Data retrieval frequency.  
- Cross-Region replication and data transfer.  
- Requests and lifecycle operations.  

#### ⚙️ **Cost Optimization Strategies**

| **Strategy** | **Description** | **Example / Tools** |
|---------------|------------------|----------------------|
| **Choose the right storage class** | Match access frequency to the appropriate tier. | Move infrequent S3 data to IA or Glacier. |
| **Automate with lifecycle policies** | Transition or delete old data automatically. | S3 Lifecycle, EFS IA transition. |
| **Delete unused resources** | Remove unattached EBS volumes, orphaned snapshots, or test buckets. | AWS Trusted Advisor or manual review. |
| **Use Intelligent-Tiering** | Automatically move S3 data between hot/cold tiers. | S3 Intelligent-Tiering. |
| **Compress and deduplicate data** | Reduce storage footprint before upload. | DataSync or Storage Gateway deduplication. |
| **Leverage cost tools** | Analyze usage and optimize spend. | Cost Explorer, Budgets, Compute Optimizer. |

🧠 *Tip:* Always tag resources by **project**, **environment**, or **team** to track usage and assign budgets accurately.

---

### 🌍 **Data Residency and Governance**

- AWS Regions enable customers to **choose where data is physically stored**.  
- Use **S3 Replication**, **AWS Backup cross-Region copies**, or **multi-Region architectures** to meet **local data sovereignty** requirements.  
- For restricted jurisdictions, ensure data stays **in-region** by disabling cross-border replication.  

---

### 🧠 **Key Takeaways**

- AWS follows a **shared responsibility model** for storage security.  
- Protect data using **IAM**, **encryption (KMS)**, and **network isolation**.  
- Monitor and maintain compliance with **CloudTrail**, **Config**, **Artifact**, and **Trusted Advisor**.  
- Use **AWS Backup**, **Vault Lock**, and **S3 Object Lock** for data protection and retention compliance.  
- Optimize storage costs with **Intelligent-Tiering**, **lifecyc**
