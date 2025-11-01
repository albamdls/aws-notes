# 🌐 Module 5 - Networking and Content Delivery

## 4️⃣ Section 4: Securing Your VPC

---

### 🟠 Security Groups

A **security group** acts as a **virtual firewall** for your Amazon EC2 instances, controlling **inbound and outbound traffic**.

#### ⚙️ Key Characteristics:

* Operates at the **instance level** (not at the subnet level).
* Each instance in a subnet can have **different security groups**.
* Used to **filter traffic** to and from your instances.

📘 **Default behavior:**

* Denies **all inbound traffic**.
* Allows **all outbound traffic**.

---

### 🟠 Security Group Rules

| Direction    | Default Behavior | Customization                                              | Notes                                                       |
| ------------ | ---------------- | ---------------------------------------------------------- | ----------------------------------------------------------- |
| **Inbound**  | Denied           | Add rules to allow specific sources, ports, and protocols. | Each rule specifies Source → Protocol → Port → Description. |
| **Outbound** | Allowed          | You can restrict or specify targets for traffic.           | If no outbound rules exist, no outbound traffic is allowed. |

🔹 **Stateful behavior:**

* Return traffic is **automatically allowed**, even if no explicit rule exists.
* Example: If an instance sends a request, the response traffic is allowed in.

🧱 **Example Default Rules:**

| Type     | Source/Destination | Protocol | Port Range | Description                              |
| -------- | ------------------ | -------- | ---------- | ---------------------------------------- |
| Inbound  | sg-xxxxxxxx        | All      | All        | Allow inbound from interfaces in same SG |
| Outbound | 0.0.0.0/0          | All      | All        | Allow all IPv4 outbound                  |
| Outbound | ::/0               | All      | All        | Allow all IPv6 outbound                  |

---

### 🟠 Custom Security Group Examples

You can specify **allow rules only** — **deny rules are not supported**.
All rules are evaluated before deciding whether to allow traffic.

#### ✅ **Inbound Rules:**

| Source                           | Protocol | Port | Description                         |
| -------------------------------- | -------- | ---- | ----------------------------------- |
| 0.0.0.0/0                        | TCP      | 80   | Allow HTTP traffic from all IPv4    |
| 0.0.0.0/0                        | TCP      | 443  | Allow HTTPS traffic from all IPv4   |
| Your network’s public IPv4 range | TCP      | 22   | Allow SSH access to Linux instances |

#### ✅ **Outbound Rules:**

| Destination    | Protocol | Port | Description                       |
| -------------- | -------- | ---- | --------------------------------- |
| Database SG ID | TCP      | 1433 | Allow Microsoft SQL Server access |

💡 **Best practice:** Limit inbound SSH access to specific trusted IP ranges and use security groups as logical firewalls between application tiers.

---

### 🟠 Network Access Control Lists (Network ACLs)

A **Network ACL (Access Control List)** provides an **additional layer of security** at the **subnet level**.
It acts as a **firewall** for controlling inbound and outbound traffic to and from subnets.

#### ⚙️ Key Characteristics:

* Operates at the **subnet level**.
* Each subnet must be associated with **one** network ACL.
* A single network ACL can be associated with **multiple subnets**.
* If not specified, subnets are automatically associated with the **default network ACL**.

📘 When you associate a new ACL with a subnet, the previous one is **replaced**.

---

### 🟠 Network ACL Rules

| Feature         | Description                                                                         |
| --------------- | ----------------------------------------------------------------------------------- |
| **Rule Types**  | Separate inbound and outbound rules. Each can either **allow** or **deny** traffic. |
| **Default ACL** | Allows all inbound and outbound IPv4 (and IPv6) traffic.                            |
| **Stateless**   | Return traffic must be explicitly allowed by rules.                                 |

🧱 **Example Default ACL:**

| Direction | Rule # | Type | Protocol | Port | Source/Destination | Action |
| --------- | ------ | ---- | -------- | ---- | ------------------ | ------ |
| Inbound   | 100    | All  | All      | All  | 0.0.0.0/0          | ALLOW  |
| Inbound   | *      | All  | All      | All  | 0.0.0.0/0          | DENY   |
| Outbound  | 100    | All  | All      | All  | 0.0.0.0/0          | ALLOW  |
| Outbound  | *      | All  | All      | All  | 0.0.0.0/0          | DENY   |

---

### 🟠 Custom Network ACL Examples

Custom ACLs deny all traffic by default until you add rules.
Rules are evaluated in **ascending order**, starting from the lowest number.

#### ✅ Example Configuration:

| Direction | Rule # | Type  | Protocol | Port | Source/Destination | Action |
| --------- | ------ | ----- | -------- | ---- | ------------------ | ------ |
| Inbound   | 100    | HTTPS | TCP      | 443  | 0.0.0.0/0          | ALLOW  |
| Inbound   | 120    | SSH   | TCP      | 22   | 192.0.2.0/24       | ALLOW  |
| Inbound   | *      | All   | All      | All  | 0.0.0.0/0          | DENY   |
| Outbound  | 100    | HTTPS | TCP      | 443  | 0.0.0.0/0          | ALLOW  |
| Outbound  | 120    | SSH   | TCP      | 22   | 192.0.2.0/24       | ALLOW  |
| Outbound  | *      | All   | All      | All  | 0.0.0.0/0          | DENY   |

💡 **Rule numbering tip:** Use increments of **10 or 100** so new rules can be inserted easily later.

📚 Learn more: [Network ACLs Documentation](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)

---

### 🟠 Security Groups vs Network ACLs

| Attribute           | Security Groups              | Network ACLs                    |
| ------------------- | ---------------------------- | ------------------------------- |
| **Scope**           | Instance level               | Subnet level                    |
| **Rules Supported** | Allow rules only             | Allow **and** deny rules        |
| **State**           | Stateful                     | Stateless                       |
| **Evaluation**      | All rules evaluated together | Rules evaluated by number order |

💡 **Summary:**

* Security groups = micro-level protection (instances).
* Network ACLs = macro-level protection (subnets).

---

### 🧩 Activity: Design a Secure VPC

**Scenario:**
You are a small business owner hosting a website on an EC2 instance. Customer data is stored on a backend database that must remain private.

#### 🧱 **Requirements:**

* Separate web and database servers into different subnets.
* Network must start at **10.0.0.0**, with **256 IPv4 addresses per subnet**.
* Customers must always have access to the web server.
* Database server must access the internet for patch updates.
* Architecture must be **highly available** and include **at least one custom firewall layer**.

🧠 **Hint:** Combine security groups for instance-level protection with network ACLs for subnet-level protection.

---

### 🟢 Key Takeaways

✅ Build **security into every layer** of your VPC architecture.
✅ **Isolate subnets** when possible for better protection.
✅ Use the **appropriate gateway or VPN connection** for your needs.
✅ Apply **firewall rules** through **security groups** and **network ACLs** to safeguard traffic.
