# 📊 Module 2 - Cloud Economics and Billing

## 4️⃣ Section 4: AWS Billing and Cost Management

### 🟠 Introducing AWS Billing and Cost Management

**AWS Billing and Cost Management** → service that you use to pay your AWS bill, monitor your usage, and budget your costs. Billing and Cost Management enables you to forecast and obtain a better idea of what your costs and usage might be in the future so that you can plan ahead.

**Features:**

- Custom time periods (daily or monthly view).
- Filtering and grouping of data by dimensions.
- **AWS Cost and Usage Report Tool** → detailed insights to identify optimization opportunities.

### 🟠 AWS Billing Dashboard

- Central view of AWS expenditure.
- Key graphs:
    - **Spend Summary** → past month spending, current month-to-date, forecast for this month.
    - **Month-to-Date Spend by Service** → shows top services used and their cost proportions.

### 🟠 Tools

Accessible from the billing dashboard:

- **AWS Bills**
- **AWS Cost Explorer**
- **AWS Budgets**
- **AWS Cost and Usage Reports**

### 🟠 Monthly Bills

- Provides **detailed breakdown** of costs:
    - By AWS service.
    - By AWS Region.
    - By linked account.
- Most up-to-date source for **monthly bill and usage information**.

### 🟠 Cost Explorer

The AWS Billing and Cost Management console includes the Cost Explorer page for viewing your AWS cost data as a graph.

- Tool for **visualizing and analyzing AWS cost and usage** over time.
- Default report shows **top cost-incurring services**.
- Monthly running costs → overview of last 3 months + forecast for next month (with confidence interval).

Cost Explorer enables you to:

- View charts of your costs.
- View cost data for the past 13 months.
- Forecast how much you are likely to spend over the next 3 months.
- Discover patterns in how much you spend on AWS resources over time and identify costproblem areas.
- Identify the services that you use the most
- View metrics, like which Availability Zones have the most traffic or which linked AWS account is used the most.

### 🟠 Forecast and track costs

**AWS Budgets** → uses the cost visualization that is provided by Cost Explorer to show you the status of your budgets and to provide forecasts of your estimated costs.

- Lets you:
    - Track budgets at monthly, quarterly, or yearly levels.
    - Customize start and end dates.
    - Set alerts when **actual or forecasted costs exceed budget**.
- Notifications sent via **email** or **Amazon SNS**.

### 🟠 Cost and usage reporting

The AWS Cost and Usage Report is a single location for accessing comprehensive information about your AWS costs and usage.

This tool lists the usage for each service category that is used by an account (and its users) in hourly or daily line items, and any tax that you activated for tax allocation purposes.

You can choose to have AWS to publish billing reports to an S3 bucket.

These reports can be updated once a day.

**Resume:**

- **Most comprehensive cost/usage data** in AWS.
- Provides detailed hourly/daily line items by:
    - Service category.
    - Account/user usage.
    - Tax allocations (if enabled).
- Reports can be delivered automatically to an **S3 bucket**, updated **daily**.