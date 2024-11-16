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
