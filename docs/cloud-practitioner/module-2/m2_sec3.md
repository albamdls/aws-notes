# 📊 Module 2 - Cloud Economics and Billing

## 3️⃣ Section 3: AWS Organizations

### 🟠 Introduction to AWS Organizations

**AWS Organizations** → account management service that enables you to consolidate multiple AWS accounts into anorganizationthat you create and centrally manage. AWS Organizations include consolidated billing and account management capabilities that help you to better meet the budgetary, security, and compliance needs of your business.

**Key benefits**:

- Centrally managed **access policies** across multiple AWS accounts.
- **Controlled access** to AWS services.
- Automated AWS account creation and management.
- **Consolidated billing** across multiple AWS accounts.

### 🟠 AWS Organizations terminology

Hereis some terminology to understand the structure of AWS Organizations.

- **Root**: the top-level container for the organization.
- **Organizational Unit (OU)**:
    - A container for accounts within a root.
    - OUs can contain other OUs (tree-like hierarchy).
    - Policies attached to a node flow down to all children.
- **Account**: a standard AWS account holding resources.
- **Policies**:
    - Can be attached at root, OU, or account level.
    - Affect all IAM users, groups, and roles inside that account.
- Rules:
    - An OU has only one parent.
    - An account belongs to exactly one OU.

### 🟠 Key features and benefits

AWS Organizations enables you to:

- Create **Service Control Policies (SCPs)** that centrally control AWS services across multiple AWS accounts.
- Create **groups of accounts** and then attach policies to a group to ensure that the correct policies are applied across the accounts.
- Simplify **account management by using** application programming interfaces **(APIs)** to automate the creation and management of new AWS accounts.
- Simplify billing with a **single payment method** for all accounts:
    - Combined view of charges.
    - Access to **volume discounts** through aggregated usage.

With consolidated billing, you can see a combined view of charges that are incurred by all your accounts, and you can take advantage of pricing benefits from aggregated usage. Consolidated billing provides a central location to manage billing across all of your AWS accounts, and the ability to benefit from volume discounts.

### 🟠 Security with AWS Organizations

- **IAM Policies**:
    - Allow/deny access to services, resources, or API actions.
    - Apply to IAM users, groups, and roles.
    - **Cannot restrict the root user** of an account.
- **SCPs (Service Control Policies)**:
    - Apply at the **organization level** (root, OU, or account).
    - Restrict/allow services across accounts.
    - Affect **all identities** (users, groups, roles) **including root user**.

👉 IAM = access control inside an account.

👉 SCPs = broader guardrails across multiple accounts.

### 🟠 Organizations setup

Keep in mind that this process assumes that you have access to two existing AWS accounts, and that you can sign in to each account as an administrator.

Review these steps forsetting up AWS Organizations:

- **Step 1** → **Create an organization** using your main AWS account (becomes the management account). Invite or create member accounts.
- **Step 2** → create two organizational units in your new organization and place the member accounts in those OUs.
- **Step 3** → create service control policies, which enable you to apply restrictions to what actions can be delegated to users and roles in the member accounts. A service control policy is a type of organization control policy.
- **Step 4** → **Test policies** by signing in as users or using the IAM policy simulator.

### 🟠 Limits of AWS Organizations

- **Naming**: Unicode, max 250 characters.
- **Entities & limits**:
    - Accounts: varies.
    - Roots: 1.
    - OUs: up to 1,000.
    - Policies: up to 1,000.
    - Policy document size: max 5,120 bytes.
    - Max OU nesting: 5 levels.
    - Invitations per day: 20.
    - Member accounts created concurrently: 5.
    - Policies can be attached to unlimited entities.

### 🟠 Accessing AWS Organizations

You can manage Organizations through:

- **AWS Management Console** → web-based UI.
- **AWS CLI** → faster, command-line management.
- **AWS SDKs** → programmatic access with libraries for Java, Python, Ruby, .NET, iOS, Android, etc.
- **HTTPS Query API** → direct API calls (requires digitally signed requests).