# 🌐 Module 5 - Networking and Content Delivery

## 6️⃣ Section 6: Amazon CloudFront

---

### 🟠 Introduction

The purpose of networking is to **share information between connected resources**.
In this section, you’ll learn about **Amazon CloudFront**, AWS’s **Content Delivery Network (CDN)** service, which helps deliver content to users worldwide with **low latency and high transfer speeds**.

---

### 🟠 Network Latency and Content Delivery

When users access a website or stream a video, their requests pass through multiple routers across different networks before reaching the **origin server** — the source where the original data (HTML, CSS, JavaScript, media files) is stored.

#### ⚠️ **Challenges:**

* Each **network hop** increases latency.
* Performance varies across **geographic locations**.

💡 **Solution:** A **Content Delivery Network (CDN)** reduces latency by caching and serving content from **locations closer to the user**.

---

### 🟠 What is a Content Delivery Network (CDN)?

A **CDN** is a **globally distributed system of caching servers** that deliver both static and dynamic content faster to end users.

#### ⚙️ **Key Features:**

* **Caches copies** of commonly requested files (static content like HTML, CSS, JavaScript, and images).
* Delivers content from the **nearest Point of Presence (PoP)** to the user.
* **Accelerates dynamic content** that cannot be cached by routing requests efficiently.
* **Improves performance** and scalability of applications.
* Establishes **secure, low-latency connections** closer to users.

💡 **Result:** Faster response times, reduced load on origin servers, and improved user experience.

---

### 🟠 Amazon CloudFront Overview

**Amazon CloudFront** is a **fast, secure, and globally distributed CDN service** that delivers **data, videos, applications, and APIs** to users worldwide.

#### ⚙️ **Key Highlights:**

* **Global network** of edge locations and regional caches.
* **Self-service model** with **pay-as-you-go pricing**.
* **Delivers files over HTTP/HTTPS** to ensure security and reliability.

💡 Unlike traditional CDN contracts, CloudFront requires **no upfront commitments** or minimum fees — it scales automatically with your needs.

📚 Learn more: [Amazon CloudFront Documentation](https://aws.amazon.com/cloudfront/)

---

### 🟠 Amazon CloudFront Infrastructure

Amazon CloudFront delivers content through a **worldwide network of edge locations** and **regional edge caches**.

#### 📦 **Components:**

* **Edge Locations:**

  * Network of data centers located around the world.
  * Serve popular content **immediately** and with **low latency**.
* **Regional Edge Caches:**

  * Larger cache capacity than edge locations.
  * Store **less popular content longer** to reduce origin fetches.
  * Positioned **between the origin server and global edge locations**.

💡 **Performance Benefit:**
By caching content at multiple layers, CloudFront ensures faster delivery and fewer trips to the origin server.

📘 Learn more: [How CloudFront Delivers Content](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/HowCloudFrontWorks.html#HowCloudFrontWorksContentDelivery)

---

### 🟠 Amazon CloudFront Benefits

| Benefit                  | Description                                                                                                                                                    |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Fast and Global**      | CloudFront’s global infrastructure reduces latency using edge locations and regional caches.                                                                   |
| **Security at the Edge** | Built-in network and application protection (e.g., **AWS Shield Standard**) and support for **custom SSL/TLS certificates** via AWS Certificate Manager.       |
| **Highly Programmable**  | Supports customization using **Lambda@Edge**, allowing you to run code close to users for improved responsiveness. Integrates with DevOps and CI/CD pipelines. |
| **Deep AWS Integration** | Seamlessly integrates with AWS services (like S3, EC2, and Elastic Load Balancing) and shares the same global network backbone.                                |
| **Cost-Effective**       | No minimum fees or long-term commitments. You pay only for what you use. Efficient caching reduces load on origin servers and operational costs.               |

💡 **Example:** CloudFront collapses multiple simultaneous viewer requests for the same file into a single origin request, further reducing costs and latency.

---

### 🟠 Amazon CloudFront Pricing

You pay for **what you use**, based on four primary metrics:

1. **Data Transfer Out**

   * Charged per GB for data transferred from CloudFront edge locations to the internet or your origin.
   * Pricing varies by geographic region.

2. **HTTP(S) Requests**

   * Charged per request made to CloudFront for content delivery.

3. **Invalidation Requests**

   * First **1,000 paths per month** are free.
   * Beyond that, $0.005 per invalidation path.

4. **Dedicated IP Custom SSL**

   * $600 per month per SSL certificate used for Dedicated IP mode.
   * Charges are prorated by the hour.

📘 Example: If an SSL certificate is active for one day, the cost is `(1/30) × $600 = $20`.

📚 Learn more: [Amazon CloudFront Pricing](https://aws.amazon.com/cloudfront/pricing/)

---

### 🟢 Key Takeaways

✅ A **CDN** is a globally distributed network of caching servers that accelerates content delivery.
✅ **Amazon CloudFront** delivers data, videos, apps, and APIs securely with **low latency and high speeds**.
✅ It provides major benefits:

* 🌎 Fast and global
* 🛡️ Security at the edge
* ⚙️ Highly programmable
* 🔗 Deep AWS integration
* 💸 Cost-effective
