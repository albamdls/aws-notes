# 🛡️ Module 4 - AWS Cloud Security  

## 1️⃣ Section 1: AWS Shared Responsibility Model

### 🟠 AWS Shared Responsibility Model

**Security and compliance** are a **shared responsibility** between **AWS** and the **customer**.  
This model is designed to **reduce the customer’s operational burden** while maintaining **flexibility and control** for deploying solutions on AWS.

The distinction between responsibilities is often referred to as:  
- 🔸 **Security “of” the cloud** → AWS responsibility.  
- 🔸 **Security “in” the cloud** → Customer responsibility.

AWS operates, manages, and controls components from the **virtualization layer down to the physical security** of the facilities where AWS services run.  
AWS is responsible for protecting the **infrastructure** (hardware, software, networking, and facilities) that powers the AWS Cloud.

The **customer**, on the other hand, is responsible for:  
- 🔐 **Encrypting data** at rest and in transit.  
- 🧱 Ensuring **secure network configurations**.  
- 👥 Managing **security credentials** and **user access**.  
- ⚙️ Maintaining and updating **operating systems** and **security groups** for any compute instances they launch.

---

### 🟠 AWS Responsibility: Security of the Cloud

**AWS is responsible for security *of* the cloud.**  
This includes managing and controlling infrastructure components from the **bare metal host operating system** and **hypervisor** down to **physical data center security**.

AWS protects the **global infrastructure** that runs all AWS services — including Regions, Availability Zones, and edge locations.

**AWS responsibilities include:**  

- 🏢 **Physical Security**
  - Data centers with **restricted access**, located in **nondescript facilities**.  
  - 24/7 security guards, **two-factor authentication**, access logging, **video surveillance**, and **secure media destruction (degaussing, shredding)**.

- 🖥️ **Hardware Infrastructure**
  - Servers, storage devices, and networking equipment that power the cloud.

- 💽 **Software Infrastructure**
  - Operating systems, service applications, and **virtualization software**.

- 🌐 **Network Infrastructure**
  - Routers, switches, firewalls, cabling, and redundant connections.  
  - AWS continuously monitors **network boundaries**, secures **access points**, and provides **intrusion detection and redundancy**.

🔎 AWS provides **third-party audit reports** (from independent auditors) that verify compliance with global **security standards and regulations**.  
Although customers cannot physically visit data centers, AWS ensures transparency through these reports.

---

### 🟠 Customer Responsibility: Security in the Cloud

While AWS manages the underlying infrastructure, **customers are responsible for securing everything they deploy or connect** within the AWS Cloud.

**Customer responsibilities include:**  
- Selecting and securing **operating systems** on EC2 instances.  
- Securing **applications** hosted on AWS resources.  
- Configuring **security groups**, **firewalls**, and **networks**.  
- Managing **user access and credentials** securely.  
- Implementing **encryption** for data at rest and in transit.  

Customers maintain **full control** over their content, including:  
- 📦 What data they choose to store on AWS.  
- 🧰 Which AWS services are used with that data.  
- 🌍 Where (in which Region) that data is stored.  
- 🧩 How the data is structured, masked, anonymized, or encrypted.  
- 👥 Who has access, and how those access rights are **granted, managed, and revoked**.

Customers retain responsibility for the **security of their own environment**, including applications, IAM configurations, and operating systems.

---

### 🟠 Service Characteristics and Security Responsibility

AWS offers multiple service models — **IaaS, PaaS, and SaaS** — each with different levels of shared responsibility.

| Service Model | Description | Example AWS Services | Customer Responsibility | AWS Responsibility |
|----------------|-------------|----------------------|--------------------------|--------------------|
| **IaaS (Infrastructure as a Service)** | Provides basic building blocks like compute, storage, and networking. | Amazon EC2 | Manage OS updates, security patches, apps, and firewall configurations. | Manages the underlying infrastructure (hardware, networking, virtualization). |
| **PaaS (Platform as a Service)** | Removes the need to manage hardware or OS. Focus is on deploying apps. | AWS Lambda, Amazon RDS | Manage data, classify assets, set permissions. | Handles OS and database patching, firewall setup, disaster recovery. |
| **SaaS (Software as a Service)** | Centrally hosted software accessed via web, API, or mobile. | AWS Trusted Advisor, AWS Shield, Amazon Chime | Use the service securely; no infrastructure management required. | Manages everything (infrastructure, platform, and application). |

---

### 🟠 Examples of SaaS Services

- **AWS Trusted Advisor** → Analyzes your AWS environment and provides **real-time recommendations** for best practices.  
  - Available to all accounts (with some advanced checks limited to Business or Enterprise Support plans).  

- **AWS Shield** → A **managed DDoS protection service** that automatically detects and mitigates attacks.  
  - AWS Shield Advanced offers **enhanced protections** and access to the **AWS DDoS Response Team**.  

- **Amazon Chime** → A communication service that allows you to **meet, chat, and call** within and outside your organization.  
  - Pay-as-you-go model, with no upfront fees or contracts.

---

### 🧾 Key Takeaways

✅ AWS and customers **share responsibility for security**.  
✅ **AWS** is responsible for **security *of* the cloud** — infrastructure, hardware, software, networking, and facilities.  
✅ **Customers** are responsible for **security *in* the cloud** — data, configurations, access management, and applications.  
✅ For **IaaS**, customers manage OS updates, patches, and firewalls.  
✅ For **PaaS**, AWS handles most of the infrastructure and OS security.  
✅ For **SaaS**, AWS manages the entire stack, and customers simply use the service securely.  
✅ In **IaaS**, customers have **more control and responsibility**.  
✅ In **PaaS** and **SaaS**, AWS assumes **greater security responsibilities**.
