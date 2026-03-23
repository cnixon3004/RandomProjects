🛡️ AWS VPC Security Groups & NACL Challenge
📌 Overview

In this lab, I built a custom Amazon VPC environment and implemented layered network security using Security Groups and Network ACLs (NACLs).

The goal was to understand how AWS handles stateful vs stateless traffic filtering and to test real-world connectivity scenarios between EC2 instances.

🧱 Architecture

This environment consists of:
+ A custom VPC (10.0.0.0/16)
+ Two public subnets:
  + 10.0.1.0/24 (Subnet A)
  + 10.0.2.0/24 (Subnet B)
+ Two EC2 instances:
  + Instance A → Security Group A (SGA)
  + Instance B → Security Group B (SGB)
+ Network ACL applied at the subnet level

🔐 Step 2: Security Group Configuration

Two security groups were created to simulate different access controls:

+ Security Group A (SGA)
  + Allows HTTP (80) from anywhere
  + Allows SSH (22) from anywhere
  + Allows all outbound traffic
+ Security Group B (SGB)
  + Allows HTTP (80) and SSH (22) from anywhere
  + Allows ICMP (ping) only from SGA
  + Allows all outbound traffic

This setup allows controlled communication between instances while still enabling external access.

<p align="center">
  <img src="/SG_NACL_Challenge/Images/SGA.png" width="40%" />
  <img src="/SG_NACL_Challenge/Images/SGB.png" width="40%" />
</p>

*Security Group for both subnets.*

💻 Step 3: EC2 Deployment & Web Server Setup

Two EC2 instances were launched (one per security group), and Apache was installed using user data:

Verified both instances were running


Confirmed Apache web server was accessible via public IP
Tested SSH access using EC2 Instance Connect
![Running EC2 Instances](/SG_NACL_Challenge/Images/instances.png)
*Running EC-2 Instance*

![Apache Test Page](/SG_NACL_Challenge/Images/browser.png)
*Apache Test page for both instances*

🧪 Step 4: Connectivity Testing

To validate the network configuration, I performed several tests:

+ 🌐 HTTP Access
 + Accessed both instances via browser using public IP
+ 🔐 SSH Access
 + Connected to both instances using EC2 Instance Connect
+ 🔁 ICMP (Ping)
  + Successfully pinged Instance B from Instance A
+ 📡 Curl Test
 + Retrieved Apache page from one instance to another using curl


