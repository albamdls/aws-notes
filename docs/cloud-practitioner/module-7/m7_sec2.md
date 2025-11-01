# 🗄️ **Module 7 - Storage**

## 2️⃣ **Section 2: Amazon Simple Storage Service (Amazon S3)**

### 🟠 **Introduction**

**Amazon Simple Storage Service (Amazon S3)** is an **object storage service** designed for **infinite scalability, high availability, and 11 9s (99.999999999%) durability**.  
It allows you to store and retrieve any amount of data from anywhere on the web.

S3 is the foundation of AWS’s storage ecosystem — used for **data lakes, backups, websites, analytics, archives, and more**.

---

### 📦 **Core Concepts**

| Concept | Description |
|----------|--------------|
| **Bucket** | The top-level container for storing objects. Each bucket has a globally unique name and resides in a specific AWS Region. |
| **Object** | The fundamental storage entity, composed of data, metadata, and a unique key (object name). |
| **Key** | The unique identifier for an object within a bucket. |
| **Region** | Determines where your data is physically stored (affects latency, cost, and compliance). |
| **Prefix** | A logical grouping used to organize and retrieve objects efficiently. |
| **Metadata** | Descriptive information about an object (e.g., content type, encoding, owner, custom tags). |

🧠 *Tip:* You can store **virtually unlimited objects** in S3 — each up to **5 TB** in size.

---

### 💡 **Why Use Amazon S3**

- Designed for **durability, scalability, and performance**.  
- **Serverless** — no infrastructure to manage.  
- Accessed via **HTTP(S)**, **AWS CLI**, **SDKs**, or **REST APIs**.  
- Integrates seamlessly with other AWS services:
  - **AWS Lambda** for event-driven automation.
  - **CloudFront** for content delivery.
  - **AWS Glue / Athena** for analytics.
  - **Amazon Macie** for sensitive data discovery.

---

### 🧩 **S3 Storage Classes**

Each S3 storage class is optimized for a different access pattern and cost profile.

| **Storage Class** | **Designed For** | **Availability** | **Durability** | **Retrieval Time** | **Use Cases** |
|--------------------|------------------|------------------|----------------|--------------------|----------------|
| **S3 Standard** | Frequently accessed data | 99.99% | 99.999999999% | Immediate | Active data, websites, mobile apps |
| **S3 Intelligent-Tiering** | Unknown or variable access patterns | 99.9% | 99.999999999% | Immediate | Unpredictable workloads |
| **S3 Standard-IA (Infrequent Access)** | Infrequently accessed data | 99.9% | 99.999999999% | Immediate | Long-term storage, backups |
| **S3 One Zone-IA** | Infrequent access, single-AZ | 99.5% | 99.999999999% | Immediate | Secondary backups, easily recreated data |
| **S3 Glacier Instant Retrieval** | Archive data with immediate access | 99.9% | 99.999999999% | Milliseconds | Archival with occasional queries |
| **S3 Glacier Flexible Retrieval** | Archive data, retrieval in minutes–hours | 99.9% | 99.999999999% | Minutes to hours | Compliance archives, large datasets |
| **S3 Glacier Deep Archive** | Long-term archival | 99.9% | 99.999999999% | Hours (12–48h) | Cold data, legal or historical archives |

🧠 *Tip:* **Intelligent-Tiering** automatically moves objects between access tiers, optimizing costs without manual effort.

---

### 🔁 **S3 Lifecycle Management**

**Lifecycle rules** allow you to automate transitions between storage classes or delete objects after a defined time.

Example workflow:
1. Store new data in **S3 Standard**.
2. After 30 days, transition to **Standard-IA**.
3. After 90 days, move to **Glacier Deep Archive**.
4. After 365 days, automatically delete the object.

Lifecycle configurations are **policy-based**, defined at the **bucket** or **prefix** level.

---

### 🌍 **Replication**

Amazon S3 supports **automatic object replication** across buckets for redundancy, compliance, and latency optimization.

| Type | Description | Typical Use Case |
|------|--------------|------------------|
| **Same-Region Replication (SRR)** | Copies objects between buckets in the same AWS Region. | Backup, log aggregation, data redundancy. |
| **Cross-Region Replication (CRR)** | Copies objects across different Regions automatically. | Disaster recovery, compliance, latency reduction. |

Replication can include **metadata**, **ACLs**, and optionally **delete markers**.  
You can filter which objects to replicate using prefix or tag-based rules.

---

### 🧮 **Versioning**

- Enables multiple versions of an object within a bucket.  
- Protects against accidental deletions and overwrites.  
- Works seamlessly with replication and lifecycle policies.  
- Each version is uniquely identified and can be restored at any time.

> ⚠️ Note: Enabling versioning increases storage costs because multiple copies are stored.

---

### 🧰 **S3 Event Notifications**

S3 can trigger events in response to object-level operations (e.g., PUT, DELETE, COPY).

You can configure notifications to:
- **Amazon SNS** → Send alerts or fan-out messages.  
- **Amazon SQS** → Queue for processing.  
- **AWS Lambda** → Run code automatically when an event occurs.  

🧠 *Example:* Trigger an image-resizing Lambda function whenever a new file is uploaded.

---

### 🔐 **Security and Access Control**

Security in S3 is managed at multiple levels:

#### **1. IAM Policies**
- Define permissions for users, groups, or roles.  
- Specify allowed actions (e.g., `s3:GetObject`, `s3:PutObject`).  

#### **2. Bucket Policies**
- Resource-based policies attached directly to a bucket.  
- Control access for external accounts or applications.

#### **3. Access Control Lists (ACLs)**
- Legacy method for granting fine-grained access to individual objects or buckets.  
- Best practice: use IAM or bucket policies instead.

#### **4. Block Public Access**
- Global setting that prevents accidental public exposure of buckets or objects.

#### **5. Encryption**
| Type | Description |
|-------|-------------|
| **SSE-S3** | Server-side encryption with AWS-managed keys. |
| **SSE-KMS** | Encryption using AWS Key Management Service (KMS). |
| **SSE-C** | Customer-managed encryption keys. |
| **Client-side encryption** | Encryption done before data upload. |

---

### 📊 **Monitoring and Logging**

- **Amazon CloudWatch Metrics:** Monitor bucket-level metrics such as request count, latency, and errors.  
- **S3 Server Access Logging:** Tracks access requests for audit and analysis.  
- **AWS CloudTrail:** Logs all API calls to detect unauthorized activity.  
- **S3 Storage Lens:** Provides organization-wide insights into storage usage and activity trends.

🧠 *Tip:* Combine S3 Storage Lens with Cost Explorer to track usage and optimize storage efficiency.

---

### 💰 **Cost Factors**

Your total S3 cost depends on:
- **Storage class** (Standard vs. Glacier).  
- **Number of requests** (PUT, GET, COPY, DELETE).  
- **Data transfer out** to the Internet or other Regions.  
- **Lifecycle transitions** and **replication** traffic.  
- **Data retrieval** for infrequent-access classes.

Use **S3 Analytics** and **Intelligent-Tiering** to identify and transition infrequently accessed data automatically.

---

### 🧠 **Key Takeaways**

- **Amazon S3** is a **highly durable, scalable object storage service**.  
- Organizes data into **buckets** and **objects**, with support for **versioning**, **replication**, and **lifecycle rules**.  
- Multiple **storage classes** balance cost and access needs — from **Standard** to **Glacier Deep Archive**.  
- S3 integrates deeply with AWS services like **Lambda**, **CloudFront**, and **Athena**.  
- Security is layered: **IAM policies**, **bucket policies**, **encryption**, and **Block Public Access**.  
- Use **Storage Lens**, **CloudTrail**, and **Cost Explorer** for visibility and cost control.  
- Follow **best practices**: enable versioning, apply lifecycle policies, and protect your buckets from public exposure.