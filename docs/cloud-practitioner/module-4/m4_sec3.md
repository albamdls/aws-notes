# 🛡️ Module 4 - AWS Cloud Security  

## 3️⃣ Section 3: Securing a New AWS Account

### 🟠 AWS Account Root User Access vs. IAM Access

When you first create an **AWS account**, you begin with a **single sign-in identity** that has complete access to all AWS services and resources in the account.  
This identity is called the **AWS account root user**, and it is accessed by signing in to the AWS Management Console using the **email address and password** you used when creating the account.

- The **root user** has and retains **full access** to all resources in the account.  
- Therefore, **AWS strongly recommends** that you **do not use root user credentials** for daily operations.

Instead, AWS recommends using **IAM** to create additional users and assign permissions following the **principle of least privilege**.  
For example:
- If you require administrator-level permissions, create an IAM user and grant full access to that user.  
- Later, you can modify or revoke those permissions by changing associated IAM policies.

If multiple users need access to the account:
- Create **unique credentials** for each user.  
- Define which resources each user can access.  
- Avoid **sharing the same credentials** among multiple users.

⚠️ Some specific administrative tasks can **only be performed by the root user**.  
You can find a full list of such tasks here:  
🔗 [Tasks that require root user credentials](https://docs.aws.amazon.com/general/latest/gr/root-vs-iam.html#aws_tasks-that-require-root).

---

### 🟠 Securing a New AWS Account: Account Root User

To stop using the **account root user** for daily operations, follow these steps:

1. **Create an IAM user for yourself**
   - While logged in as the root user, create a new IAM user with **AWS Management Console access** enabled.  
   - Do **not** attach permissions yet. Save the IAM user’s access keys if needed.
2. **Create an IAM group**
   - Give the group a descriptive name (for example, `FullAccess`).  
   - Attach IAM policies that grant full access to essential AWS services.  
   - Add your newly created IAM user to this group.
3. **Disable and remove root access keys**
   - If your root user has access keys, delete them immediately.
4. **Enable a password policy**
   - Apply a strong password policy for all IAM users.  
   - Copy the IAM user sign-in link from the IAM dashboard.
5. **Sign out as the root user**
   - Use the sign-in link to log in as your IAM user instead.
6. **Store root credentials securely**
   - Keep them in a **safe and restricted location**.

📘 For detailed steps, see the AWS guide:  
🔗 [Creating Your First IAM Admin User and Group](https://docs.aws.amazon.com/IAM/latest/UserGuide/getting-started_create-admin-group.html).

---

### 🟠 Securing a New AWS Account: MFA (Multi-Factor Authentication)

To enhance security, **enable MFA** for both the **root user** and **all IAM users**.

- MFA requires users to provide a **second form of authentication** (in addition to their password).  
- This protects against unauthorized access, even if passwords are compromised.

You can also enable MFA to secure **programmatic access** to AWS APIs.  
For configuration details, see:  
🔗 [Configuring MFA-Protected API Access](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_credentials_mfa_configure-api-require.html)

**MFA device options include:**
- 📱 Virtual MFA apps (e.g., *Google Authenticator*, *Authy*)
- 🔑 U2F security key devices
- 💻 Hardware MFA devices (key fobs or display cards)

---

### 🟠 Securing a New AWS Account: AWS CloudTrail

**AWS CloudTrail** is a service that records all **API requests** made to resources in your account, providing **operational auditing** and **security visibility**.

- CloudTrail is **enabled by default** for all AWS accounts.  
- It retains a record of the **last 90 days** of management event activity.  
- You can view or download these logs for **create**, **modify**, and **delete** operations.

You can extend log retention and enable event alerts by creating a **trail**.  
This allows you to:
- Store CloudTrail logs for **longer periods**.  
- Send notifications when **specific events occur**.  

📘 For detailed guidance, see:  
🔗 [Creating a Trail Using the Console (AWS Documentation)](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-create-a-trail-using-the-console-first-time.html)

You can also review the list of supported services here:  
🔗 [CloudTrail Service-Specific Topics](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-aws-service-specific-topics.html)

---

### 🟠 Securing a New AWS Account: Billing Reports

Another best practice for securing and managing your AWS account is to **enable billing reports**, such as the **AWS Cost and Usage Report**.

- These reports provide detailed insights into **resource usage** and **estimated costs**.  
- AWS delivers them automatically to an **Amazon S3 bucket** of your choice.  
- Reports are updated **at least once per day**.

The AWS Cost and Usage Report tracks:
- Hourly and daily usage by service.  
- Estimated charges for each AWS service.  

📘 Learn more here:  
🔗 [Creating an AWS Cost and Usage Report](https://docs.aws.amazon.com/cur/latest/userguide/cur-create.html)

---

### 🧾 Key Takeaways

✅ Enable **Multi-Factor Authentication (MFA)** for all users (including root).  
✅ **Delete root user access keys**.  
✅ Create **individual IAM users** and grant permissions following the **Principle of Least Privilege**.  
✅ Use **groups** to assign permissions efficiently.  
✅ Enforce a **strong password policy**.  
✅ Delegate permissions using **roles** instead of sharing credentials.  
✅ Monitor all account activity using **AWS CloudTrail**.
