# Module 4: Networking
## Amazon Virtual Private Cloud (Amazon VPC)
A free networking service that you can use to establish boundaries around your AWS resources.

Amazon VPC enables you to provision an isolated section of the AWS Cloud. In this isolated section, you can launch resources in a virtual network that you define. Within a VPC, you can organize your resources into subnets. A **subnet** is a section of a VPC that can contain resources such as Amazon EC2 instances.

**Internet gateway:** To allow public traffic from the internet to access your VPC. Is a connection between a VPC and the internet. Without an internet gateway, no one can access the resources within your VPC.

### Virtual private gateway
To access private resources in a VPC, you can use a virtual private gateway. Is the component that allows protected internet traffic to enter the VPC.

**Virtual private network (VPN):** Connection that encrypts (or protects) your internet traffic from all the other requests around it. Full hour is billed.

A **virtual private gateway** enables you to establish a **virtual private network** (VPN) connection between your VPC and a private network, such as an on-premises data center or internal corporate network. A virtual private gateway allows traffic into the VPC only if it is coming from an approved network.

**Network address translation (NAT) gateway:** To enable instances in a private subnet to connect to the internet or other AWS services, but prevent the internet from initiating a connection with those instances.

## AWS Direct Connect
AWS Direct Connect is a service that enables you to establish a dedicated private connection between your data center and a VPC.

The private connection that AWS Direct Connect provides helps you to reduce network costs and increase the amount of bandwidth that can travel through your network. AWS Direct Connect supports only the BGP (Border Gateway Protocol) routing protocol for this connectivity.

## Subnets
A section of a VPC in which you can group resources based on security or operational needs. Subnets can be public or private. In a VPC, subnets can communicate with each other.

**Public subnets** contain resources that need to be accessible by the public, such as an online store’s website.

**Private subnets** contain resources that should be accessible only through your private network, such as a database that contains customers’ personal information and order histories. 

## Network traffic in a VPC
A packet is a unit of data sent over the internet or a network, which is sent as request to an application hosted in the AWS Cloud. It enters a VPC through an internet gateway. Before a packet can enter a subnet or exit one, it checks for permissions. These permissions indicate who sent the packet and how the packet is trying to communicate with the resources in a subnet.

The VPC component that checks packet permissions for subnets is a network access control list (ACL). VPC endpoint configured by AWS Private Link can have **Amazon SES (Simple Email Service)**.

## Network access control lists (NACLs)
An optional virtual firewall that controls inbound and outbound traffic at the **subnet level**. Each AWS account includes a default network ACL. When configuring your VPC, you can use your account’s default network ACL or create custom network ACLs.

By default, your account’s default network ACL **allows all inbound and outbound traffic**, but you can modify it. For custom network ACLs, all inbound and outbound traffic is denied until you add rules to specify which traffic to allow. Additionally, all network ACLs have an explicit deny rule. This rule ensures that if a packet doesn’t match any of the other rules on the list, the packet is denied.

### Stateless packet filtering
**Network ACLs perform stateless packet filtering.** They remember nothing and check packets that cross the subnet border each way: inbound and outbound. The VPC component that checks packet permissions for an Amazon EC2 instance is a security group.

#### Security groups
A security group is a virtual firewall that controls inbound and outbound traffic for an Amazon EC2 instance. By default, a security group denies all inbound traffic and allows all outbound traffic. You can add custom rules to configure which traffic to allow or deny. **Instance level**.

If you have multiple instances within a subnet, you can associate them with the same security group.

### Stateful packet filtering
**Security groups perform stateful packet filtering.** They remember previous decisions made for incoming packets. Both network ACLs and security groups enable you to configure custom rules for the traffic in your VPC.

| Name           | Definition   |
| -------------- |:-------------|
| Private subnet | Isolates databases containing customers personal information |
| Virtual private gateway | Create a VPN connection between VPC and the internal corporate network |
| Public subnet | Support the customer facing website |
| AWS Direct connect | Establish a dedicated connection between the on-premises data center and the VPC |
| Security groups | They are stateless and deny all inbound traffic by default. |

## Domain Name System (DNS)
Customers enter a web address into their browser, and they can access the website. This happens because of Domain Name System (DNS) resolution. DNS resolution involves a DNS server communicating with a web server.

## Amazon Route 53
Amazon Route 53 is a DNS web service. It gives developers and businesses a reliable way to route end users to internet applications hosted in AWS. Amazon Route 53 connects user requests to infrastructure running in AWS. It can route users to infrastructure outside of AWS.

Another feature of Route 53 is the ability to manage the DNS records for domain names. You can register new domain names directly in Route 53. You can also transfer DNS records for existing domain names managed by other domain registrars. This enables you to manage all your domain names within a single location.

It takes 24 to 48 hours to update resolvers around the world because those can only reflect their changes in their cache after the Time to Live has expired.

The geolocation policy allows for different resources to serve content based on the origin of the request.
- **Multivalue routing:** Returns multiple healthy IP addresses. Improves availability and load balancing.
- **Failover routing:** When 99.99% of uptime is required. Used in disaster recovery scenarios.
- **Weighted routing:** Route traffic in proportions.

**VPC peering connection** is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different regions (also known as an inter-region VPC peering connection). *Fault-Tolerance, disaster recovery and redundancy*.

## Other services
**Elastic IP:** Static IP address that can be created and assigned to an AWS Account rather than to an Availability Zone.

**EventBridge:** is a serverless event bus that makes it easy to connect applications together using data from your own applications.