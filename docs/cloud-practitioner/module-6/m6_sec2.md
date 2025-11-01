# ⚙️ **Module 6 - Compute**  

## 2️⃣ **Section 2: Amazon Elastic Compute Cloud (Amazon EC2)**

### 🟠 **Introduction to Amazon EC2**

**Amazon Elastic Compute Cloud (Amazon EC2)** provides secure, resizable compute capacity in the AWS Cloud.  
It is designed to make web-scale cloud computing easier for developers.

With EC2, you can:
- Launch virtual servers (instances) within minutes.
- Configure CPU, memory, storage, and networking.
- Scale up or down to handle variable workloads.
- Pay only for what you use.

**Key benefits:**
- Elasticity and scalability.  
- Complete control over instances.  
- Flexible cloud hosting environment.  
- Integration with most AWS services.

---

### 💡 **Understanding EC2 Instances**

An **EC2 instance** is a virtual server running on AWS infrastructure.

You can:
- Choose from a wide variety of **instance types** optimized for compute, memory, or storage.
- Launch instances in specific **Availability Zones** within a Region.
- Use **Auto Scaling** and **Elastic Load Balancing (ELB)** for high availability and performance.

Each instance type is a combination of:
- **CPU**
- **Memory**
- **Storage**
- **Networking capacity**

---

### ⚙️ **The EC2 Launch Process**

When launching an EC2 instance, you define its configuration in several steps:

1. **Choose an Amazon Machine Image (AMI)**  
   - AMI = a pre-configured template containing an operating system, software, and settings.  
   - AWS provides both **public AMIs** and **custom AMIs**.  
   - You can also create your own AMI from an existing instance for reuse.

2. **Choose an Instance Type**  
   - Instance types are grouped into families based on their use case:  

     | Instance Family | Optimization Focus | Example Use Cases |
     |-----------------|--------------------|-------------------|
     | **General Purpose** | Balanced compute, memory, and networking | Web servers, app servers |
     | **Compute Optimized** | High-performance CPU | High-traffic web apps, scientific modeling |
     | **Memory Optimized** | Large memory for in-memory processing | Databases, analytics |
     | **Storage Optimized** | High, sequential read/write access | Data warehousing, big data |
     | **Accelerated Computing** | GPU or FPGA acceleration | Machine learning, rendering |

3. **Configure Instance Details**  
   - Specify **number of instances**, **VPC**, **subnet**, **public IP settings**, **IAM role**, and **shutdown behavior**.
   - Optionally, add **user data scripts** to automate setup tasks at boot.

4. **Add Storage**  
   - Choose between multiple storage options (see below).

5. **Add Tags**  
   - Tags are key-value pairs for organization and cost tracking (e.g., `Environment=Production`).

6. **Configure Security Group**  
   - Acts as a **virtual firewall** for your instance.
   - Controls inbound/outbound traffic using rules (protocols, ports, IP ranges).

7. **Review and Launch**  
   - Choose or create a **key pair** to enable secure SSH (Linux) or RDP (Windows) access.

---

### 🧱 **Amazon Machine Images (AMIs)**

- An **AMI** defines:
  - The operating system.
  - Initial state (applications, libraries, and configurations).
  - Permissions for usage (public or private).
- You can **share**, **copy**, or **encrypt** AMIs.
- AMIs are Region-specific but can be copied to other Regions.

---

### 💾 **EC2 Storage Options**

AWS provides several types of storage that can be attached or integrated with EC2:

| Storage Type | Description | Key Features | Example Use |
|---------------|-------------|---------------|--------------|
| **Amazon Elastic Block Store (EBS)** | Block storage attached to EC2 instances. | Persistent, durable, automatically replicated within AZ. | Databases, file systems, boot volumes. |
| **Instance Store** | Temporary block storage physically attached to the host. | Very high I/O performance but data lost when instance stops/terminates. | Caching, temporary files, buffers. |
| **Amazon Elastic File System (EFS)** | Fully managed NFS file system shared across instances. | Scalable, elastic, accessible across multiple AZs. | Shared application data, content management. |
| **Amazon Simple Storage Service (S3)** | Object storage for any type of data. | Highly durable (11 9s), scalable, accessible anywhere. | Backups, logs, static assets, snapshots. |

---

### 🔒 **Security and Access**

#### 🔑 **Key Pairs**
- Used for secure SSH/RDP access to your instances.
- A key pair consists of:
  - **Public key** (stored by AWS)
  - **Private key** (stored by you, required for login)
- Always keep private keys secure. Lost private keys cannot be recovered.

#### 🧱 **Security Groups**
- Virtual firewalls controlling inbound/outbound traffic.
- Rules are **stateful**: if you allow an inbound connection, its response is automatically allowed.
- You can assign one or more security groups per instance.

#### 👤 **IAM Roles**
- Allow your instance to securely access other AWS services **without embedding credentials**.
- Best practice: assign a specific IAM role to each instance rather than using access keys.

---

### 🌐 **Networking**

Each EC2 instance resides inside an **Amazon Virtual Private Cloud (VPC)**.  

Within the VPC, you can configure:
- **Subnets** → logical segments of your network (public or private).  
- **Elastic IP Addresses** → static public IPs that can be reassigned between instances.  
- **Elastic Network Interfaces (ENIs)** → virtual network cards for more advanced configurations.

**Public vs. Private IPs**
- **Public IPs**: Accessible from the Internet (temporary unless associated with an Elastic IP).  
- **Private IPs**: Used for communication within a VPC.

---

### 🧩 **EC2 Instance Lifecycle**

| State | Description |
|--------|-------------|
| **Pending** | The instance is being launched. |
| **Running** | The instance is operational and billing begins. |
| **Stopping / Stopped** | Instance is halted but data persists on EBS volumes. |
| **Shutting-down / Terminated** | Instance is permanently deleted. |

---

### 📊 **Monitoring EC2**

Use **Amazon CloudWatch** to monitor EC2 performance metrics, such as:
- CPU utilization  
- Disk I/O  
- Network traffic  
- Status checks  

You can create **CloudWatch Alarms** to trigger notifications or Auto Scaling actions.

---

### 💬 **EC2 Cost Model**

Amazon EC2 offers multiple pricing models:

| Model | Description | Use Case |
|--------|-------------|-----------|
| **On-Demand** | Pay per second or hour with no commitment. | Short-term, unpredictable workloads. |
| **Reserved Instances** | 1–3 year commitment with discounts up to 75%. | Steady-state workloads. |
| **Spot Instances** | Up to 90% discount; can be interrupted by AWS. | Flexible, fault-tolerant workloads. |
| **Dedicated Hosts / Instances** | Physically isolated hardware. | Compliance or licensing requirements. |

---

### 🧠 **Key Takeaways**

- **Amazon EC2** provides scalable virtual servers in the cloud.  
- You can fully control the instance type, OS, storage, and network.  
- **AMIs** simplify deployment by offering reusable templates.  
- **Security Groups** act as virtual firewalls; **IAM Roles** grant secure access to other AWS services.  
- **CloudWatch** is used for monitoring performance.  
- Choose the right **pricing model** to balance cost and flexibility.  
- Combine **Auto Scaling** and **Elastic Load Balancing** for high availability and resilience.