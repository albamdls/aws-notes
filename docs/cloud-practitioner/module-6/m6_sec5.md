# ⚙️ **Module 6 - Compute**  

## 5️⃣ **Section 5: AWS Lambda (Serverless Compute)**

### 🟠 **Introduction**

**AWS Lambda** is a *serverless compute service* that lets you run code without provisioning or managing servers.  
You upload your code, configure triggers, and AWS handles the execution automatically.

You are charged only for:
- The number of **requests** to your functions.
- The **duration** your code runs.

No need to manage infrastructure — Lambda automatically scales and provides high availability.

---

### ⚡ **How AWS Lambda Works**

AWS Lambda runs your code in response to **events** such as:
- Changes to data in **Amazon S3** or **DynamoDB**.
- HTTP requests via **Amazon API Gateway**.
- Stream processing from **Amazon Kinesis** or **MSK**.
- Scheduled events through **Amazon EventBridge** or **CloudWatch Events**.

Each function runs inside a **stateless, isolated environment** that is automatically created when invoked.

---

### 🧩 **Key Features of AWS Lambda**

| Feature | Description |
|----------|-------------|
| **Serverless** | No infrastructure to manage. AWS provisions resources on your behalf. |
| **Event-driven** | Executes code automatically in response to events or triggers. |
| **Automatic Scaling** | Scales from zero to thousands of requests per second seamlessly. |
| **Pay-per-use** | You are charged for compute time used (measured in milliseconds). |
| **Multi-language support** | Supports Node.js, Python, Java, Go, C#, Ruby, and custom runtimes. |
| **Integrations** | Works with over 200 AWS services as event sources or destinations. |
| **Built-in Monitoring** | Integrated with Amazon CloudWatch for logs and metrics. |

---

### ⚙️ **Lambda Function Components**

Every Lambda function has three main components:

1. **Code**  
   - The logic you want to execute.  
   - Can be uploaded as a ZIP file or container image (up to 10 GB).  
   - You can edit code directly in the Lambda console or use tools like AWS CLI or SDKs.

2. **Handler**  
   - The specific method inside your code that AWS Lambda executes.  
   - Example (Python):  
     ```python
     def lambda_handler(event, context):
         print("Hello from Lambda!")
     ```

3. **Execution Role (IAM Role)**  
   - Grants your function permissions to access AWS resources (e.g., S3, DynamoDB).  
   - Follows the **principle of least privilege** for security.

---

### ⚡ **Execution and Scaling**

When a Lambda function is invoked:
1. AWS creates or reuses a container environment.
2. The handler runs your code with the provided event data.
3. Lambda scales automatically based on incoming requests.
4. Multiple executions can occur in parallel, each in an isolated environment.

AWS manages:
- Scaling and load balancing.
- Health monitoring.
- Logging and metrics.

---

### 🧮 **Pricing Model**

You are billed based on:
- **Number of requests:** $0.20 per 1 million requests (first 1 million free).  
- **Compute time:** Measured in milliseconds, depending on allocated memory (from 128 MB to 10 GB).  
- **Free tier:** 1 million requests and 400,000 GB-seconds per month.

Example:
- A function running for 100 ms with 512 MB of memory costs only fractions of a cent.

Lambda’s pricing model encourages **cost efficiency** for short-lived or variable workloads.

---

### 🧠 **Supported Event Sources**

| Service | Trigger Type | Example |
|----------|---------------|----------|
| **Amazon S3** | Object event | Run code when a file is uploaded. |
| **Amazon DynamoDB Streams** | Data event | React to database changes. |
| **Amazon API Gateway** | HTTP request | Build serverless APIs. |
| **Amazon EventBridge / CloudWatch** | Scheduled or system event | Run periodic tasks (cron). |
| **Amazon Kinesis / MSK** | Data stream | Real-time data processing. |
| **AWS Step Functions** | Workflow trigger | Execute function chains. |

---

### 🧱 **Integrations and Use Cases**

#### 🪣 **File Processing**
Automatically trigger a Lambda function when an object is uploaded to S3 (e.g., image resizing or metadata extraction).

#### 🔄 **Data Transformation**
React to changes in DynamoDB and transform or forward the data to another service.

#### 🌐 **Serverless APIs**
Combine Lambda with **API Gateway** to create fully managed REST or GraphQL APIs.

#### ⏰ **Scheduled Tasks**
Use EventBridge rules to execute functions at fixed intervals (e.g., cleanup jobs).

#### 📊 **Real-time Stream Processing**
Consume data from **Amazon Kinesis** streams for analytics or monitoring.

---

### 🔐 **Security and Permissions**

- Each Lambda function uses an **IAM role** for AWS resource access.  
- Store secrets and API keys securely in:
  - **AWS Secrets Manager**
  - **AWS Systems Manager Parameter Store**
- Use **VPC integration** if your Lambda function needs to access private resources.  
- Enable **CloudWatch Logs** for monitoring executions and debugging.

---

### ⚙️ **Best Practices**

1. **Keep functions small and modular** — single-purpose functions are easier to maintain.  
2. **Avoid heavy dependencies** — minimize cold start times.  
3. **Reuse execution environments** when possible (use global variables).  
4. **Implement error handling and retries** for reliability.  
5. **Use concurrency limits** to control scaling behavior.  
6. **Monitor metrics** such as invocation count, duration, and throttling via CloudWatch.  
7. **Leverage Lambda Layers** to share code and dependencies across functions.  

---

### 🧮 **Limits and Quotas**

| Limit | Value |
|--------|--------|
| **Memory Allocation** | 128 MB – 10 GB |
| **Maximum Execution Time** | 15 minutes |
| **Package Size (ZIP)** | 250 MB |
| **Package Size (Container Image)** | 10 GB |
| **Concurrent Executions (Default)** | 1,000 (adjustable) |
| **Environment Variables** | 4 KB limit per function |

---

### 🧠 **Key Takeaways**

- **AWS Lambda** runs code *without servers*, *automatically scaling* based on demand.  
- **Event-driven** model integrates with 200+ AWS services.  
- Pay only for what you use — *no idle costs*.  
- Use **IAM roles** for secure resource access and **CloudWatch** for monitoring.  
- Lambda is ideal for:
  - Event-driven processing.
  - Serverless APIs.
  - Automation and scheduled tasks.  
- Follow best practices to reduce latency, cost, and improve maintainability.