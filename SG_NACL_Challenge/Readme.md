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
