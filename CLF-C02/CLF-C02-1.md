#### Server

What is a server composed of:

- Compute: CPU
- Memory: RAM
- Storage: Data
- Database: Store data in a structured way
- Network: Routers, switch, DNS server

IT Terminology

- Network: cables, routers and servers connected with each other
- Router : A networking device that forwards data packets between computer networks. They know where to send your packets on the internet!
- Switch: Takes a packet and send it to the correct server / client on your network Router Switch

What is Cloud Computing:

- Cloud computing is the on-demand deliver y of compute power, database storage, applications, and other IT resources
- Through a cloud services platform with pay-as-you-go pricing
- You can provision exactly the right type and size of computing resources you need
- You can access as many resources as you need, almost instantly
- Simple way to access ser vers, storage, databases and a set of application ser vices
- Amazon Web Services owns and maintains the network-connected hardware required for these application services, while you provision and use what you need via a web application.

The Deployment Models of the Cloud

- Private Cloud:

  - Cloud services used by a single organization, not exposed to the public.
  - Complete control
  - Security for sensitive applications
  - Meet specific business needs

- Public Cloud:

  - Cloud resources owned and operated by a third-party cloud service provider delivered over the Internet.
  - Six Advantages of Cloud Computing
    - Trade capital expense (CAPEX) for operational expense (OPEX)
      - Pay On-Demand: don’t own hardware
      - Reduced Total Cost of Ownership (TCO) & Operational Expense (OPEX)
  - Benefit from massive economies of scale
    - Prices are reduced as AWS is more efficient due to large scale
  - Stop guessing capacity
    - Scale based on actual measured usage
  - Increase speed and agility
  - Stop spending money running and maintaining data centers
  - Go global in minutes: leverage the AWS global infrastructure

  - The Five Characteristics of Cloud Computing
    - On-demand self service: Users can provision resources and use them without human interaction from the service provider
    - Broad network access: Resources available over the network, and can be accessed by diverse client platforms
    - Multi-tenancy and resource pooling:
      - Multiple customers can share the same infrastructure and applications with security and privacy
      - Multiple customers are serviced from the same physical resources
    - Rapid elasticity and scalability:
      - Automatically and quickly acquire and dispose resources when needed
      - Quickly and easily scale based on demand
    - Measured ser vice: Usage is measured, users pay correctly for what they have used

- Hybrid Cloud:
  - Keep some servers on premises and extend some capabilities to the Cloud
  - Control over sensitive assets in your private infrastructure
  - Flexibility and cost-effectiveness of the public cloud

Types of Cloud Computing

- Infrastructure as a Ser vice (IaaS)
  - Provide building blocks for cloud IT
  - Provides networking, computers, data storage space
  - Highest level of flexibility
  - Easy parallel with traditional on-premises IT
- Platform as a Ser vice (PaaS)
  - Removes the need for your organization to manage the underlying infrastructure
  - Focus on the deployment and management of your applications
- Software as a Ser vice (SaaS)
  - Completed product that is run and managed by the service provider

Pricing of the Cloud

- AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model
- Compute:
  - Pay for compute time
- Storage:
  - Pay for data stored in the Cloud
- Data transfer OUT of the Cloud:
  - Data transfer IN is free

AWS Global Infrastructure

- AWS Regions

  - A region is a cluster of data centers
  - Most AWS ser vices are region-scoped

- AWS Availability Zones

  - Each region has many availability zones (usually 3, min is 3, max is 6)
  - Each availability zone (AZ) is one or more discrete data centers with redundant power, networking, and connectivity
  - They’re separate from each other, so that they’re isolated from disasters
  - They’re connected with high bandwidth, ultra-low latency networking

- AWS Data Centers
- AWS Edge Locations / Points of Presence
  - Content is delivered to end users with lower latency

Shared Responsibility Model diagram

- AWS = RESPONSIBILITY FOR THE SECURITY OF THE CLOUD
- CUSTOMER = RESPONSIBILITY FOR THE SECURITY IN THE CLOUD

#### IAM - Identity and Access Management

- IAM = Identity and Access Management, Global service
- Root account created by default, shouldn’t be used or shared
- Users are people within your organization, and can be grouped
- Groups only contain users, not other groups
- Users don’t have to belong to a group, and user can belong

IAM: Permissions

- Users or Groups can be assigned JSON documents called policies
- These policies define the permissions of the users
- In AWS you apply the least privilege principle: don’t give more permissions than a user needs

IAM Policies Structure

Consists of

- Version: policy language version, always include “2012-10-17”
- Id: an identifier for the policy (optional)
- Statement: one or more individual statements (required)

Statements consists of

- Sid: an identifier for the statement (optional)
- Effect: whether the statement allows or denies access (Allow, Deny)
- Principal: account/user/role to which this policy applied to
- Action: list of actions this policy allows or denies
- Resource: list of resources to which the actions applied to
- Condition: conditions for when this policy is in effect (optional)

```json
{
  "Version": "2012-10-17",
  "Id": "S3-Account-Permissions",
  "Statement": [
    {
        "Sid": "1",
      "Effect": "Allow",
      "Principal":{
        "AWS":["arn:aws:iam:123456789012:root"]
      }
      "Action": "ec2:Describe*",
      "Resource": "*"
    }
  ]
}
```

To access AWS, you have three options:

- AWS Management Console (protected by password + MFA)
- AWS Command Line Interface (CLI): protected by access keys
- AWS Software Developer Kit (SDK) - for code: protected by access keys
  Access Keys are generated through the AWS Console

The AWS CLI

- A tool that enables you to interact with AWS services using commands in your command-line shell
- Direct access to the public APIs of AWS services

the AWS SDK

- AWS Software Development Kit (AWS SDK)
- Language-specific APIs (set of libraries)
- Enables you to access and manage AWS services programmatically
- Embedded within your application
- Supports
  - SDKs (JavaScript, Python, PHP, .NET, Ruby, Java, Go, Node.js, C++)
  - Mobile SDKs (Android, iOS, ...)
  - IoT Device SDKs (Embedded C, Arduino, ...)
- Example: AWS CLI is built on AWS SDK for Python

IAM Roles for Services

- Some AWS service will need to perform actions on your behalf
- To do so, we will assign permissions to AWS services
  with IAM Roles
- Common roles:
  - EC2 Instance Roles
  - Lambda Function Roles
  - Roles for CloudFormation

IAM Security Tools

- IAM Credentials Report (account-level)
  1. a report that lists all your account's users and the status of their various credentials
- IAM Access Advisor (user-level)
  1. Access advisor shows the service permissions granted to a user and when those services were last accessed.
  1. You can use this information to revise your policies.

IAM Section – Summary

- Users: mapped to a physical user, has a password for AWS Console
- Groups: contains users only
- Policies: JSON document that outlines permissions for users or groups
- Roles: for EC2 instances or AWS services
- Security: MFA + Password Policy
- AWS CLI: manage your AWS services using the command-line
- AWS SDK: manage your AWS services using a programming language
- Access Keys: access AWS using the CLI or SDK
- Audit: IAM Credential Reports & IAM Access Advisor
