# 🛡️ Module 4 - AWS Cloud Security  

## 4️⃣ Section 4: Securing Accounts

### 🟠 AWS Organizations

**AWS Organizations** is an account management service that enables you to consolidate multiple AWS accounts into a single **organization** that you create and centrally manage.

This section focuses on the **security features** provided by AWS Organizations.

**Key security capabilities include:**

- 🧱 **Grouping accounts** into *Organizational Units (OUs)* and attaching **different access policies** to each OU.  
  Example: If you have accounts that should only access AWS services that meet certain **regulatory requirements**, you can group them into one OU and attach a policy that **blocks access** to non-compliant services.

- 🔐 **Integration with AWS Identity and Access Management (IAM)**:  
  AWS Organizations extends IAM control to the account level, allowing you to define what **users and roles** in an account (or group of accounts) can do.

- ⚙️ **Permission intersection**:  
  Effective permissions are determined by the intersection between:
  - The **AWS Organizations policy settings** (e.g., Service Control Policies), and  
  - The **IAM policies** applied within the account.  
  A user can access only what is allowed by **both** policy types.

- 🛡️ **Service Control Policies (SCPs)**:  
  These define the **maximum permissions** that member accounts in the organization can have.  
  SCPs can **restrict access** to specific AWS services, resources, or API actions.  
  Even administrators in member accounts cannot override these restrictions.

When AWS Organizations blocks access to a service, resource, or API action, **no user or role** in that account can access it — even if an admin explicitly grants permission.

---

### 🟠 AWS Organizations: Service Control Policies (SCPs)

SCPs provide **centralized control** over the maximum available permissions for all accounts within an organization.  
They ensure that every account operates within the organization’s access control boundaries.

**Key details:**

- SCPs are available **only when all features are enabled**, including **consolidated billing**.  
  📘 Learn more: [Enable All Features in AWS Organizations](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_org_support-all-features.html)

- SCPs are **not available** if the organization uses only consolidated billing features.

- For instructions on enabling and managing SCPs, see:  
  [Enabling and Disabling a Policy Type on a Root](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies.html#enable_policies_on_root.SCPs)

**Comparison to IAM Policies:**

| Feature | Service Control Policy (SCP) | IAM Policy |
|----------|------------------------------|-------------|
| Purpose | Defines **maximum permissions** within an organization | Grants or denies permissions to specific identities |
| Syntax | JSON (similar to IAM policies) | JSON |
| Scope | Organization, Root, or OU level | Account or Resource level |
| Grants permissions? | ❌ No (it only limits) | ✅ Yes |

**Important notes:**
- Attaching an SCP to the **organization root** or an **OU** sets a **boundary** for what member accounts can do.  
- SCPs **do not replace IAM** — you still need to attach IAM policies to actually grant access.

Learn more about IAM policies:  
📘 [AWS IAM Policies Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html)

---

### 🟠 AWS Key Management Service (AWS KMS)

**AWS Key Management Service (AWS KMS)** enables you to **create, manage, and control encryption keys** used across AWS services and applications.

**Key characteristics:**

- 🧩 Uses **Hardware Security Modules (HSMs)** that are validated (or in the process of validation) under **Federal Information Processing Standards (FIPS) 140-2**.  
- 🔐 Provides **secure and resilient** key management infrastructure.  
- 🧾 Integrates with **AWS CloudTrail** to log all key usage for compliance and auditing.  
- 🪪 Manages **Customer Master Keys (CMKs)** that control access to **Data Encryption Keys (DEKs)**.  
- 🔄 You can **create, import, or rotate keys** as needed.  
- 🌐 Integrates with most AWS services (e.g., S3, EBS, RDS, Lambda) to manage encryption.

**Learn more:**  
📘 [AWS Key Management Service Features](https://aws.amazon.com/kms/features/)

---

### 🟠 Amazon Cognito

**Amazon Cognito** provides secure solutions for **user authentication and access control** within your applications.

**Core functionalities:**

- 🧍‍♂️ **Role-based access**: You can define roles and map users to roles, ensuring that applications access only authorized AWS resources.  
- 🌍 **Support for SAML 2.0 (Security Assertion Markup Language)**:  
  Cognito uses SAML — an open standard for exchanging **identity and security information** between identity providers and applications.  
  - Supports **Single Sign-On (SSO)** using corporate credentials (e.g., from Microsoft Active Directory).  
  - Enables seamless authentication across multiple applications.

**Compliance and Regulatory Support:**

Amazon Cognito helps organizations meet multiple **security and compliance requirements**, including those for **highly regulated industries** such as healthcare and finance.

**Compliance frameworks supported:**  
- 🏥 **HIPAA** – [AWS HIPAA Compliance](https://aws.amazon.com/compliance/hipaa-compliance/)  
- 💳 **PCI DSS** – [AWS PCI DSS FAQs](https://aws.amazon.com/compliance/pci-dss-level-1-faqs/)  
- 🧾 **AICPA SOC** – [AWS SOC FAQs](https://aws.amazon.com/compliance/soc-faqs/)  
- 🌐 **ISO/IEC Standards**:  
  - [ISO/IEC 27001](https://aws.amazon.com/compliance/iso-27001-faqs/)  
  - [ISO/IEC 27017](https://aws.amazon.com/compliance/iso-27017-faqs/)  
  - [ISO/IEC 27018](https://aws.amazon.com/compliance/iso-27018-faqs/)  
  - [ISO 9001](https://aws.amazon.com/compliance/iso-9001-faqs/)

By using Amazon Cognito, you can manage users securely while complying with key **international standards**.

---

### 🟠 AWS Shield

**AWS Shield** is a **managed Distributed Denial of Service (DDoS) protection** service designed to protect applications running on AWS.

**Key capabilities:**

- 🧠 Provides **always-on detection** and **automatic inline mitigations** to minimize downtime and latency.  
- 🛡️ Protects against multiple attack types, including:
  - **Infrastructure-layer attacks** (e.g., UDP floods)  
  - **State exhaustion attacks** (e.g., TCP SYN floods)  
  - **Application-layer attacks** (e.g., HTTP GET/POST floods)  

📘 For examples, refer to the [AWS WAF Developer Guide](https://docs.aws.amazon.com/waf/latest/developerguide/waf-chapter.html).

**AWS Shield Service Tiers:**

| Tier | Description | Cost |
|------|--------------|------|
| **AWS Shield Standard** | Enabled by default for all AWS customers. Provides baseline DDoS protection. | Free |
| **AWS Shield Advanced** | Offers enhanced protection against large or sophisticated attacks. Includes 24/7 DDoS Response Team (DRT) support. | Paid service (requires Enterprise or Business Support) |

**AWS Shield Advanced** extends protection to:  
- Amazon EC2  
- Elastic Load Balancing (ELB)  
- Amazon CloudFront  
- AWS Global Accelerator  
- Amazon Route 53

---

### 🧾 Key Takeaways

✅ **AWS Organizations** allows central management and security control across multiple accounts.  
✅ **Service Control Policies (SCPs)** define the **maximum permissions** available within the organization.  
✅ **AWS KMS** manages encryption keys securely using FIPS-compliant HSMs.  
✅ **Amazon Cognito** provides secure, standards-based authentication and supports regulatory compliance (HIPAA, PCI DSS, ISO, etc.).  
✅ **AWS Shield** offers managed DDoS protection — both free (Standard) and advanced (paid) tiers.  
