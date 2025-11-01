# 🌐 Module 5 - Networking and Content Delivery

## 3️⃣ Section 3: VPC Connectivity Options

---

### 🟠 AWS Site-to-Site VPN

By default, instances launched in a VPC **cannot communicate with remote networks**. To connect your VPC to an on-premises or remote data center, you can set up a **Site-to-Site VPN connection**.

#### ⚙️ Steps to create a VPN connection:

1. **Create a Virtual Private Gateway (VGW):** Attach it to your VPC.
2. **Define a Customer Gateway:** Provides AWS with information about your VPN device.
3. **Configure route tables:** Direct traffic destined for your corporate network to the VGW.
4. **Establish a Site-to-Site VPN connection:** Links the two networks securely.
5. **Update security groups and routing rules** to allow communication.

📘 Learn more: [AWS VPN Connections Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/vpn-connections.html)

💡 **Example:**

| Subnet         | Route Table | Destination     | Target |
| -------------- | ----------- | --------------- | ------ |
| Public Subnet  |             | 10.0.0.0/16     | local  |
|                |             | 0.0.0.0/0       | igw-id |
| Private Subnet |             | 10.0.0.0/16     | local  |
|                |             | 192.168.10.0/24 | vgw-id |

---

### 🟠 AWS Direct Connect (DX)

**AWS Direct Connect (DX)** provides a **dedicated, private network connection** between your on-premises data center and AWS.

#### 💡 Benefits:

* Reduces **network latency** caused by distance.
* **Increases bandwidth** throughput.
* Provides a **more consistent network experience** than internet-based VPNs.
* Uses the **IEEE 802.1Q VLAN standard** for virtual local area networks.

📚 Learn more: [AWS Direct Connect](https://aws.amazon.com/directconnect/)

🧩 **Use case:** Ideal for organizations with high-volume data transfers or latency-sensitive workloads between AWS and their data centers.

---

### 🟠 VPC Endpoints

A **VPC endpoint** allows private connectivity between your VPC and supported AWS services **without using the internet**, VPN, or Direct Connect.

🔒 **Traffic never leaves the AWS network.** Instances in the VPC **do not require public IPs** to access these services.

#### 🧩 Two types of endpoints:

1. **Interface Endpoints** (powered by AWS PrivateLink)

   * Connect to AWS services, partner services, or other customers' VPCs.
   * Each connection creates an **Elastic Network Interface (ENI)** with a private IP address.
   * You are charged per endpoint hour + data processing.
   * Example: Amazon EC2 API endpoint.

2. **Gateway Endpoints**

   * Free to use (no hourly charge).
   * Used for **Amazon S3** and **Amazon DynamoDB**.
   * Add a route to the route table targeting the gateway endpoint.

📚 Learn more: [VPC Endpoints Documentation](https://docs.aws.amazon.com/vpc/latest/privatelink/concepts.html)

---

### 🟠 AWS Transit Gateway

As organizations grow, they often have **hundreds of VPCs** across multiple AWS accounts and Regions. Managing point-to-point connections between them (via VPN or VPC peering) becomes complex.

**AWS Transit Gateway (TGW)** simplifies this by acting as a **central hub** that connects multiple VPCs, on-premises networks, and remote offices using a **hub-and-spoke model**.

#### ⚙️ Benefits of AWS Transit Gateway:

* Centralized control of **connectivity policies**.
* Simplified management and reduced operational cost.
* Scalable to connect **multiple networks** efficiently.
* Each network connects only once—to the transit gateway—and becomes reachable by all others.

📚 Learn more: [AWS Transit Gateway Documentation](https://docs.aws.amazon.com/vpc/latest/tgw/what-is-transit-gateway.html)

💡 **Hub-and-Spoke Model:**

```
     +--------------------+
     |  AWS Transit GW   |
     +--------------------+
      /      |      \   
 VPC A   VPC B   On-Premises
```

---

### 🧠 Activities

#### 🔹 Network Diagram Exercise

Identify and label the VPC components such as:

* Internet gateway (IGW)
* NAT gateway
* Elastic Network Interface (ENI)
* Route tables (public and private)
* Subnets (public and private)
* IP address ranges

✅ **Solution Overview:**

* Public Subnet: 10.0.1.0/24 (uses IGW)
* Private Subnet: 10.0.2.0/24 (uses NAT Gateway)
* Local route: 10.0.0.0/16
* Default route: 0.0.0.0/0 → IGW

#### 🎥 AWS VPC Demonstration

Watch the recorded demo: [AWS VPC Wizard Demo](https://aws-tc-largeobjects.s3-us-west-2.amazonaws.com/ILT-TF-100-ACFNDS-20-EN/Module_5_VPC_Wizard+v2.0.mp4)

Learn how to use the **VPC Wizard** to create a VPC with public and private subnets.

---

### 🟢 Key Takeaways

✅ AWS provides multiple VPC connectivity options:

* **Internet Gateway (IGW):** Connects your VPC to the internet.
* **NAT Gateway:** Allows private subnets to connect to the internet securely.
* **VPC Endpoint:** Connects your VPC privately to AWS services.
* **VPC Peering:** Connects two VPCs directly.
* **VPC Sharing:** Allows multiple AWS accounts to share a single centrally managed VPC.
* **AWS Site-to-Site VPN:** Connects your VPC to on-prem networks securely.
* **AWS Direct Connect:** Provides dedicated physical connectivity.
* **AWS Transit Gateway:** Central hub for multi-VPC and on-prem connectivity.

✅ Use the **VPC Wizard** to implement and test your network design efficiently.
