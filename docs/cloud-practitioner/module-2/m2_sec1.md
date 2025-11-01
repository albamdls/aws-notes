# 📊 Module 2 - Cloud Economics and Billing

## 1️⃣ Section 1: Fundamentals of pricing

### 🟠 AWS pricing model

The **three main cost drivers** in AWS are:

- **Compute** → charged per hour/second, varies by instance type.
- **Storage** → typically charged per GB.
- **Data transfer** → outbound is charged (aggregated across services), inbound is usually free within the same region (exceptions exist).

👉 Outbound data transfer charges appear on the bill as **Data Transfer Out**.

### 🟠 How do you pay for AWS?

At the end of each month, you pay for what you use. You can start or stop using a product at any time. No long-term contracts are required.

AWS follows a **utility-style model**: you pay only for what you use, with no long-term contracts.

Key principles:

1. **Pay for what you use** – no upfront infrastructure costs.
2. **Pay less when you reserve** – discounts with Reserved Instances (EC2, RDS).
3. **Pay less by using more** – tiered pricing with volume discounts (e.g., Amazon S3).
4. **Pay even less as AWS grows** – AWS continuously lowers costs as it scales.

### 🟠 Pay for what you use

With AWS, you pay only for the services that you consume with no large upfront expenses.

You can lower variable costs, so you no longer need to dedicate valuable resources to building costly infrastructure, including purchasing servers, software licenses, or leasing facilities.

Quickly adapt to changing business needs and redirect your focus on innovation and invention by paying only for what you use and for as long as you need it.

All AWS services are available on demand, require no long-term contracts, and have no complex licensing dependencies

### 🟠 Pay less when you reserve

For certain services like Amazon Elastic Compute Cloud (Amazon EC2) and Amazon Relational Database Service (Amazon RDS), you can invest in reserved capacity.

With Reserved Instances, you can save up to 75 percent over equivalent on-demand capacity.

Reserved Instances are available in **three options**:

- **All Upfront Reserved Instance (AURI)** → highest discount
- **Partial Upfront Reserved Instance (PURI**) → smaller upfront payment, medium discount
- **No Upfront Payments Reserved Instance (NURI**) → no initial payment, lowest discount

When you buy Reserved Instances, you receive a greater discount when you make a larger upfront payment. To maximize your savings, you can pay all upfront and receive the largest discount. Partial Upfront RIs offer lower discounts, but they give you the option to spend less upfront.

Lastly, you can choose to spend nothing upfront and receive a smaller discount, which enables you to free capital to spend on other projects.

By using reserved capacity, your organization can minimize risks, more predictably manage budgets, and comply with policies that require longer-term commitments.

### 🟠 Pay less by using more

For services like **Amazon Simple StorageService (Amazon S3)**, pricing is tiered, which means that you pay less per GB when you use more.

In addition, data transfer inis always free.

Multiple storage services deliver lower storage costs based on your needs.

As a result, as your AWS usage needs increase, you benefit from the economies of scale that enable you to increase adoption and keep costs under control.

### 🟠 Pay even less as AWS grows

As AWS grows:

- AWS focuses on lowering cost of doing business
- This practice results in AWS passing savings from economies of scale to you.
- Since 2006, AWS has reduced prices over **75 times**.
- Newer, higher-performing resources often replace older ones **at no extra cost**.

### 🟠 Custom pricing

• For high-volume or unique projects, AWS provides **custom pricing agreements**.

### 🟠 AWS Free Tier

- New customers get **12 months of free usage** for selected services (e.g., EC2 t2.micro, S3, EBS, Load Balancer, data transfer).
- Designed to let users explore AWS at no initial cost.

### 🟠 Services with no charge

Some services are included at **no additional cost**, such as:

- **Amazon Virtual Private Cloud (Amazon VPC)** → enables you to provision a logically isolated section of the AWS Cloud where you can launch AWS resources in a virtual network that you define.
- **AWS Identity and Access Management (IAM)** → controls your users’ access to AWS services and resources.
- **Consolidated Billing** → is a billing feature in AWS Organizations to consolidate payment for multiple AWS accounts or multiple Amazon Internet Services Private Limited (AISPL) accounts*. Consolidated billing provides:•One bill for multiple accounts.
- The ability to **easily track each account’s charges**.
- The opportunity **to decrease charges as a result of volume pricing discounts** from combined usage.
- **Consolidate all of your accounts using Consolidated Billing and get tiered benefits.**
- **AWS Elastic Beanstalk** → is an even easier way for you to quickly deploy and manage applications in the AWS Cloud.
- **AWS CloudFormation** → gives developers and systems administrators an easy way to create a collection of related AWS resources and provision them in an orderly and predictable fashion.
- **Automatic Scalingautomatically** → adds or removes resources according to conditions you define. The resources you are using increase seamlessly during demand spikes to maintain performance and decrease automatically during demand lulls to minimize costs.
- **AWS OpsWorks** → is an application management service that makes it easy to deploy and operate applications of all shapes and sizes.

**Note:** The difference between **AWS accounts** and **AISPL accounts** (India) is the seller of record. AISPL bills in INR, while AWS Inc. bills in USD.
