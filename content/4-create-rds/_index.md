---
title: 'Create RDS'
date: '`r Sys.Date()`'
weight: 4
chapter: false
pre: ' <b> 4. </b> '
---

1. Access **Amazon RDS** console

- Click **Create database**

![RDS](../images/rds_1.png)

2. Under **Create database** console

- **Choose a database creation method**

  - Choose **Standard create**
    ![RDS](../images/rds_2.png?height=200)

- Engine options

  - Engine type: Choose **MySQL**
    ![RDS](../images/rds_3.png?height=500)

  - Edition: **MySQL Community**
  - Engine version: Choose your suitable version. In my case, the version is **MySQL 8.0.35**
    ![RDS](../images/rds_4.png?height=400)

- Template: Choose **Free tier**
  ![RDS](../images/rds_5.png?height=400)

- **Settings**

  - DB instance identifier: `bistro-database`
  - Credentials Settings
    - Master username: **your username**
    - Master password: **your password**

![RDS](../images/rds_6.png?height=500)

- **Instance configuration**

  - DB instance class: **db.t3.micro**
    ![RDS](../images/rds_7.png?height=400)

- **Conectivity**

  - Compute resource: **Connect to an EC2 compute resource**
  - EC2 instance: Choose **created EC2 - BistroCheese**
    ![RDS](../images/rds_8.png?height=500)

- DB subnet group: **Choose existing**
- Existing DB subnet groups: **db-subnet-groups** (this is group subnet that we created in the preparation)
- VPC security group (firewall): **Create new**
- New VPC security group name: `rds-ec2-sg`
  ![RDS](../images/rds_9.png?height=500)

- **Database authentication**
  - Database authentication options: **Password authentication**

{{% notice note %}}
You can also choose **IAM authentication** if you want to use AWS **Identity and Access Management (IAM)** to manage access to your database.
{{% /notice %}}
![RDS](../images/rds_10.png?height=300)

{{% notice note %}}
Under **Monitoring**, choose **Enable Enhanced Monitoring** and enter **60** as the granularity. This will enable the enhanced monitoring feature of Amazon RDS, which will collect and display metrics about your database instance every 60 seconds. You can also choose **Disable Enhanced Monitoring** if you don’t want to use this feature. You can also modify the monitoring role and the additional metrics settings later.
{{% /notice %}}

- **Additional configuration**
  - Initial database name: `bistro-database`
  - Backup retention period: choose **7 days**

{{% notice note %}}
This will enable the automated backup feature of Amazon RDS, which will take daily snapshots of your database and store them for 7 days. You can also choose Disable automatic backups if you don’t want to use this feature. You can also modify the backup window and the backup encryption settings later.
{{% /notice %}}
![RDS](../images/rds_11.png?height=500)

{{% notice info %}}
Please note that automated backups are currently supported for InnoDB storage engine only. If you are using MyISAM, refer to details here.
{{% /notice %}}

- Click **Create database**
  ![RDS](../images/rds_12.png?height=700)

{{% notice note %}}
When your database is created completely, if you check the Security group, you will see 2 new Security groups (ec2-rds-1, rds-ec2-1) that are created automatically to allow traffic from EC2 to come to the MySQL database.
{{% /notice %}}
