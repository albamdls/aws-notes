# 📊 Module 2 - Cloud Economics and Billing

## 2️⃣ Section 2: Total Cost of Ownership

### 🟠 On-premises vs. cloud

- **On-Premises Infrastructure**
    - Installed locally on company hardware.
    - High **capital expenses**: facilities, hardware, licenses, IT staff.
    - **Scaling up** → expensive, time-consuming.
    - **Scaling down** → fixed costs remain.
- **Cloud Infrastructure**
    - Provided and maintained by AWS.
    - Pay only for what you use (**consumption-based model**).
    - Easy to scale up or down.
    - Costs are transparent and easier to estimate.

👉 On-premises focuses on **CapEx** (capital expenditure, long planning cycles).

👉 Cloud focuses on **OpEx** (operational expenditure, agility, and flexibility).

### 🟠 What is Total cost of Ownership (TCO)?

**Total Cost of Ownership (TCO)** is a financial estimate that is intended to help buyers and owners determine the direct and indirect costs of a product or system.

TCO includes the cost of a service, plus all the costs that are associated with owning the service.

**¿Why use TCO?**

- To compare the costs of running an **entire infrastructure environment or a specific workload** on-premises versus on AWS.
- To budget and **build the business case** for moving to the cloud

In resume, it helps to decide the most cost-effective deployment model.

### 🟠 TCO considerations

Some of the costs that are associated with data center management include:

- **Server costs for both hardware and software**, and facilities costs to house the equipment.
- **Storage costs for the hardware**, administration, and facilities.
- **Network costs for hardware**, administration, and facilities.
- **IT labor costs that are required to administer the entire solution**.

When you compare an on-premises to cloud solution, it is important to accurately assess the true costs of both options.

With the cloud, most costs are upfront and readily calculated. For example, cloud providers give transparent pricing based on different usage metrics, such as RAM, storage, and bandwidth, among others. Pricing is frequently fixed per unit of time.

**Resume:**

Key cost categories for data center management:

- **Servers**: hardware, software, facilities.
- **Storage**: hardware, administration, facilities.
- **Networking**: hardware, administration, facilities.
- **IT Labor**: ongoing operations and administration.

**Cloud**:

- Costs are upfront, transparent, based on metrics (RAM, storage, bandwidth).
- Easier to calculate and predict.

**On-Premises**:

- Costs are harder to determine, must include:
    - **Direct costs**: power, space, storage, IT operations.
    - **Indirect costs**: network, storage infrastructure, security, software, facilities, taxes, upgrades, admin staff.

### 🟠 On-premises versus all-in-cloud

- **On-Premises Setup**:
    - 1 VM, 4 CPUs, 16 GB RAM, Linux.
    - 100% utilization, optimized by RAM.
    - **3-year total cost**: $167,422.
- **AWS Setup**:
    - 1 m4.xlarge instance, 4 CPUs, 16 GB RAM.
    - 3-year **Partial Upfront Reserved Instance**.
    - **3-year total cost**: $7,509.
    - **Savings**: $159,913 (96% cheaper).

👉 **On-premises →** constant costs, even when unused.

👉 **AWS →** resources only billed when used, then decommissioned.

### 🟠 AWS Pricing Calculator

**AWS Pricing Calculator** help you to estimate a monthly AWS bill. You can use this tool to explore AWS services and create an estimate for the cost of your use cases on AWS. 

The **AWS Pricing Calculator** helps you:

- Estimate monthly costs of AWS services
- Identify opportunities for cost reduction
- Model your solutions before building them
- Explore price points and calculations behind your estimate
- Find the available instance types and contract terms that meet your needs

The AWS Pricing Calculator enables you to name your estimate and create and name groups of services. Groupsare containers that you add services to in order to organize and build your estimate. You can organize your groups and services by cost-center, department, product architecture, etc.

### 🟠 Reading an estimate

AWS Pricing Calculator estimates are broken into:

- **The total for your first 12 months** → The total estimate for your current group and all of the services and groups in your current group. It combines the upfront and monthly estimates.
- **Your total upfront** → How much you are estimated to pay upfront as you set up your AWS stack.
- **Your total monthly** → How much you're estimated to spend every month while you run your AWS stack.

Within a group, you can see how much each service is estimated to cost. If you want to price out different ways to build your AWS setup, you can use different groups for each variation of your setup and compare the estimates for the different setups. 

### 🟠 Additional benefit considerations

**Hard benefits (direct, measurable):**

- Lower spending on compute, storage, networking, security.
- Reduced hardware/software purchases.
- Lower operational costs (backup, disaster recovery).
- Reduced need for operations personnel.

**Soft benefits (indirect, harder to measure):**

- Service/application reuse with cloud tools.
- Higher developer productivity.
- Improved customer satisfaction.
- Agile processes → faster response to opportunities.
- Increased global reach.

👉 A full **ROI analysis** should consider **both hard and soft benefits**.
