# 🛡️ Module 4 - AWS Cloud Security  

## 6️⃣ Section 6: Working to Ensure Compliance

### 🟠 AWS Compliance Programs

AWS works with **external certifying bodies** and **independent auditors** to provide customers with transparency into the **security policies, processes, and controls** implemented by AWS.

A full list of compliance programs is available here:  
🔗 [AWS Compliance Programs](https://aws.amazon.com/compliance/programs/)

For details on which AWS services are covered under specific compliance frameworks, visit:  
🔗 [AWS Services in Scope by Compliance Program](https://aws.amazon.com/compliance/services-in-scope/)

**Example: ISO/IEC 27001:2013 Certification**  
This certification defines requirements for establishing, maintaining, and improving an **Information Security Management System (ISMS)**.  
It demonstrates that AWS manages security in a **comprehensive and continuous** way.

AWS also supports customers in meeting **common regulations and legal requirements**, such as:

- 🏥 **Health Insurance Portability and Accountability Act (HIPAA)** – for healthcare data protection  
- 🇪🇺 **General Data Protection Regulation (GDPR)** – protects EU citizens’ privacy and data  
  📘 [AWS GDPR Center](https://aws.amazon.com/compliance/gdpr-center/)  
- 💳 **Payment Card Industry Data Security Standard (PCI DSS)** – for payment data protection  

---

### 🟠 AWS Config

**AWS Config** enables you to **assess, audit, and evaluate** the configurations of your AWS resources.  
It continuously monitors and records resource configurations and automatically evaluates them against predefined compliance rules.

**Capabilities:**

- 📋 Tracks changes and relationships between resources.  
- 🧾 Provides a detailed **configuration history** for auditing.  
- ⚙️ Detects and flags **non-compliant resources**.  
- 🌍 Operates as a **Regional service**, but can **aggregate results across Regions or accounts** for unified visibility.

**Benefits:**  
- Simplifies **compliance auditing**, **security analysis**, **change management**, and **operational troubleshooting**.  

---

### 🟠 AWS Artifact

**AWS Artifact** provides **on-demand access** to AWS **security and compliance documentation**, such as:  
- ISO certifications  
- PCI reports  
- Service Organization Control (SOC) reports  

**Key uses:**

- Submit compliance documents to **auditors or regulators** to demonstrate AWS security posture.  
- Use reports to **evaluate your own cloud architecture** and **internal controls**.  
- Manage **agreements and compliance documents** (e.g., Business Associate Agreement for HIPAA).

**Features:**

- AWS Artifact only provides documents about **AWS itself**.  
- Customers are responsible for their **own organization’s compliance**.  
- You can **review, accept, and track agreements** (such as HIPAA BAA) directly in Artifact.  
- Agreements can apply to **multiple AWS accounts** via **AWS Organizations**.

📘 Learn more: [Managing Agreements in AWS Artifact](https://docs.aws.amazon.com/artifact/latest/ug/managing-agreements.html)

---

### 🧾 Key Takeaways

✅ **AWS Compliance Programs** provide transparency into AWS security controls and certifications.  
✅ **AWS Config** continuously monitors configurations for compliance and security issues.  
✅ **AWS Artifact** offers access to official AWS compliance and audit reports for internal and external use.  
