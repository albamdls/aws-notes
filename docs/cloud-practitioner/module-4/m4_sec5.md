# 🛡️ Module 4 - AWS Cloud Security  

## 5️⃣ Section 5: Securing Data on AWS

### 🟠 Encryption of Data at Rest

**Data encryption** is an essential tool for protecting digital information.  
It converts readable data into an unreadable format using a **secret key**.  
Even if an attacker gains access to the data, they cannot interpret it without the key.

**Data at rest** refers to information **physically stored** on disk or tape.  

AWS allows you to create **encrypted file systems** so that all data and metadata are automatically encrypted using the **Advanced Encryption Standard (AES)-256** algorithm.

When using **AWS Key Management Service (KMS)**, encryption and decryption are handled **automatically and transparently**, meaning you don’t need to modify your applications.

If your organization is subject to **corporate or regulatory policies** that require encryption, AWS recommends enabling encryption on **all services** that store data.

🔗 See supported services: [How AWS Services Use AWS KMS](https://docs.aws.amazon.com/kms/latest/developerguide/service-integration.html)

---

### 🟠 Encryption of Data in Transit

**Data in transit** refers to data **moving across networks**.  
It is protected using **Transport Layer Security (TLS) 1.2** with **AES-256 encryption**.  
TLS was formerly known as **Secure Sockets Layer (SSL)**.

**AWS Certificate Manager (ACM)** allows you to provision, manage, and deploy **SSL/TLS certificates** to secure network communications and verify the identity of websites and resources.

**Key points:**

- HTTPS (TLS/SSL) protects traffic from **eavesdropping** and **man-in-the-middle attacks**.  
- AWS Certificate Manager also **handles certificate renewals automatically**.  
- HTTP traffic is not secure; always use **HTTPS** instead.

**Examples of encryption in transit:**

1. 🧩 An **EC2 instance** mounting an **Amazon EFS shared file system** — all data traffic is encrypted using TLS/SSL.  
   📘 Learn more: [Encryption of EFS Data in Transit](https://docs.aws.amazon.com/whitepapers/latest/efs-encrypted-file-systems/encryption-of-data-in-transit.html)

2. 🗄️ **AWS Storage Gateway** connecting on-premises infrastructure to **Amazon S3** — data is encrypted while traveling over the Internet.

---

### 🟠 Securing Amazon S3 Buckets and Objects

By default, **Amazon S3 buckets are private** and accessible only to users who are explicitly granted access.

**Best Practices for S3 Security:**

- 🚫 **Enable Amazon S3 Block Public Access**  
  - Overrides all other permissions or bucket policies.  
  - Prevents accidental public exposure of S3 data.

- 🧾 **Use IAM policies**  
  - Define which users or roles can access specific buckets and objects.

- 📜 **Use Bucket Policies**  
  - Define access permissions directly on the bucket.  
  - Useful when IAM authentication is not available.  
  - Bucket policies can grant **cross-account access** or **public access**, but must be written carefully.

- ❌ **Use Access Control Lists (ACLs)** only when necessary  
  - ACLs are an older access mechanism that predates IAM.  
  - Avoid overly permissive ACLs.

- 🔍 **Use AWS Trusted Advisor**  
  - Check for bucket permissions that may allow **global access**.
