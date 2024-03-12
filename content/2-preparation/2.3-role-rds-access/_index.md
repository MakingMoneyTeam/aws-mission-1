---
title: 'Create Role RDS Access'
date: '`r Sys.Date()`'
weight: 3
chapter: false
pre: ' <b> 2.3. </b> '
---

1. Access the **IAM** interface and click **Roles**.

![Role RDS Access](../../images/role_rds_1.png)

- Click **Create role**.

![Role RDS Access](../../images/role_rds_2.png)

2. Under **Create role** interface

- **Select trusted entity**

  - Trusted enty type: **AWS service**.
    ![Role RDS Access](../../images/role_rds_3.png)
  - Use case: **EC2**.
  - Click **Next**.
    ![Role RDS Access](../../images/role_rds_4.png)

- **Add permissions**

  - Search for `AmazonRDSFullAccess`
  - Select the **checkbox** next to it.
  - Click **Next**.
    ![Role RDS Access](../../images/role_rds_5.png)

- **Name, review, and create**
  - Name: `ec2-rds-role`
  - Description: `Allows EC2 instances to call AWS RDS services`
    ![Role RDS Access](../../images/role_rds_6.png)
  - Review your configuration and click **Create role**.
    ![Role RDS Access](../../images/role_rds_7.png)

3. Check your created IAM role
   ![Role RDS Access](../../images/role_rds_8.png)
