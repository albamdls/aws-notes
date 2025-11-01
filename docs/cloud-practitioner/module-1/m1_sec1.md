# ☁️ Module 1 - Cloud Concepts Overview  

## 1️⃣ Section 1: What is Cloud Computing?  

### 🟠 Definition  

**Cloud computing** is the **on-demand delivery of compute power, databases, storage, applications, and other IT resources** via the internet with **pay-as-you-go pricing**.  

💡 These resources run on **servers located in large data centers** around the world. When you use a provider like **AWS**, that provider **owns and manages** the physical infrastructure.  

📚 Learn more: [What is Cloud Computing?](https://aws.amazon.com/what-is-cloud-computing/)  

---

### 🟠 Infrastructure as Software  

Cloud computing allows you to **stop thinking of infrastructure as hardware** and instead treat it as **software**.  

#### 🔹 Traditional (On-Premises) Model  
- Physical hardware requires **space, staff, physical security, planning, and capital expenditure (CapEx)**.  
- **Long procurement cycles** for buying and maintaining hardware.  
- Must **guess future capacity** (risk of over- or under-provisioning).  
- Example: setting up a new website requires purchasing and installing servers manually.  

#### 🔹 Cloud Computing Model  
- Infrastructure becomes **software-driven and flexible**.  
- Provision or terminate resources **on demand**.  
- **Pay only for what you use**.  
- **Scale elastically** up or down automatically.  
- **Reduce undifferentiated heavy lifting** like maintenance and capacity planning.  
- Enables **rapid innovation** and **low upfront costs**.  

---

### 🟠 Cloud Service Models  

Each service model offers a different level of control and management responsibility:  

| Model | Description | Example AWS Services |
|--------|--------------|----------------------|
| **IaaS (Infrastructure as a Service)** | Basic building blocks of cloud IT: networking, compute, and storage. Offers the **highest flexibility and control**. | Amazon EC2, Amazon S3 |
| **PaaS (Platform as a Service)** | Removes the need to manage underlying infrastructure. Focus on **application deployment and management**. | AWS Elastic Beanstalk, AWS Lambda, Amazon RDS |
| **SaaS (Software as a Service)** | Complete software product managed by the provider. You only **use the application**. | Amazon Chime, AWS WorkMail, AWS Trusted Advisor |

📊 **Control Level:**  
➡️ IaaS = More control  
➡️ SaaS = Less control  

---

### 🟠 Cloud Deployment Models  

| Model | Description | Characteristics |
|--------|--------------|----------------|
| **Cloud** | Fully deployed in the cloud. Built or migrated apps run entirely on AWS. | Scalable, flexible, cost-effective |
| **Hybrid** | Combines on-premises infrastructure with cloud resources. | Connects local systems with AWS |
| **On-Premises / Private Cloud** | Resources managed locally (legacy IT). | Dedicated hardware, less flexible |

---

### 🟠 AWS vs Traditional IT  

| Area | Traditional IT | AWS Equivalent |
|-------|----------------|----------------|
| **Security** | Firewalls, ACLs, admins | Security Groups, Network ACLs, IAM |
| **Networking** | Routers, switches | Amazon VPC, Elastic Load Balancing |
| **Compute** | On-prem servers | Amazon EC2, AMIs |
| **Storage & Databases** | DAS, SAN, NAS, RDBMS | Amazon EBS, EFS, S3, RDS |

💡 With AWS, you can do **almost everything you would in a traditional data center**, but faster and more efficiently.  

---

### 🟠 Key Takeaways  

✅ **Cloud computing** = On-demand IT resources via the internet with pay-as-you-go pricing.  
✅ Think of your **infrastructure as software**, not hardware.  
✅ **Three service models**: IaaS, PaaS, SaaS.  
✅ **Three deployment models**: Cloud, Hybrid, On-Premises.  
✅ Almost everything done in traditional IT can also be implemented in the AWS Cloud.  