# ⚙️ **Module 10 - Automatic Scaling and Monitoring**  

## 2️⃣ **Section 2: Amazon CloudWatch**

### 🟠 **Introduction**

To maintain performance, cost control, and security in the cloud, you need **visibility** into how your systems are operating.  
**Amazon CloudWatch** provides real-time **monitoring**, **alerting**, and **automation** for AWS resources and applications.

CloudWatch collects and tracks **metrics**, collects **logs**, and enables **automated responses** to changes in your environment — helping you operate efficiently and proactively.

---

### 📊 **What Is Amazon CloudWatch?**

**Amazon CloudWatch** is a **monitoring and observability service** that provides data and actionable insights for:
- AWS resources (e.g., EC2, RDS, Lambda, EBS, S3).  
- On-premises systems and hybrid environments.  
- Applications and custom business metrics.  

It helps detect anomalies, optimize performance, and trigger automated actions when thresholds are breached.

🧠 *Example:* Automatically add EC2 instances to handle traffic spikes or send an alert when CPU usage exceeds 80%.

---

### 🧩 **Core CloudWatch Components**

| **Component** | **Description** |
|----------------|-----------------|
| **Metrics** | Quantitative data points (e.g., CPU utilization, network I/O, request latency). |
| **Alarms** | Trigger notifications or actions based on metric thresholds. |
| **Logs** | Collect and analyze log data from AWS services and applications. |
| **Dashboards** | Custom visualizations for monitoring metrics in real time. |
| **Events (EventBridge)** | Respond to system changes automatically (e.g., trigger Lambda functions). |
| **Contributor Insights** | Identify top contributors to system performance issues. |
| **Anomaly Detection** | Uses ML to detect unusual behavior in metrics automatically. |

---

### 📈 **CloudWatch Metrics**

Metrics are the **foundation** of CloudWatch monitoring.  
They measure the performance of AWS resources and are automatically collected for most services.

| **Metric Example** | **Service** | **Purpose** |
|----------------------|-------------|--------------|
| CPUUtilization | EC2 | Measures instance processor use. |
| Invocations | Lambda | Tracks number of function executions. |
| DatabaseConnections | RDS | Measures open connections to a database. |
| NetworkIn / NetworkOut | EC2, ELB | Monitors incoming and outgoing traffic. |
| ReadIOPS / WriteIOPS | EBS | Tracks disk read/write operations. |

🧠 *Tip:* You can also **publish custom metrics** (e.g., number of users online, app latency).

---

### 🚨 **CloudWatch Alarms**

**Alarms** let you respond automatically when metrics breach predefined thresholds.

#### 💡 **How They Work**
1. Define a **metric and threshold** (e.g., CPUUtilization > 75%).  
2. Specify an **evaluation period** (how long to wait before triggering).  
3. Choose an **action** — send an alert (via SNS) or run an automation (e.g., scale resources).

#### ⚙️ **Alarm States**
| **State** | **Meaning** |
|------------|-------------|
| **OK** | Metric is within the defined threshold. |
| **ALARM** | Metric has crossed the threshold. |
| **INSUFFICIENT_DATA** | Not enough data points to determine state. |

🧠 *Example:* If average CPU > 80% for 5 minutes, CloudWatch triggers an SNS notification or Auto Scaling event.

---

### 📜 **CloudWatch Logs**

**CloudWatch Logs** collect, store, and analyze logs from AWS services and custom applications.

#### 🧰 **Capabilities**
- Centralized **log aggregation** from multiple sources.  
- **Real-time log streaming** for analysis or dashboards.  
- Integration with **CloudWatch Logs Insights** for querying logs with SQL-like syntax.  
- Retention policies for automatic log deletion.  

🧠 *Example:* Store EC2 system logs or Lambda execution logs for troubleshooting.

---

### 🧮 **CloudWatch Dashboards**

Create **custom dashboards** to visualize metrics and logs from multiple AWS accounts and Regions in one place.

#### **Key Benefits**
- Combine multiple metrics (e.g., CPU, memory, latency) on a single panel.  
- Share dashboards across teams.  
- Add alarms, charts, and annotations for context.  
- Use them for **operational visibility** and **executive reporting**.

🧠 *Example:* A single dashboard shows EC2 instance health, Auto Scaling activity, and RDS performance metrics.

---

### ⚙️ **CloudWatch Events (Now Amazon EventBridge)**

**CloudWatch Events** (integrated into **Amazon EventBridge**) enable **event-driven automation**.

#### **Capabilities**
- Detects changes in AWS resources (e.g., EC2 state change, Lambda error).  
- Triggers actions automatically (e.g., invoke a Lambda, start a Step Function, or send an SNS notification).  
- Uses event patterns and rules to route events to targets.

🧠 *Example:* When an EC2 instance stops unexpectedly, EventBridge triggers a Lambda function to restart it.

---

### 🤖 **Automation and Integration**

**CloudWatch** integrates with other AWS services to automate responses and remediation.

| **Integration** | **Action** |
|------------------|-------------|
| **Auto Scaling** | Adjust instance capacity automatically based on metrics. |
| **AWS Lambda** | Execute custom automation code when an event occurs. |
| **Amazon SNS** | Send alerts via email, SMS, or to chatbots. |
| **AWS Systems Manager** | Run predefined automation playbooks for incident response. |

🧠 *Example:* CloudWatch detects high latency → triggers Lambda → clears cache in ElastiCache cluster.

---

### 🔐 **Security and Access Control**

- Integrated with **AWS Identity and Access Management (IAM)** for granular permissions.  
- Use **resource-level permissions** to restrict access to metrics and dashboards.  
- Encrypt logs using **AWS KMS**.  
- Use **cross-account dashboards** for centralized monitoring in multi-account environments.  

🧠 *Best Practice:* Limit CloudWatch access to read-only roles for most users.

---

### 🧠 **Key Takeaways**

- **Amazon CloudWatch** provides **monitoring, observability, and automation** across AWS resources.  
- Use **metrics**, **alarms**, **logs**, and **dashboards** to maintain operational health.  
- **EventBridge integration** enables **event-driven automation**.  
- Combine CloudWatch with **Auto Scaling**, **SNS**, and **Lambda** for proactive operations.  
- Secure CloudWatch data using **IAM policies** and **KMS encryption**.  
- Centralize monitoring across Regions and accounts with **cross-account dashboards**.  