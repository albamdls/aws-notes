# ⚙️ **Module 10 - Automatic Scaling and Monitoring**  
## 1️⃣ **Section 1: Elastic Load Balancing (ELB)**

### 🟠 **Introduction**

Applications deployed in the cloud need to handle **variable traffic loads** while maintaining **availability** and **performance**.  
**Elastic Load Balancing (ELB)** automatically distributes incoming application traffic across multiple **targets** — such as Amazon EC2 instances, containers, IP addresses, or Lambda functions.

It ensures that no single component is overwhelmed, improving **fault tolerance**, **scalability**, and **user experience**.

---

### ⚖️ **What Is Elastic Load Balancing?**

**Elastic Load Balancing** is a fully managed service that:
- Distributes traffic evenly across multiple resources.  
- Monitors health and routes traffic only to healthy targets.  
- Scales automatically with changing traffic patterns.  
- Integrates with **Auto Scaling** and **CloudWatch** for performance and monitoring.  

🧠 *Example:*  
During a marketing campaign, ELB automatically balances millions of incoming requests across multiple EC2 instances running in different Availability Zones.

---

### 💡 **How ELB Works**

1. A user sends a request to your application (e.g., through a web browser).  
2. The request first reaches the **Elastic Load Balancer**.  
3. ELB checks the **health** of registered targets (EC2, containers, etc.).  
4. The load balancer forwards the request to one of the **healthy targets**.  
5. If a target becomes unhealthy, ELB automatically routes traffic to other healthy instances.

---

### 🧱 **Key Benefits of Elastic Load Balancing**

| **Benefit** | **Description** |
|--------------|-----------------|
| **High Availability** | Distributes traffic across multiple Availability Zones. |
| **Fault Tolerance** | Automatically reroutes traffic away from unhealthy targets. |
| **Scalability** | Handles varying traffic loads seamlessly. |
| **Security** | Integrates with AWS Certificate Manager (ACM) for HTTPS. |
| **Elasticity** | Works with Auto Scaling to dynamically adjust capacity. |
| **Monitoring** | Integrated with Amazon CloudWatch for metrics and health checks. |

🧠 *Tip:* ELB scales automatically — you don’t need to manually configure capacity.

---

### 🧩 **Types of Elastic Load Balancers**

AWS offers different load balancers for different workloads.

| **Type** | **Best For** | **Protocols Supported** | **Key Features** |
|-----------|---------------|--------------------------|------------------|
| **Application Load Balancer (ALB)** | Web applications and microservices. | HTTP, HTTPS, gRPC | Layer 7 routing, host/path-based routing, WebSocket support. |
| **Network Load Balancer (NLB)** | High-performance, low-latency apps. | TCP, UDP, TLS | Handles millions of requests per second with ultra-low latency. |
| **Gateway Load Balancer (GWLB)** | Third-party virtual appliances (firewalls, intrusion detection). | IP | Integrates third-party security and networking tools. |
| **Classic Load Balancer (CLB)** | Legacy applications. | HTTP, HTTPS, TCP | Basic load balancing across EC2 instances. |

🧠 *Example:*  
Use **ALB** for a modern web app with microservices, **NLB** for real-time gaming or financial trading, and **GWLB** for advanced network security.

---

### 🧰 **Application Load Balancer (ALB) Details**

**ALB** operates at **Layer 7 (Application Layer)** of the OSI model, routing requests based on content.

#### **Key Features**
- **Path-based routing**: `/images` → one target group, `/api` → another.  
- **Host-based routing**: `api.example.com` → one service, `shop.example.com` → another.  
- **Container integration** with Amazon ECS and EKS.  
- **WebSocket support** for real-time communication.  
- **SSL termination** with AWS Certificate Manager (ACM).

🧠 *Example:*  
A web app with microservices can route `/login` requests to the auth service and `/orders` to the order service automatically via ALB rules.

---

### ⚡ **Network Load Balancer (NLB) Details**

**NLB** operates at **Layer 4 (Transport Layer)** and is optimized for **high throughput and low latency**.

#### **Key Features**
- Handles **millions of requests per second**.  
- Supports **static IP addresses** and **Elastic IPs**.  
- Ideal for applications needing **TCP/UDP** or **TLS passthrough**.  
- Integrates with **PrivateLink** for secure access between VPCs.

🧠 *Example:*  
Use NLB for financial trading apps that require constant, fast TCP connections.

---

### 🛡️ **Gateway Load Balancer (GWLB)**

**GWLB** simplifies the deployment and scaling of **virtual network appliances** such as:
- Firewalls  
- Intrusion detection/prevention systems (IDS/IPS)  
- Deep packet inspection (DPI) tools  

#### **Key Features**
- Combines **transparent network gateway** + **load balancer**.  
- Uses **GENEVE** protocol for encapsulation.  
- Ensures traffic is inspected by appliances before reaching its destination.

🧠 *Use Case:*  
Organizations can deploy third-party firewall appliances (e.g., Palo Alto, Check Point) with GWLB for managed inspection at scale.

---

### 🧮 **Load Balancer Health Checks**

Each load balancer continuously monitors the health of its targets.

| **Health Check Type** | **Example** |
|------------------------|-------------|
| **HTTP(S) Check** | `/health` endpoint returns 200 OK. |
| **TCP Check** | Confirms that the port is open and responsive. |
| **Target Group Status** | Unhealthy targets are automatically removed until they recover. |

🧠 *Best Practice:* Configure multiple health check endpoints for redundancy and faster detection.

---

### 🧩 **Integration with Auto Scaling**

**Elastic Load Balancing** integrates seamlessly with **Amazon EC2 Auto Scaling**:
- ELB automatically registers new instances when they launch.  
- Deregisters instances when they terminate.  
- Ensures only **healthy instances** receive traffic.  

🧠 *Result:* Fully elastic, self-healing architecture — your app scales automatically without downtime.

---

### 🔐 **Security Features**

- **HTTPS/TLS support** with **AWS Certificate Manager**.  
- **Security groups** control inbound and outbound traffic.  
- **Integration with WAF and Shield** for DDoS protection.  
- **Access logs** capture detailed request information for analysis.  

🧠 *Tip:* Enable **access logging** and **CloudWatch metrics** to analyze performance and detect anomalies.

---

### 🧠 **Key Takeaways**

- **Elastic Load Balancing (ELB)** automatically distributes traffic across multiple targets.  
- Provides **fault tolerance**, **high availability**, and **elastic scalability**.  
- Choose **ALB** for HTTP/S apps, **NLB** for TCP/UDP workloads, **GWLB** for network appliances, and **CLB** for legacy systems.  
- **Integrates with Auto Scaling and CloudWatch** for a fully automated architecture.  
- Supports **encryption**, **DDoS protection**, and **access logging** for secure operations.  
- A core building block for resilient, scalable AWS architectures.  