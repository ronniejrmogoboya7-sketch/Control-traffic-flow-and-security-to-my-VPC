In this project, I designed and configured a custom Virtual Private Cloud (VPC) in AWS to simulate a secure production-ready cloud network.

The focus of this project was on:

Controlling network traffic flow

Implementing layered security

Separating public and private resources

Applying best practices for cloud network architecture
The VPC was configured with the following components:

Custom VPC with CIDR block 10.0.0.0/16

Public Subnet

Private Subnet

Internet Gateway (IGW)

Route Tables
Internet Access (Public Subnet)

Attached an Internet Gateway to the VPC

Created a Route Table with:

0.0.0.0/0 → Internet Gateway


Associated the route table with the public subnet

Enabled auto-assign public IP on public instances

This allowed public EC2 instances to receive internet traffic.
Private Subnet Isolation

Private subnet does NOT have direct internet access

No route to Internet Gateway

Used security groups to restrict inbound traffic

This ensures backend resources remain protected.
Security Implementation
Security Groups (Instance-Level Firewall)

Configured:

Allowed SSH (Port 22) from specific IP only

Allowed HTTP (Port 80) for web server testing

Blocked all other inbound traffic

Outbound allowed as required

Security Groups are stateful, meaning return traffic is automatically allowed.
onfigured custom NACL rules to:

Allow required inbound traffic

Restrict unnecessary ports

Control outbound traffic rules

Unlike Security Groups, NACLs are stateless, so both inbound and outbound rules were configured.

 Key Concepts Applied

CIDR block planning

Public vs Private subnet separation

Stateful vs Stateless firewalls

Principle of Least Privilege

Route table associations

Secure SSH access control

🧪 Testing & Validation

Verified internet access from public instance

Confirmed private instance had no direct internet access

Tested SSH restrictions

Confirmed route table associations worked correctly

 What I Learned

How AWS handles traffic routing inside a VPC

The difference between Security Groups and NACLs

Why subnet isolation is critical in production environments

How to design secure cloud network architecture

Future Improvements

Add NAT Gateway for private subnet internet access

Implement Bastion Host

Add Load Balancer

Use Infrastructure as Code (Terraform / CloudFormation)

 Author

Ronnie Jr Mogoboya
Aspiring Cloud Engineer
AWS Certified Cloud Practitioner
Working toward AWS Solutions Architect
Security Groups

Network ACLs (NACLs)
