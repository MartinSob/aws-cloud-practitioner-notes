# Module 8: Pricing and support
## AWS Free Tier
The AWS Free Tier enables you to begin using certain services without having to worry about incurring costs for the specified period.

- **Always Free:** These offers do not expire and are available to all AWS customers. For example, AWS Lambda allows 1 million free requests and up to 3.2 million seconds of compute time per month. Amazon DynamoDB allows 25 GB of free storage per month.
- **12 Months Free:** These offers are free for 12 months following your initial sign-up date to AWS.
- **Trials:** Short-term free trial offers start from the date you activate a particular service. The length of each trial might vary by number of days or the amount of usage in the service.

## How AWS pricing works
- **Pay for what you use:** For each service, you pay for exactly the number of resources that you use.
- **Pay less when you reserve:** Some services offer reservation options that provide a significant discount compared to On-Demand Instance pricing.
- **Pay less with volume-based discounts when you use more:** Some services offer tiered pricing, so the per-unit cost is incrementally lower with increased usage. For example, the more Amazon S3 storage space you use, the less you pay for it per GB.
- **No cost for inbound data transfer**
- **Saving plans:** Equal to 72% (not available in all regions)

## AWS Pricing Calculator
It lets you explore AWS services and create an estimate for the cost of your use cases on AWS. You can organize your AWS estimates by groups that you define. A group can reflect how your company is organized, such as providing estimates by cost center.

### AWS pricing examples
**AWS Lambda:** you are charged based on the number of requests for your functions and the time that it takes to run.
**Amazon S3:**
- *Storage:* You pay for only the storage that you use.
- *Requests and data retrievals:* You pay for requests made to your Amazon S3 objects and buckets.
- *Data transfer:* There is no cost to transfer data between different Amazon S3 buckets or from Amazon S3 to other services within the same AWS Region.
- *Management and replication:* You pay for the storage management features that you have enabled on your account’s Amazon S3 buckets. These features include Amazon S3 inventory, analytics, and object tagging.

## AWS Billing Dashboard
Where you can pay your AWS bill, monitor your usage, and analyze and control your costs.
- Compare your current month-to-date balance with the previous month and get a forecast of the next month based on current usage.
- View month-to-date spend by service.
- View Free Tier usage by service.
- Access Cost Explorer and create budgets.
- Purchase and manage Savings Plans.
- Publish AWS Cost and Usage Reports.

## Consolidated billing
The consolidated billing feature of AWS Organizations enables you to receive a single bill for all AWS accounts in your organization. By consolidating, you can easily track the combined costs of all the linked accounts in your organization. The default maximum number of accounts allowed for an organization is 4, but you can contact AWS Support to increase your quota, if needed.

Also, you can share bulk for discount pricing, like Savings Plans, and Reserved Instances.

## AWS Budgets
You can create budgets to plan your service usage, service costs, and instance reservations.

The information in AWS Budgets updates three times a day. This helps you to accurately determine how close your usage is to your budget. You can also set custom alerts when your usage exceeds (or is forecasted to exceed) the budgeted amount.

## AWS Cost Explorer
It is a tool that enables you to visualize, understand, and manage your AWS costs and usage over time. It includes a default report of the costs and usage for your top five cost-accruing AWS services. Includes data for up to the last 12 months

Identifies areas that need further inquiry and provides trends that you can use to understand costs. Can provide usage-based forecasts of estimated billing costs and usage for the coming 12 months.

## AWS Support
### Basic Support
It is free for all AWS customers. It includes access to whitepapers, documentation, and support communities. You can also contact AWS for billing questions and service limit increases.

With Basic Support, you have access to a limited selection of AWS Trusted Advisor checks. Additionally, you can use the **AWS Personal Health Dashboard**, a tool that provides alerts and remediation guidance when AWS is experiencing events that may affect you (can be used to identify an issue with the Amazon CloudWatch service) (Availability and performance of AWS services, alerts and notifications).

### Developer, Business, and Enterprise Support
They include all the benefits of Basic Support, in addition to the ability to open an unrestricted number of technical support cases. These three Support plans have pay-by-the-month pricing and require no long-term contracts.
- Developer:
    - Best practice guidance
    - Client-side diagnostic tools
    - Building-block architecture support
- Business Support:
    - Use-case guidance to identify AWS offerings, features, and services
    - All AWS Trusted Advisor checks
    - Limited support for third-party software
- Enterprise
    - Application architecture guidance
    - Infrastructure event management: Provides use-case, architectural and scaling guidance.

You can see the full table of differences in the [official documentation](https://aws.amazon.com/premiumsupport/plans/).

## Technical Account Manager (TAM)
Included with Enterprise Support. Primary point of contact at AWS. They provide guidance, architectural reviews, and ongoing communication with your company as you plan, deploy, and optimize your applications. They help you design solutions that efficiently use multiple services together through an integrated approach.

## AWS Marketplace
AWS Marketplace is a digital catalog that includes thousands of software listings from independent software vendors. You can use AWS Marketplace to find, test, and buy software that runs on AWS.

CPU bound SW licenses require a dedicated Host 🡪 expensive. High availability may involve manual recovery of resources. 

## Other services
**Total cost of ownership:** Number of servers migrated to AWS. The TCO calculator will make suggestions and recommendations on appropriate resource types based on the user’s input values and settings.

**TCO Calculator:** Use this calculator to compare the cost of running your applications in an on-premises or colocation environment to AWS.