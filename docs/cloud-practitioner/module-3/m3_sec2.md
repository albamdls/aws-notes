# 🌎 Module 3 - AWS Global Infrastructure Overview

## 2️⃣ Section 2: AWS services and service category overview

### 🟠 AWS foundational services

- Built on: **Regions, AZs, PoPs**.
- Deliver: **networking, compute, storage, databases**.
- On-demand utility → **available in seconds, pay-as-you-go**.

### 🟠 AWS categories of services

- AWS has **23 service categories**.
- Exam focus categories:
    - **Compute**
    - **Storage**
    - **Database**
    - **Networking & Content Delivery**
    - **Security, Identity & Compliance**
    - **Management & Governance**
    - **Cost Management**

### 🟠 Storage service category

- **Amazon S3** → object storage, scalable, secure, used for web apps, backup, IoT, analytics.
- **Amazon EBS** → block storage for EC2, high performance, used for DBs, analytics, containers.
- **Amazon EFS** → managed NFS file system, scales to petabytes, grows/shrinks automatically.
- **Amazon S3 Glacier** → low-cost archival storage, 11 9s durability, compliance.

### 🟠 Compute service category

- **Amazon EC2** → resizable compute capacity (VMs).
- **EC2 Auto Scaling** → adjust instances based on conditions.
- **Amazon ECS** → container orchestration for Docker.
- **Amazon ECR** → container registry for Docker images.
- **Elastic Beanstalk** → simple web app deployment.
- **AWS Lambda** → run code without servers (serverless), pay per execution.
- **Amazon EKS** → managed Kubernetes service.
- **AWS Fargate** → run containers without managing servers/clusters.

### 🟠 Database service category

- **Amazon RDS** → managed relational DB, automates provisioning, patching, backups.
- **Amazon Aurora** → MySQL/PostgreSQL-compatible, 3–5x faster than standard DBs.
- **Amazon Redshift** → petabyte-scale data warehouse, queries on Redshift + S3.
- **Amazon DynamoDB** → key-value/document NoSQL DB, millisecond latency, built-in security.

### 🟠 Networking and content delivery service category

- **Amazon VPC** → isolated networks in the AWS Cloud.
- **Elastic Load Balancing (ELB)** → distributes traffic across multiple resources.
- **Amazon CloudFront** → global CDN, low latency content delivery.
- **AWS Transit Gateway** → connect VPCs and on-prem networks to one gateway.
- **Amazon Route 53** → scalable DNS service, routes domains to apps.
- **AWS Direct Connect** → dedicated private connection to AWS.
- **AWS VPN** → secure tunnels to AWS.

### 🟠 Security, identity and compliance service category

- **IAM** → manage users, groups, permissions.
- **AWS Organizations** → multi-account management with SCPs.
- **Amazon Cognito** → user authentication and access for apps.
- **AWS Artifact** → compliance/security reports and agreements.
- **AWS KMS** → encryption key management.
- **AWS Shield** → managed DDoS protection.

### 🟠 AWS cost management service category

- **AWS Cost and Usage Report** → detailed billing and usage.
- **AWS Budgets** → alerts when forecasted/actual usage exceeds budget.
- **AWS Cost Explorer** → visualize and analyze costs.

### 🟠 Management and governance service category

- **AWS Management Console** → web-based management interface.
- **AWS Config** → track resource inventory and changes.
- **Amazon CloudWatch** → monitor resources and apps.
- **AWS Auto Scaling** → scale multiple resources dynamically.
- **AWS CLI** → unified command-line management tool.
- **AWS Trusted Advisor** → optimization insights (cost, performance, security).
- **AWS Well-Architected Tool** → review workloads against best practices.
- **AWS CloudTrail** → track API calls and user activity.
