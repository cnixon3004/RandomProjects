🛡️ AWS VPC Security Groups & NACL Challenge
📌 Overview

In this lab, I built a custom Amazon VPC environment and implemented layered network security using Security Groups and Network ACLs (NACLs).

The goal was to understand how AWS handles stateful vs stateless traffic filtering and to test real-world connectivity scenarios between EC2 instances.

🧱 Architecture
* Custom VPC with public subnets
  * 2 EC2 instances:
  * Instance A → Security Group A (SGA)
  * Instance B → Security Group B (SGB)
  *  Apache web server installed via user data
* Controlled traffic using:
  * Security Groups (stateful)
  * Network ACLs (stateless)
