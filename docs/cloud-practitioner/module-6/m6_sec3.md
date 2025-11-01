# ⚙️ **Module 6 - Compute**  

## 3️⃣ **Section 3: Amazon EC2 Cost Optimization**

### 🟠 **Introduction**

Cost optimization is a key benefit of using AWS compute services.  
AWS gives you flexibility to choose **different pricing models** and features to manage costs while maintaining performance.

This section covers strategies and tools for optimizing EC2 costs through instance selection, elasticity, automation, and monitoring.

---

### 💸 **EC2 Pricing Models**

Amazon EC2 offers several pricing options depending on your workload type and budget.

| Pricing Model | Description | Ideal For |
|----------------|-------------|------------|
| **On-Demand Instances** | Pay for compute capacity by the hour or second, with no long-term commitments. | Unpredictable workloads or testing environments. |
| **Reserved Instances (RIs)** | Commit to a 1- or 3-year term for significant discounts (up to 75%). | Steady-state or predictable workloads. |
| **Spot Instances** | Use unused EC2 capacity at discounts up to 90%. AWS may reclaim capacity with short notice. | Fault-tolerant, flexible, or batch workloads. |
| **Dedicated Hosts** | Physical servers dedicated to a single customer for regulatory or licensing compliance. | Enterprise or compliance-heavy workloads. |
| **Savings Plans** | Flexible pricing model offering savings across EC2, Fargate, and Lambda in exchange for a 1- or 3-year usage commitment. | Variable workloads across services. |

---

### ⚙️ **Key Cost Optimization Strategies**

AWS defines **four pillars of EC2 cost optimization**:

#### 1️⃣ **Right-Size Your Resources**
- Choose the most efficient instance types and sizes for your workload.  
- Regularly analyze performance and adjust resources accordingly.  
- Use **AWS Compute Optimizer** to receive recommendations based on utilization data.

#### 2️⃣ **Increase Elasticity**
- Scale resources dynamically using **Auto Scaling**.  
- Automatically add or remove instances based on demand.  
- Avoid over-provisioning by aligning capacity with actual usage.  
- Combine **Elastic Load Balancing (ELB)** and Auto Scaling to distribute traffic efficiently.

#### 3️⃣ **Use the Optimal Pricing Model**
- Evaluate the combination of **On-Demand**, **Reserved**, and **Spot Instances**.  
- Example:
  - Use **On-Demand** for unpredictable peaks.
  - Use **Reserved Instances** for steady-state workloads.
  - Use **Spot** for batch jobs or background tasks.  

#### 4️⃣ **Optimize Storage and Data Transfer**
- Choose the right **EBS volume type** (e.g., gp3 vs. io2) to balance performance and cost.  
- Delete unused **EBS snapshots** and orphaned volumes.  
- Use **Amazon S3 Lifecycle Policies** to move data to cheaper storage classes.  
- Consolidate data transfer where possible using **Amazon CloudFront** or **PrivateLink**.

---

### 📈 **Tools for Cost Optimization**

AWS provides several tools to help monitor and reduce compute costs:

| Tool | Function |
|------|-----------|
| **AWS Cost Explorer** | Visualize, track, and analyze AWS spending patterns. |
| **AWS Budgets** | Set custom cost and usage budgets with email/SNS alerts. |
| **AWS Trusted Advisor** | Provides cost optimization checks and recommendations (e.g., idle instances, underused RIs). |
| **AWS Compute Optimizer** | Suggests optimal EC2 instance types based on past performance metrics. |
| **Amazon CloudWatch** | Monitors resource utilization (CPU, memory, network) to identify inefficiencies. |

---

### 🧮 **Right-Sizing Example**

Let’s say you have multiple **m5.large** instances running at only 15% CPU utilization.  
By switching to **t3.medium** instances, you could:
- Reduce cost by more than **50%**.
- Maintain the same performance level for typical usage.
- Automatically scale up when load increases (with Auto Scaling).

💡 *AWS Compute Optimizer* uses CloudWatch metrics to make these recommendations automatically.

---

### 🔁 **Leveraging Elasticity and Automation**

Elasticity is one of the core advantages of the AWS Cloud.

You can:
- Automatically **scale in/out** using **Auto Scaling Groups**.  
- **Stop or terminate** instances during off-peak hours to save money.  
- Use **AWS Lambda** or **EventBridge** to schedule instance shutdowns.  
- Employ **Savings Plans** to automatically apply lower rates to eligible compute usage.

Elastic workloads = efficient cost management ✅

---

### 💬 **Reserved Instances and Savings Plans**

#### 🔹 **Reserved Instances (RIs)**
- Provide discounts in exchange for long-term usage.
- Types:
  - **Standard RIs** → largest discount; fixed instance type and Region.
  - **Convertible RIs** → flexibility to change instance families or OS.
  - **Scheduled RIs** → run at specific times, ideal for predictable usage windows.

#### 🔹 **Savings Plans**
- Newer, more flexible option.  
- Commit to a consistent spend ($/hour) rather than specific instances.  
- Automatically applies savings to any compute usage (EC2, Fargate, or Lambda).  
- Easier to manage and more adaptable than RIs.

---

### 💡 **Spot Instances and Workload Resilience**

Spot Instances can offer up to **90% discounts** but can be interrupted when AWS reclaims capacity.

**Best practices for Spot usage:**
- Use **Spot Fleets** to diversify across instance types and AZs.  
- Combine Spot with On-Demand or Reserved Instances.  
- Store critical data on **EBS** or **S3** to preserve state.  
- Use **Auto Scaling** with interruption handling to maintain performance.

---

### 🧠 **Key Takeaways**

- **EC2 pricing flexibility** allows you to balance cost, performance, and reliability.  
- Apply the **four pillars of cost optimization**:
  1. Right-size resources.  
  2. Increase elasticity.  
  3. Choose the optimal pricing model.  
  4. Optimize storage and data transfer.  
- Use AWS tools like **Cost Explorer**, **Trusted Advisor**, **Compute Optimizer**, and **CloudWatch**.  
- Combine **On-Demand**, **Reserved**, and **Spot Instances** for maximum savings.  
- Automation and elasticity are the most powerful levers for long-term cost efficiency.  