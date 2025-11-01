# 🌐 Module 5 - Networking and Content Delivery

## 2️⃣ Section 2: Amazon Virtual Private Cloud (Amazon VPC)

---

### 🟠 What is Amazon VPC?

**Amazon Virtual Private Cloud (Amazon VPC)** enables you to provision a **logically isolated section of the AWS Cloud** where you can launch AWS resources in a virtual network that **you define and control**.

🔹 **Key capabilities:**

* Selection of your **own IP address range**.
* **Creation of subnets** within the VPC.
* **Configuration of route tables** and network gateways.
* Use of **IPv4 and IPv6** for secure access to resources.
* Multiple layers of **network security** using **security groups** and **network ACLs**.

📘 Example setup:

* **Public subnet** → web servers that access the internet.
* **Private subnet** → backend systems (databases, application servers) without internet access.

✅ **Amazon VPC provides full control** over your virtual networking environment, similar to running your own data center but with the scalability of AWS.

---

### 🟠 VPCs and Subnets

A **VPC** is a **virtual network** isolated from other VPCs in the AWS Cloud.

#### 📋 **VPC characteristics:**

* Logically isolated from other VPCs.
* Dedicated to your AWS account.
* Belongs to a **single Region** but can **span multiple Availability Zones (AZs)**.

#### 📋 **Subnets characteristics:**

* A **range of IP addresses** that divides a VPC into smaller networks.
* Each subnet belongs to **a single Availability Zone**.
* **Classified as:**

  * **Public subnet** → direct internet access.
  * **Private subnet** → no internet access.

💡 Best practice: Create **subnets in multiple AZs** for **high availability** and fault tolerance.

---

### 🟠 IP Addressing in a VPC

When you create a VPC, you must assign an **IPv4 CIDR block** (range of private IPv4 addresses).

🔹 **Important notes:**

* CIDR block cannot be changed after creation.
* CIDR block size limits:

  * **Largest:** `/16` → 65,536 addresses.
  * **Smallest:** `/28` → 16 addresses.
* **IPv6** addressing is also supported.
* **Subnet CIDR blocks cannot overlap.**
* No **duplicate IP addresses** are allowed in the same VPC.

🧮 **Example:**
A VPC with a `/16` block (65,536 IPs) can be divided into `/24` subnets (256 IPs each).

📚 Learn more: [AWS VPC Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/what-is-amazon-vpc.html)

---

### 🟠 Reserved IP Addresses

When you create a **subnet**, AWS reserves **five IP addresses** in each subnet’s CIDR block that cannot be used.

| Reserved For      | Example (CIDR 10.0.0.0/24) | Description                  |
| ----------------- | -------------------------- | ---------------------------- |
| Network address   | 10.0.0.0                   | Identifies the subnet itself |
| VPC local router  | 10.0.0.1                   | For internal communication   |
| DNS resolution    | 10.0.0.2                   | AWS-provided DNS             |
| Future use        | 10.0.0.3                   | Reserved for AWS use         |
| Broadcast address | 10.0.0.255                 | Used for broadcast traffic   |

💡 Example: A subnet with `/24` CIDR block (256 addresses) → **251 available** for use.

---

### 🟠 Public IP Address Types

Each instance in a VPC automatically receives a **private IP address**. You can also assign **public IPs** for internet access.

#### 📋 **Types of public IP addresses:**

* **Public IPv4 address** → Automatically or manually assigned at the subnet level.
* **Elastic IP address (EIP):**

  * Static, public IPv4 address tied to your AWS account.
  * Can be allocated, reassigned, or released anytime.
  * Allows quick recovery by **remapping** to another instance.
  * Additional costs may apply — release unused EIPs to avoid charges.

💡 Associating an **Elastic IP with a network interface** allows you to move all its attributes between instances in one step.

📚 Learn more: [Elastic IP Addresses Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-eips.html)

---

### 🟠 Elastic Network Interface (ENI)

An **Elastic Network Interface (ENI)** is a **virtual network interface** that you can:

* Attach to an instance.
* Detach from an instance and reattach to another.

🔹 **Key points:**

* ENI attributes (IP, MAC, security group) **move with it** when reattached.
* Each instance has a **primary ENI** (default, non-detachable).
* Additional ENIs can be created and attached depending on instance type.

📚 Learn more: [Elastic Network Interface Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html)

---

### 🟠 Route Tables and Routes

A **route table** defines how **network traffic is directed** from subnets within your VPC.

#### 📋 **Key concepts:**

* A **route** specifies:

  * **Destination** → CIDR block of target network.
  * **Target** → where to send traffic (e.g., internet gateway, NAT gateway).
* Each route table contains a **default local route** for internal VPC communication.
* Every **subnet must be associated** with exactly one route table.

#### 🧭 **Main route table:**

* Automatically created with the VPC.
* Controls routing for subnets not explicitly linked to another route table.
* You can **add custom routes**, but **cannot delete the local route**.

📚 Learn more: [VPC Route Tables Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_Route_Tables.html)

---

### 🟢 Key Takeaways

✅ A **VPC** is a logically isolated section of the AWS Cloud.
✅ Each **VPC belongs to one Region** and requires a **CIDR block**.
✅ **Subnets** divide a VPC and each belong to one Availability Zone.
✅ **Route tables** control traffic within and outside subnets.
✅ Each route table includes a **default local route** that cannot be deleted.
