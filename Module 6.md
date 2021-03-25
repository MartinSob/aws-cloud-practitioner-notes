# Module 6: Security
## AWS shared responsibility model
AWS is responsible for the security of some parts of your environment and you (the customer) are responsible for other parts. It is divided into:

- **Customer responsibilities (“security in the cloud”):** Customers are responsible for the security of everything that they create and put in the AWS Cloud. The user is responsible for IAM roles and identities that can invoke the AWS Lambda functions. Client side data encryption, patch guest OS.

    When using AWS services, you maintain complete control over the content. You are responsible for managing security requirements for your content, including which content you choose to store on AWS, which AWS services you use, and who has access to that content. You also control how access rights are granted, managed, and revoked.
- **AWS responsibilities (“security of the cloud”):** AWS operates, manages, and controls the components at all layers of infrastructure. This includes areas such as the host operating system, the virtualization layer, and even the physical security of the data centers from which services operate. AWS is responsible for protecting the global infrastructure that runs all of the services offered in the AWS Cloud. This infrastructure includes AWS Regions, Availability Zones, and edge locations.

## AWS Identity and Access Management (IAM)
Document that enables you to manage access to AWS services and resources securely. IAM gives you the flexibility to configure access based on your company’s specific operational and security needs. **It is free of cost**.

### AWS account root user
When you first create an AWS account, you begin with an identity known as the root user. It has complete access to all the AWS services and resources in the account.

### IAM users
An IAM user is an identity (represents the person or application) that you create in AWS. It consists of a name and credentials. By default, when you create a new IAM user in AWS, it has no permissions associated with it. To allow the IAM user to perform specific actions in AWS, you must grant the IAM user the necessary permissions.

### IAM policies
Is a document that allows or denies permissions to AWS services and resources.  

### IAM groups
An IAM group is a collection of IAM users. When you assign an IAM policy to a group, all users in the group are granted permissions specified by the policy.
**IAM roles:** For getting temporary security credentials
**IAM tags:** Labels for custom attributes. Key-value pair.

## AWS Organizations
You can use AWS Organizations to consolidate and manage multiple AWS accounts within a central location. When you create an organization, AWS Organizations automatically creates a root, which is the parent container for all the accounts in your organization.

In AWS Organizations, you can centrally control permissions for the accounts in your organization by using **service control policies (SCPs)**. SCPs enable you to place restrictions on the AWS services, resources, and individual API actions that users and roles in each account can access.

SCPs can be used in Organizational Units and in an individual member account. Can be automated.

### Organizational units
In AWS Organizations, you can group accounts into organizational units (OUs) to make it easier to manage accounts with similar business or security requirements. When you apply a policy to an OU, all the accounts in the OU automatically inherit the permissions specified in the policy. Can only have one parent.

## AWS Artifact
AWS Artifact is a service that provides on-demand access to AWS security and compliance reports and select online agreements. AWS Artifact consists of two main sections:

- **Agreements:** You can review, accept, and manage agreements for an individual account and for all your accounts in AWS Organizations. Different types of agreements are offered.
- **Reports:** Provide compliance reports from third-party auditors. These auditors have tested and verified that AWS is compliant with a variety of global, regional, and industry-specific security standards and regulations.

### Customer Compliance Center
Contains resources to help you learn more about AWS compliance.

## Denial-of-service attacks (DoS)
It is a deliberate attempt to make a website or application unavailable to users.

**Distributed denial-of-service attacks:** Multiple sources are used to start an attack that aims to make a website or application unavailable.

## AWS Shield
A service that protects applications against DDoS attacks. Route 53, Cloudfront and Load balancing also help in this. AWS Shield provides two levels of protection: 

- **Standard:** Automatically protects all AWS customers at no cost. It protects your AWS resources from the most common, frequently occurring types of DDoS attacks. As network traffic comes into your applications, a variety of analysis techniques is used to detect malicious traffic in real time and automatically mitigates it.
- **Advanced:** Is a paid service that provides detailed attack diagnostics and the ability to detect and mitigate sophisticated DDoS attacks.

## AWS Key Management Service (AWS KMS)
Enables you to perform encryption operations through the use of cryptographic keys. You can use AWS KMS to create, manage, and use cryptographic keys. You can also control the use of keys across a wide range of services and in your applications. Uses envelope encryption while integrating with other AWS services.

A cryptographic key is a random string of digits used for locking (encrypting) and unlocking (decrypting) data.

With AWS KMS, you can choose the specific levels of access control that you need for your keys. For example, you can specify which IAM users and roles are able to manage keys. Alternatively, you can temporarily disable keys so that they are no longer in use by anyone. Your keys never leave AWS KMS, and you are always in control of them.

AWS managed KMS keys can only be rotated automatically as compared to the Customer Managed KMS keys that can be rotated automatically or manually.

## Amazon Inspector
Helps to improve the security and compliance of applications by running automated security assessments. It checks applications for security vulnerabilities and deviations from security best practices. After the Amazon Inspector has performed an assessment, it provides you with a list of security findings.

Amazon Inspector provides two types of packages. Network reachability rules package checks network accessibility checks on Amazon EC2 instance. Host assessment rules package checks vulnerabilities on Amazon EC2 instances. Uses predefined templates.

## Amazon GuardDuty
It is a service that provides intelligent threat detection for your AWS infrastructure and resources. It identifies threats by continuously monitoring the network activity and account behavior within your AWS environment, including S3.

## Other services
**AWS WAF:** It is a web application firewall that lets you monitor network requests that come into your web applications.

**Bastion Host Overview:** Bastion means a structure for Fortification to protect things behind it. In AWS, a Bastion host can be used to securely access instances in the private subnets. They need to be created in multiple AZ for redundancy.

**Certificate Manager:** Allows the web administrator to maintain one or several SSL/TLS certificates. To verify one: a CNAME record would need to be created and the administrator would need to acknowledge a verification email.

**Cloud HSM:** Allows for the administrator to have full and exclusive control over the generation and management cryptographic keys on actual hardware security modules that are physically stored in AWS data centers.

**Cognito:** Lets you add user sign-up, sign-in, and access control to your web and mobile apps quickly and easily. Supports sign-in with social identity providers, such as Apple, Facebook, Google, and other login services.

**Encryption SDK:** Improves implementation of the client-side encryption.

**Firewall manager:** Can manage VPC security groups, AWS Shield Advanced and WAF rules on one platform even across multiple AWS accounts. Since the DB does not require a Public IP, it is always a good practice to host the DB server on a non-default subnet that does not allocate a public IP by default. Also, the DB server should not have a route to the internet gateway.

**Identity Federation:** So users can access the AWS environment using their active directory credentials. It is possible for users to log into the AWS environment using their Facebook, Twitter or LinkedIn login credentials.

**Secrets Manager:** Easy way to safely store encrypted credentials and perform on demand retrieval.

**Security hub:** Facilitates the view of high priority security alerts. provides a view of across-account security status and gives security alerts.

**Security Token service:** web service that enables you to request temporary, limited-privilege credentials for AWS IAM users or for users that you authenticate (federated users). Mobile apps need access to AWS resources. STS + Identity federation = Session

**Single Sign-On (SSO):** Simplifies access management and manages access to multiple AWS accounts and business applications centrally.