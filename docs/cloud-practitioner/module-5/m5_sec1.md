# 🌐 Module 5 - Networking and Content Delivery

## 1️⃣ Section 1: Networking Basics

In this section, we review fundamental networking concepts that form the foundation for understanding **Amazon Virtual Private Cloud (Amazon VPC)**.

---

### 🟠 What is a Network?

A **computer network** is a connection of **two or more client machines** that share resources.

🔹 **Key concepts:**

* A network can be **logically partitioned** into smaller units called **subnets**.
* **Networking devices** (such as routers and switches) connect clients and enable communication between them.

📘 **Example:**

```
Subnet 1  ↔  Router  ↔  Subnet 2
```

---

### 🟠 IP Addresses

Each device in a network has a **unique Internet Protocol (IP) address** that identifies it.

* IP addresses are written in **decimal format** (e.g., `192.0.2.0`) but are stored in **binary** by machines.
* Each IP address consists of **four octets**, separated by dots (`.`).
* Each octet = **8 bits** → ranges from **0 to 255**.
* Total = **32 bits** in binary (4 × 8).

💡 **Example:**
`192.0.2.0` = 11000000.00000000.00000010.00000000

---

### 🟠 IPv4 vs IPv6

| Version  | Bit Length | Example                                   | Description                                     |
| -------- | ---------- | ----------------------------------------- | ----------------------------------------------- |
| **IPv4** | 32 bits    | `192.0.2.0`                               | Older standard, supports ~4.3 billion addresses |
| **IPv6** | 128 bits   | `2600:1f18:22ba:8c00:ba86:a05e:a5ba:00FF` | Newer standard, supports vastly more devices    |

🔹 **IPv6 address format:**

* 8 groups of 4 hexadecimal characters separated by colons (`:`).
* Each group = **16 bits** → range from `0000` to `FFFF`.
* Total = **128 bits** in binary.

✅ **IPv6 enables more scalability** to accommodate the growing number of internet-connected devices.

---

### 🟠 Classless Inter-Domain Routing (CIDR)

**CIDR (Classless Inter-Domain Routing)** is a notation used to describe a **range of IP addresses**.

📘 **CIDR format:**

```
<IP Address>/<Prefix Length>
```

For example: `192.0.2.0/24`

🔹 **How it works:**

* The number after the slash (`/`) indicates how many bits are **fixed** for the network identifier.
* The remaining bits are **variable** (host identifiers).

#### 🧮 Example:

| CIDR           | Fixed Bits | Flexible Bits | Address Range               | Total IPs |
| -------------- | ---------- | ------------- | --------------------------- | --------- |
| `192.0.2.0/24` | 24         | 8             | `192.0.2.0 – 192.0.2.255`   | 256       |
| `192.0.2.0/16` | 16         | 16            | `192.0.0.0 – 192.0.255.255` | 65,536    |

#### ⚙️ Special CIDR Cases:

* `192.0.2.0/32` → Only **one** fixed IP (useful for firewall rules).
* `0.0.0.0/0` → Represents **all IP addresses on the internet**.

💡 CIDR simplifies routing and allocation of IP addresses by grouping consecutive addresses efficiently.

---

### 🟠 OSI Model (Open Systems Interconnection)

The **OSI model** is a conceptual framework that describes how **data travels through a network**.

It consists of **7 layers**, each responsible for specific functions and protocols.

| Layer | Name         | Function                                 | Common Protocols / Addresses |
| ----- | ------------ | ---------------------------------------- | ---------------------------- |
| **7** | Application  | Interface for apps to access the network | HTTP(S), FTP, DHCP, LDAP     |
| **6** | Presentation | Data formatting, encryption, translation | ASCII, ICA                   |
| **5** | Session      | Manages sessions and data exchange       | NetBIOS, RPC                 |
| **4** | Transport    | End-to-end communication between hosts   | TCP, UDP                     |
| **3** | Network      | Routing and packet forwarding            | IP                           |
| **2** | Data Link    | Transfers data within same LAN           | MAC, Bridges, Switches       |
| **1** | Physical     | Transmits raw bits over medium           | Electrical signals, Hubs     |

🧩 **Key Notes:**

* **Routers** operate at **Layer 3 (Network)**.
* **Switches and bridges** operate at **Layer 2 (Data Link)**.
* **Hubs** work at **Layer 1 (Physical)**.

💬 The OSI model helps you understand how communication happens inside **Amazon VPC**, which will be covered next.

---

### 🟢 Key Takeaways

✅ A **network** connects devices to share resources and can be divided into **subnets**.
✅ Each device has a **unique IP address** (IPv4 or IPv6).
✅ **CIDR notation** defines IP address ranges using a prefix (e.g., `/24`).
✅ The **OSI model** describes how data moves through seven network layers.
✅ These fundamentals are essential for understanding **Amazon VPC** and AWS networking.
