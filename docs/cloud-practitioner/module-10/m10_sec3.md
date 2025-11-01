# ⚙️ **Module 10 - Automatic Scaling and Monitoring**  

## 3️⃣ **Section 3: Amazon EC2 Auto Scaling**

### 🟠 **Introduction**

**Amazon EC2 Auto Scaling** automatically adds or removes compute capacity to maintain application availability and optimize costs.  
It ensures your application has the **right number of EC2 instances** running to handle current demand — no more, no less.

By scaling automatically, you can deliver consistent performance while minimizing wasted resources.

---

### ⚡ **What Is Amazon EC2 Auto Scaling?**

**EC2 Auto Scaling** monitors your applications and adjusts capacity dynamically based on predefined policies and metrics (e.g., CPU utilization, network traffic).  
It works hand-in-hand with **Elastic Load Balancing (ELB)** and **Amazon CloudWatch** for full automation.

| **Capability** | **Description** |
|-----------------|----------------|
| **Dynamic Scaling** | Responds automatically to changes in demand. |
| **Predictive Scaling** | Uses machine learning to forecast future traffic. |
| **Scheduled Scaling** | Scales at specific times or dates. |
| **Health Checks & Recovery** | Detects unhealthy instances and replaces them automatically. |

🧠 *Example:* When traffic to your web app increases, EC2 Auto Scaling launches new instances. When demand drops, it terminates them to save cost.

---

### 🧩 **Core Components of EC2 Auto Scaling**

| **Component** | **Purpose** |
|----------------|-------------|
| **Auto Scaling Group (ASG)** | Logical group of EC2 instances managed together. |
| **Launch Template / Configuration** | Defines the instance settings (AMI, instance type, security groups, etc.). |
| **Scaling Policies** | Define when and how scaling actions occur. |
| **Health Checks** | Monitors instance health via EC2 or ELB. |

---

### 🧱 **Auto Scaling Group (ASG)**

An **Auto Scaling Group** maintains a defined number of EC2 instances — called the **desired capacity** — and ensures they are evenly distributed across **Availability Zones**.

#### **ASG Key Settings**
- **Minimum capacity** → The lowest number of instances to run.  
- **Maximum capacity** → The highest number of instances allowed.  
- **Desired capacity** → The target number of instances maintained by Auto Scaling.  

🧠 *Example:*  
If the ASG minimum = 2, maximum = 10, desired = 4 → Auto Scaling ensures there are always **4 healthy instances** running, scaling up or down as needed.

---

### ⚙️ **Launch Templates**

A **Launch Template** defines how new instances should be created.  
It includes configurations such as:
- AMI ID (Amazon Machine Image).  
- Instance type (e.g., t3.medium).  
- Key pair and security groups.  
- User data scripts (for automated setup).  
- IAM role permissions.

🧠 *Tip:* Launch Templates support versioning, so you can easily roll back to previous configurations.

---

### 🧮 **Scaling Policies**

Scaling policies define how Auto Scaling reacts to metric thresholds or forecasts.

| **Policy Type** | **Description** | **Use Case** |
|------------------|------------------|---------------|
| **Target Tracking** | Maintains a specific metric target (e.g., 50% CPU utilization). | Keeps performance consistent automatically. |
| **Step Scaling** | Adds/removes capacity based on incremental metric thresholds. | Scales faster when demand changes sharply. |
| **Simple Scaling** | Adds or removes a fixed number of instances based on a single alarm. | Suitable for smaller, steady workloads. |
| **Predictive Scaling** | Uses ML-based forecasts to add capacity in advance. | Ideal for recurring traffic patterns. |

🧠 *Example:*  
A target tracking policy keeps average CPU at 60%. When CPU exceeds that level, Auto Scaling adds new instances.

---

### 📅 **Scheduled and Predictive Scaling**

#### **Scheduled Scaling**
- Triggered at specific times (e.g., weekdays at 9 AM).  
- Helps prepare for predictable usage patterns (like business hours).  

#### **Predictive Scaling**
- Uses machine learning to anticipate demand before it occurs.  
- Adds instances **ahead of time**, improving performance and stability.  

🧠 *Example:*  
An e-commerce site schedules scaling during daily traffic surges and uses predictive scaling before holiday sales.

---

### 🔁 **Integration with ELB and CloudWatch**

**Auto Scaling** works seamlessly with:
- **Elastic Load Balancing (ELB)** → Distributes traffic evenly among instances.  
- **CloudWatch Alarms** → Triggers scaling events when metrics exceed thresholds.  
- **AWS Systems Manager** → Applies patches or configuration updates to new instances.  

🧠 *Example:* CloudWatch detects high CPU → triggers scaling policy → Auto Scaling adds new EC2 instances → ELB starts sending traffic to new instances automatically.

---

### 💰 **Cost Optimization**

- Pay only for the compute capacity you actually need.  
- Scale **out** during high demand and **in** during low traffic.  
- Combine **Auto Scaling** with **Savings Plans** or **Spot Instances** for further cost reduction.  
- Eliminate idle resources automatically.  

🧠 *Tip:* Use **instance weighting** to mix different instance types and sizes within the same ASG for flexibility and savings.

---

### 🧱 **Health Checks and Self-Healing**

Auto Scaling continuously monitors instance health using:
- **EC2 Status Checks** (hardware/software).  
- **Elastic Load Balancer (ELB) Health Checks** (application-level).  

If an instance fails health checks:
- It is **terminated** automatically.  
- A **new instance** is launched to replace it.  

🧠 *Result:* Your application remains available even when instances fail.

---

### 🔐 **Security Considerations**

- Apply least privilege to the IAM role associated with Auto Scaling.  
- Use **Launch Templates** with preconfigured **security groups** and **KMS encryption**.  
- Enforce **patching and compliance** with **AWS Systems Manager**.  
- Monitor scaling events via **CloudTrail** and **CloudWatch Logs**.

---

### 🧠 **Key Takeaways**

- **Amazon EC2 Auto Scaling** maintains **application availability** and **cost efficiency** automatically.  
- Use **Auto Scaling Groups (ASGs)** to define capacity limits and maintain desired instance counts.  
- **Scaling Policies** (Target Tracking, Step, Predictive) control how scaling happens.  
- Integrate with **CloudWatch** for metric-based scaling and **ELB** for traffic distribution.  
- Supports **scheduled scaling**, **predictive scaling**, and **health check recovery**.  
- Ensures a **self-healing, elastic architecture** with minimal manual intervention.  
