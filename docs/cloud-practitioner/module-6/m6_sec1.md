# ⚙️ **Module 6 - Compute**  
## 1️⃣ **Section 1: Compute Services Overview**

### 🟠 **Introduction**

AWS offers a broad range of **compute services** in the cloud.  
Each service is designed for different use cases, with varying levels of control, management, and flexibility.

This section covers the most important compute services and how they are categorized within the AWS Cloud.

---

### 🖥️ **Primary Compute Services**

| Service | Brief Description |
|----------|------------------|
| **Amazon Elastic Compute Cloud (Amazon EC2)** | Provides resizable compute capacity (virtual machines) in the cloud. |
| **Amazon EC2 Auto Scaling** | Automatically adjusts capacity to maintain performance and availability. |
| **Amazon Elastic Container Registry (Amazon ECR)** | Secure, scalable repository for storing Docker images. |
| **Amazon Elastic Container Service (Amazon ECS)** | Container orchestration service to run Docker applications. |
| **VMware Cloud on AWS** | Enables hybrid environments without custom hardware. |
| **AWS Elastic Beanstalk** | Platform as a service (PaaS) that simplifies application deployment. |
| **AWS Lambda** | *Serverless* compute service that runs code on demand, charging only for execution time. |
| **Amazon Elastic Kubernetes Service (Amazon EKS)** | Managed Kubernetes service for running containerized workloads. |
| **Amazon Lightsail** | Simplified environment for building web apps and websites. |
| **AWS Batch** | Runs batch processing jobs at any scale. |
| **AWS Fargate** | Runs containers without managing servers or clusters. |
| **AWS Outposts** | Runs AWS services on-premises for hybrid workloads. |
| **AWS Serverless Application Repository** | Repository to discover and deploy pre-built serverless applications. |

---

### ⚙️ **Compute Service Categories**

AWS compute services can be grouped into **four main categories**, based on their level of control and management:

| **Services** | **Key Concepts** | **Characteristics** | **Ease of Use** |
|---------------|------------------|----------------------|-----------------|
| **Amazon EC2** | • Infrastructure as a Service (IaaS)  <br> • Instance-based  <br> • *Virtual machines* | • Provision virtual machines that you can manage as you choose | A familiar concept to many IT professionals. |
| **AWS Lambda** | • *Serverless* computing  <br> • Function-based  <br> • Low-cost | • Write and deploy code that runs on a schedule or that can be triggered by events  <br> • Use when possible (architect for the cloud) | A relatively new concept for many IT staff members, but easy to use after you learn how. |
| **Amazon ECS**  <br> **Amazon EKS**  <br> **AWS Fargate**  <br> **Amazon ECR** | • *Container-based* computing  <br> • Instance-based | • Spin up and run jobs more quickly | AWS Fargate reduces administrative overhead, but you can use options that give you more control. |
| **AWS Elastic Beanstalk** | • Platform as a Service (PaaS)  <br> • For *web applications* | • Focus on your code (building your application)  <br> • Easily integrates with other AWS services — databases, DNS, etc. | Fast and easy to get started. |

---

### 📈 **Category Details**

#### 🧩 **IaaS – Amazon EC2**
- Provides virtual machines called *EC2 instances*.  
- Offers full control over OS, storage, security, and networking.  
- Ideal for users familiar with traditional on-premises environments.  
- Foundational service of AWS and among the most widely used.

#### ⚡ **Serverless – AWS Lambda**
- Runs code without provisioning or managing servers.  
- Automatically scales based on demand.  
- Pay only for actual execution time.  
- Integrated with multiple AWS services such as S3, DynamoDB, and API Gateway.  

#### 🐳 **Container-based – ECS, EKS, Fargate, ECR**
- Run workloads inside containers on a shared OS.  
- Faster startup than virtual machines.  
- Easier deployment, scaling, and portability of microservices.  
- **AWS Fargate** eliminates the need to manage servers or clusters.  

#### ☁️ **PaaS – Elastic Beanstalk**
- Fully managed platform for deploying web applications.  
- AWS handles infrastructure provisioning, load balancing, scaling, and monitoring.  
- Developers only upload their code and configuration files.  

---

### 🧮 **Choosing the Right Compute Option**

There’s no single best service for every scenario.  
Your choice depends on:

- 📊 **Application design**
- 🔁 **Usage patterns**
- ⚙️ **Configuration and management needs**
- 💸 **Cost and operational model**

👉 Using the wrong service can result in inefficiency, higher costs, or poor performance.

---

### 💡 **Best Practices**

1. **Evaluate all compute options** before selecting a service.  
2. **Understand configuration choices** — instance type, size, storage, and network.  
3. **Collect performance metrics** using tools such as *Amazon CloudWatch*.  
4. **Leverage elasticity** to automatically scale with demand.  
5. **Continuously reassess** compute requirements to optimize for performance and cost.

---

### 🔍 **Architecture Example**

A customer might start using **Amazon EC2** for full control,  
then migrate to **AWS Lambda** or **Elastic Beanstalk** as the application evolves into a more agile, *cloud-native* architecture.

AWS recommends:  
> “Collect performance metrics, and adjust your compute configuration as your architecture evolves.”

📹 *Reference:* [Inventory Tracking Solution Example – AWS YouTube Video](https://www.youtube.com/watch?v=zr3Kib0i-OQ)

---

### 🧠 **Key Takeaways**

- AWS offers multiple compute options: **EC2**, **Lambda**, **ECS/EKS/Fargate**, and **Elastic Beanstalk**.  
- Main categories:  
  - **IaaS** → EC2  
  - **Serverless** → Lambda  
  - **Containers** → ECS, EKS, Fargate  
  - **PaaS** → Elastic Beanstalk  
- Choosing the right service depends on **control level**, **management needs**, and **application design**.  
- **Best practices:**  
  - Evaluate all options.  
  - Use metrics to guide decisions.  
  - Optimize and reassess regularly for performance and cost efficiency.  