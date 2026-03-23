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
  <img src="URL_OF_IMAGE_1" width="300" />
  <img src="URL_OF_IMAGE_2" width="300" />
</p>
