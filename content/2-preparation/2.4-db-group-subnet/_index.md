---
title: 'Create DB Group Subnet'
date: '`r Sys.Date()`'
weight: 4
chapter: false
pre: ' <b> 2.4. </b> '
---

1. Access **RDS** interface

- Click **Subnet groups**.
- Click **Create DB subnet group**.
  ![DB Group Subnet](../../images/db_group_subnet_1.png)

2. Under **Create DB subnet group** interface

- **Subnet group details**

  - Name: `db-subnet-group`
  - Description: `Bistro Database Subnet Group`
  - VPC: Choose the **created VPC**
    ![DB Group Subnet](../../images/db_group_subnet_2.png)

- **Add subnets**
  - Availability Zones: **ap-southeast-1a** and **ap-southeast-1b**
  - Subnets: Choose **2 private subnets CIDR** placed in **2 different availability zones**
- Click **Create**
  ![DB Group Subnet](../../images/db_group_subnet_3.png)
