# 🌎 Module 3 - AWS Global Infrastructure Overview

## 1️⃣ Section 1: AWS Global Infrastructure

### 🟠 AWS Global Infrastructure

- Designed for: **flexibility, reliability, scalability, security**.
- Provides **high-quality global network performance**.

### 🟠 AWS Regions

- AWS has **22 Regions worldwide**.
- **Region** = geographical location with one or more **Availability Zones (AZs)**.
- **Availability Zones** = one or more **data centers**.
- **Isolation**:
    - Regions are independent for **fault tolerance** and **stability**.
    - Resources are **not automatically replicated** across Regions.
    - If replication is required, the **customer is responsible**.
- **Region enablement**:
    - Regions before **March 20, 2019** → enabled by default.
    - Regions after (e.g., Hong Kong, Bahrain) → must be manually enabled.
- **Restricted Regions**:
    - **China (Beijing, Ningxia)** → only with AWS China accounts.
    - **AWS GovCloud (US)** → for US government workloads, regulatory compliance.

### 🟠 Selecting a Region

When choosing a Region, consider:

1. **Data governance & legal requirements**
    - Example: EU Data Protection Directive may restrict where data can be stored.
2. **Latency**
    - Best practice: choose a Region **closest to your users/systems**.
    - Tool: [CloudPing](http://www.cloudping.info/) → measure latency to Regions.
3. **Service availability**
    - Not all services are in all Regions → check before deploying.
4. **Cost variation**
    - Example (On-Demand EC2 t3.medium, Linux):
        - **US East (Ohio)**: $0.0416/hour
        - **Asia Pacific (Tokyo)**: $0.0544/hour

### 🟠 Availability Zones

- Each Region has multiple **AZs** (usually 3).
- **AZ features**:
    - Isolated locations with their own power and infrastructure.
    - Physically separated by **many kilometers**, but within **100 km**.
    - Contain **multiple data centers** (up to hundreds of thousands of servers).
    - Connected with **high-bandwidth, low-latency, redundant fiber**.
    - Support **synchronous replication**.
- **Benefits**:
    - Build apps that are **highly available, fault tolerant, and scalable**.
    - Protects against local disasters (e.g., lightning, tornadoes, earthquakes).
- **Best practices**:
    - Distribute systems across **multiple AZs**.
    - Design apps to survive **temporary or prolonged AZ failures**.

### 🟠 AWS data centers

- **Most granular choice** customers can make = **AZ**, not individual data centers.
- Data centers = actual **physical sites** where data resides.
- **Design principles**:
    - Sites chosen to **reduce environmental risk**.
    - Redundant design anticipating/tolerating failures.
    - Critical systems **backed up across AZs**.
    - Continuous monitoring ensures capacity.
    - Locations are **undisclosed** and access is restricted.
    - Automated failover → reroutes traffic during failures.
- **Technology**: AWS uses **custom-built networking equipment** from multiple **Original Device Manufacturers (ODMs)**.

### 🟠 Points of Presence

Amazon CloudFront is a content delivery network (CDN) used to distribute content to end users to reduce latency.

Amazon Route 53 is a Domain Name System (DNS) service.Requests going to either one of these services will be routed to the nearest edge location automatically in order to lower latency.

- Support services like:
    - **Amazon CloudFront** (CDN).
    - **Amazon Route 53** (DNS).
    - **AWS Shield**.
    - **AWS WAF**.
- Located in **major cities worldwide**.
- Purpose:
    - Route requests to the **nearest edge location** to reduce latency.
    - Continuously optimize connectivity and routing.
- **Regional Edge Caches**:
    - Store less frequently accessed content.
    - Reduce need to fetch data from the origin server.

### 🟠 AWS infrastructure features

The AWS Global Infrastructure has several valuable features:

- First, it is elasticand scalable. This means resources can dynamically adjust to increases or decreases in capacity requirements. It can also rapidly adjust to accommodate growth.
- Second, this infrastructure is fault tolerant, which means it has built-in component redundancy which enables it to continue operations despite a failed component.
- Finally, it requires minimal to no human intervention, while providing high availability with minimal down time.

**Resume:**

- **Elastic & Scalable** → resources adjust dynamically to demand.
- **Fault Tolerant** → redundancy ensures continued operation despite failures.
- **Highly Available & Automated** → minimal downtime, minimal human intervention.