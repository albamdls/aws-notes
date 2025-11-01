# 🏗️ **Module 9 - Cloud Architecture**  

## 6️⃣ **Section 6: Designing for Security and Compliance in the Cloud**

### 🟠 **Introduction**

Security is the **top priority** at AWS and a **shared responsibility** between AWS and the customer.  
When designing architectures in the cloud, you must implement **defense in depth**, **encryption**, and **access control** across every layer.

AWS provides numerous services, tools, and best practices to help you design **secure, compliant, and auditable** cloud environments.

---

### 🧩 **The Shared Responsibility Model**

In the AWS Cloud, **security and compliance responsibilities** are shared between AWS and the customer.

| **Responsibility** | **AWS** | **Customer** |
|---------------------|----------|---------------|
| **Infrastructure Security** | Secures the physical facilities, hardware, and global network. | Configures resources securely (IAM, networking, encryption). |
| **Compute and Storage** | Manages the host operating systems and virtualization layers. | Manages guest OS, applications, and data access. |
| **Networking** | Protects global backbone and routing. | Configures firewalls, VPC security groups, and NACLs. |
| **Data** | Provides encryption and storage isolation. | Classifies and controls access to data. |

🧠 *Tip:* AWS secures **the cloud**, while customers secure **what’s in the cloud**.

---

### 🔐 **Security by Design**

AWS encourages **security to be built into every layer** of your architecture.

#### **Key Security Design Principles**
| **Principle** | **Description** |
|----------------|-----------------|
| **1. Implement Least Privilege** | Give users and applications only the permissions they need. |
| **2. Enable Traceability** | Use logging and monitoring (CloudTrail, Config) for visibility. |
| **3. Apply Defense in Depth** | Layer security controls (network, IAM, encryption, application). |
| **4. Automate Security Tasks** | Use infrastructure as code (IaC) and automated remediation. |
| **5. Protect Data in Transit and at Rest** | Use TLS, SSE-KMS, or client-side encryption. |
| **6. Prepare for Security Events** | Enable alerts, incident response plans, and recovery processes. |

🧠 *Best Practice:* Automate security using **AWS Config Rules**, **GuardDuty**, and **Security Hub**.

---

### 🛡️ **Identity and Access Management (IAM)**

**AWS Identity and Access Management (IAM)** allows you to control who can access your AWS resources and how.

#### 🔧 **Core Features**
- **Users and Groups:** Define individual or team access.  
- **Roles:** Grant temporary permissions for AWS services or federated identities.  
- **Policies:** JSON documents that define permissions (allow or deny actions).  
- **Access Keys and MFA:** Enable secure authentication.  
- **IAM Identity Center (SSO):** Centralized access for enterprise users.

🧠 *Tip:* Always apply **least privilege**, use **IAM roles** instead of long-term keys, and enable **MFA** for all accounts.

---

### 🌐 **Network Security**

AWS networking services enable you to **secure data traffic** and **isolate resources**.

| **Service / Feature** | **Purpose** |
|------------------------|-------------|
| **Amazon VPC** | Create isolated virtual networks. |
| **Security Groups** | Instance-level virtual firewalls. |
| **Network ACLs (NACLs)** | Subnet-level traffic filtering. |
| **VPC Peering / PrivateLink** | Secure, private communication between VPCs or services. |
| **AWS Shield** | Managed DDoS protection. |
| **AWS WAF (Web Application Firewall)** | Protects against web exploits and attacks. |

🧠 *Example:* Combine **VPC**, **Security Groups**, and **WAF** to secure your public-facing web applications.

---

### 🧱 **Data Protection and Encryption**

AWS provides **encryption at rest and in transit** for all major services.

| **Service** | **Encryption Options** | **Managed By** |
|--------------|------------------------|----------------|
| **Amazon S3** | SSE-S3, SSE-KMS, SSE-C, client-side. | Customer / AWS. |
| **Amazon EBS / RDS / DynamoDB** | KMS-managed encryption. | Customer. |
| **AWS KMS (Key Management Service)** | Centralized key management with audit logs. | Customer. |
| **AWS Certificate Manager (ACM)** | Provision and manage SSL/TLS certificates. | AWS. |

🧠 *Tip:* Use **AWS KMS** for unified key management and **ACM** for secure HTTPS endpoints.

---

### 🧮 **Security Monitoring and Threat Detection**

| **Service** | **Function** |
|--------------|--------------|
| **AWS CloudTrail** | Logs all API calls and user actions. |
| **AWS Config** | Tracks configuration changes and compliance. |
| **Amazon CloudWatch** | Monitors performance metrics and sets alerts. |
| **Amazon GuardDuty** | Detects malicious activity and anomalies. |
| **AWS Security Hub** | Centralized security visibility and best practice checks. |
| **AWS Detective** | Investigates security findings with context. |

🧠 *Best Practice:* Enable **GuardDuty**, **Config**, and **CloudTrail** in all accounts by default.

---

### 📜 **Compliance and Governance**

AWS adheres to numerous global compliance standards and frameworks, helping customers meet their own regulatory obligations.

| **Framework / Standard** | **Purpose** |
|----------------------------|--------------|
| **ISO 27001 / 27017 / 27018** | Information security management and cloud privacy. |
| **SOC 1, SOC 2, SOC 3** | Internal control and security reporting. |
| **PCI DSS** | Secure handling of payment card data. |
| **HIPAA** | Protects healthcare information. |
| **FedRAMP** | Federal government compliance in the U.S. |
| **GDPR** | EU data privacy regulation. |

🧠 *Tip:* Use **AWS Artifact** to download compliance reports and certifications.

---

### ⚙️ **Automation and Security at Scale**

Automation ensures consistent and repeatable security configurations across accounts and Regions.

#### **AWS Tools for Security Automation**
- **AWS CloudFormation** – Deploy secure infrastructure as code.  
- **AWS Systems Manager (SSM)** – Patch and configure systems automatically.  
- **AWS Organizations & SCPs** – Enforce policies across multiple accounts.  
- **AWS Control Tower** – Automate account setup and guardrails.  

🧠 *Example:* Automatically deploy a compliant landing zone using **Control Tower** with **predefined security guardrails**.

---

### 🧠 **Key Takeaways**

- AWS and customers share security responsibilities — AWS secures **the cloud**, you secure **your data and configurations**.  
- Implement **defense in depth** with IAM, encryption, and network isolation.  
- Automate security controls and auditing using **Config**, **GuardDuty**, **CloudTrail**, and **Security Hub**.  
- Use **KMS** and **ACM** for encryption and certificate management.  
- Design architectures that meet **compliance standards** (ISO, SOC, PCI, HIPAA, GDPR).  
- Build security into every stage of development — automate wherever possible.  
- Always apply the **principle of least privilege** and enable **multi-factor authentication (MFA)** for all users.  
