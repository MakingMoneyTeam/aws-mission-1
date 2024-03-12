---
title: 'Create Security Group'
date: '`r Sys.Date()`'
weight: 2
chapter: false
pre: ' <b> 2.2. </b> '
---

1. Access **Security Group**

- Click **Create security group**.
  ![Security Group](../../images/security_group_1.png)

2. Under **Create Security Group** interface

- **Basic details**

  - Security group name: `WebServerSecurity`
  - Description: `Allow traffic to access web server application`
  - VPC: **_Remember to choose our created VPC_**
    ![Security Group](../../images/security_group_2.png)

- **Inbound rule**

  - Allow **SSH** protocol - source: My IP
  - Allow **ICMP - IPV4** - source: My IP
  - Allow **Custome TCP** - Port **8080** (default port of Spring Boot Application) - source: anywhere

- Remain **Outbound rule**, and click **Create security group**.
  ![Security Group](../../images/security_group_3.png)

3. We review the result in **Security groups**.
   ![Security Group](../../images/security_group_4.png)
