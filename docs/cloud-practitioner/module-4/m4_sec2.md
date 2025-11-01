# 🛡️ Module 4 - AWS Cloud Security  

## 2️⃣ Section 2: AWS Identity and Access Management (IAM)

### 🟠 AWS Identity and Access Management Overview

**AWS Identity and Access Management (IAM)** enables you to control access to AWS compute, storage, database, and application services.  
It handles both **authentication** (who can sign in) and **authorization** (what actions they can perform).

IAM is a **centralized access management tool** that lets you define permissions to launch, configure, manage, and terminate resources in your AWS account.  
It provides **granular control** over resources — you can specify exactly which API calls users are authorized to make to each service.

Whether you use the **AWS Management Console**, the **AWS CLI**, or **SDKs**, every call to an AWS service is an **API call** authenticated through IAM.  
IAM allows you to manage **who can access what resources** and **how** they can access them.

You can assign different permission levels:  
- 👩‍💻 Some users may have **full administrative access**.  
- 👀 Others may have **read-only access** to limited resources (e.g., specific S3 buckets).  
- 💼 Some may have access only to **billing information** or account details.

IAM is a **feature of every AWS account** and is **free of charge**.

---

### 🟠 Essential IAM Components

To understand IAM, you must know its four key components:

| 🧱 Component | 🔍 Description |
|--------------|----------------|
| **IAM User** | Represents a person or application that interacts with AWS. Each has a **unique name** and **credentials** (passwords or keys). |
| **IAM Group** | A **collection of IAM users**. Helps manage permissions by assigning policies to groups instead of individuals. |
| **IAM Policy** | A **JSON document** that defines permissions. Specifies which actions are allowed or denied on which AWS resources. |
| **IAM Role** | Grants **temporary access** to AWS resources. Roles are not tied to a specific user and can be assumed by anyone authorized to do so. |

---

### 🟠 Authentication and Access Types

Authentication ensures that only verified users or systems can access AWS.  

When defining an **IAM user**, you can choose between two types of access:  

1. 🔹 **Programmatic access**  
   - Uses the **AWS CLI**, **SDKs**, or **APIs**.  
   - Requires an **Access Key ID** and a **Secret Access Key**.  

2. 🔹 **AWS Management Console access**  
   - Allows sign-in via a **web interface** with a username and password.  
   - Users must enter their **12-digit account ID or alias**.  
   - If **Multi-Factor Authentication (MFA)** is enabled, an **extra authentication code** is required.  

You can grant **one**, **both**, or **neither** access type depending on user needs.

---

### 🟠 Multi-Factor Authentication (MFA)

🔐 MFA adds an **extra layer of protection** by requiring a secondary authentication token in addition to a password.  

**Available MFA options:**  
- 📱 Virtual MFA apps — *Google Authenticator*, *Authy*, etc.  
- 🔑 U2F hardware security keys.  
- 💻 Physical MFA devices (key fobs, display cards).  

MFA is **strongly recommended** for all users — especially **root** and **administrative accounts**.

---

### 🟠 Authorization: What Actions Are Permitted

Authorization defines **what users, services, or applications can do** once authenticated.  

- By default, all IAM users have **no permissions**.  
- Access must be explicitly granted using **IAM policies** written in **JSON**.  
- Each policy lists allowed or denied actions for specified AWS resources.  

---

### 🟠 IAM Authorization Logic

When creating IAM policies, keep these principles in mind:  

- ❌ **No default permissions** — everything is denied unless explicitly allowed.  
- 🚫 **Explicit deny** always overrides any allow.  
- ✅ Follow the **Principle of Least Privilege** — grant only the permissions users need to perform their tasks.  
- 🌎 IAM settings are **global**, not regional (they apply across all Regions).  

---

### 🟠 IAM Policies

An **IAM policy** defines a set of permissions that can be attached to **users, groups, roles, or resources**.

**Policies specify:**  
- The **actions** users can perform.  
- The **resources** they can access.  
- The **conditions** under which access is granted or denied.  

**Policy Evaluation Rules:**  
- All relevant policies are evaluated together.  
- The **most restrictive rule** applies in case of conflict.  

**Types of IAM Policies:**  
- 🧩 **Identity-based policies**  
  - Attached to users, groups, or roles.  
  - Can be:  
    - **Managed policies** (reusable and standalone).  
    - **Inline policies** (embedded directly in one entity).  

- 🗂️ **Resource-based policies**  
  - Attached directly to an AWS resource (e.g., S3 bucket policies).  
  - Define who can access the resource and under what conditions.

---

### 🟠 Example: IAM Policy Document

IAM policies are written in **JSON** format.  

An example policy might:  
- Allow access only to a **specific DynamoDB table** and an **S3 bucket**.  
- Include an `"Effect": "Deny"` statement to block any other actions or resources.  
- Use `"NotResource"` to prevent use of other services, even if granted elsewhere.  

➡️ Remember: **Explicit Deny** overrides all other permissions.

---

### 🟠 Resource-Based Policies

While identity-based policies are linked to IAM users or groups, **resource-based policies** are attached directly to a resource (for example, an S3 bucket).  

To create one in AWS Management Console:  
1. Go to the **resource (e.g., S3 bucket)**.  
2. Open the **Permissions** tab.  
3. Click **Bucket Policy**, and define the **JSON-formatted policy**.  

**Example Scenario:**  
- The user *MaryMajor* can access the S3 bucket **photos** either by:  
  - An **identity-based policy** attached to her user.  
  - A **resource-based policy** on the bucket granting her access.  

If a **Deny** statement exists in the bucket policy, it **overrides any Allow** in identity-based policies.

---

### 🟠 IAM Permission Evaluation Process

When IAM evaluates permissions, it follows this order:  

1. 🔍 Check for any **explicit Deny**.  
2. ✅ If no Deny, check for **explicit Allow**.  
3. 🚫 If neither exists, the default is **Implicit Deny**.  

This ensures fine-grained and secure access control for every AWS identity.

---

### 🟠 IAM Groups

IAM Groups simplify permission management for multiple users.  

**Example:**  
Create a group called `Developers`, attach the required policies, and then add users.  
All users in that group automatically inherit the group’s permissions.

**Key characteristics:**  
- 👥 A group can contain **many users**.  
- 🔄 A user can belong to **multiple groups**.  
- 🧱 Groups **cannot be nested** (no group inside another group).  
- 🚫 There is **no default group** — all must be created manually.  

---

### 🟠 IAM Roles

An **IAM Role** is similar to a user but not tied to a specific person.  
It is designed to be **assumed temporarily** by whoever needs it.  

**Roles provide temporary security credentials** and are commonly used for:  
- 🤝 **Cross-account access** (between AWS accounts).  
- 📱 **Applications** that require temporary AWS access (without embedding credentials).  
- 🧑‍💻 **Delegating access** to third-party auditors or AWS services.  
- 🧩 **Federated access** — users authenticated through corporate directories (e.g., Active Directory).  

Roles are fundamental to building **secure, scalable, and compliant** AWS environments.

---

### 🧾 Key Takeaways

✅ IAM policies are written in **JSON** and define permissions precisely.  
✅ Policies can be attached to **users, groups, or roles**.  
✅ **IAM entities** include **users**, **groups**, and **roles**.  
✅ An **IAM user** represents a person or application with credentials.  
✅ An **IAM group** simplifies permission assignment to multiple users.  
✅ An **IAM role** provides **temporary, delegated access** to AWS resources.  
