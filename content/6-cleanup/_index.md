---
title: 'Clean up resources'
date: '`r Sys.Date()`'
weight: 6
chapter: false
pre: ' <b> 6. </b> '
---

Please follow these step to clean up the resource:

1. Terminate EC2 instance

- Access the **EC2 Management Console**.
- In the left navigation bar, select **Instances**.
- Select **created EC2 Instances** related to the lab.
- Click **Actions**.
- Click **Manage Instance State**.
- Select **Terminate**.
- Click **Change State**.
  ![Deployment](../../images/cleanup_1.png)

2. Delete Stack of CloudFormation

- Access **CloudFormation console**.
- Choose the **stack** relating to lab.
- Click **delete**.
  ![Deployment](../../images/cleanup_2.png)

3. Delete the VPC

- Access **VPC console**.
- Choose **VPC** relating to the lab.
- Click **delete**.

{{% notice info %}}
When you delete **Stack** and **VPC** respectively, all related resources such as Subnets, Route table, Internet Gateway are also deleted.
{{% /notice %}}

4. Delete DB Instance

- Access the **RDS Management Console**.
- In the left navigation bar, select **Databases**.
- Select all **DB Instances** related to the lab.
- Click **Actions**.
- Click **Delete**.
- Enter `delete me` in the empty field.
- Click **Delete**.
  ![Deployment](../../images/cleanup_3.png)
- You also need to access **Subnet groups** and **delete** the related one.
  ![Deployment](../../images/cleanup_4.png)

5. Delete RDS snapshots

- Access the **RDS Management Console**.
- In the left navigation bar, select **Snapshots**.
- Select all **snapshots** related to the lab.
- Click **Actions**.
- Click **Delete snapshot**.
- Click **Delete**.
  ![Deployment](../../images/cleanup_5.png)

6. Delete Security groups

- Access the **VPC Console**.
- In the left navigation bar, select **Security Groups**.
- Select all **Security Groups** related to the lab.
- Click **Actions**.
- Click **Delete security groups**.
- Click **Delete**.
  ![Deployment](../../images/cleanup_6.png)
