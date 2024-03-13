---
title: 'Create EC2'
date: '`r Sys.Date()`'
weight: 3
chapter: false
pre: ' <b> 3. </b> '
---

1. Access EC2 Instances console

- Find **EC2** and click **Instances** to access Instances interface
  ![EC2](../images/ec2_1.png)

- Click **Launch Instance**
  ![EC2](../images/ec2_2.png)

2. Under **Launch an instance** interface

- **Name and tags**

  - name: `ec2-application`
    ![EC2](../images/ec2_3.png)

- **Application and OS Images (Amazon Machine Image)**

  - Quick Start: **Amazon Linux**
  - Amazon Machine Image (AMI): **Amazon Linux 2023 AMI**
  - Architecture: **64-bit (x86)**
    ![EC2](../images/ec2_4.png)

- **Instance type**
  - Instance type: **t2.micro**
- **Key pair**

  - Key pair name: Choose the available key pair or create a new key pair with **.pem** format
    ![EC2](../images/ec2_5.png)
  {{% notice note %}}
  A key pair consists of a public key and a private key that are used to encrypt and decrypt the communication between your instance and your device. You’ll need to download and save the private key file (.pem) to your device and change its permissions to make it readable only by you. You’ll also need to use a terminal or a shell program that supports SSH, such as PuTTY or Git Bash.
  {{% /notice %}}

- **Network settings**

  - Click Edit
  - VPC: Choose created VPC
  - Subnet: Choose public subnet
  - Auto-assign public IP: enable
  - Firewall: Select existing security group
  - Common security group: WebServerSecurity - The security group for public subnet
    ![EC2](../images/ec2_6.png)

- Click **Launch instance**
  ![EC2](../images/ec2_7.png)

- Back to your **EC2 console**.

  - In the navigation pane, choose **Instances** and select the instance that you created in the previous section. Then from Actions choose **Security**, and **Modify IAM Role**.
    ![EC2](../images/ec2_8.png)

  - On the **Modify IAM Role** page, choose the role that you created in the previous steps from the **IAM role** dropdown list. Then choose **Apply**.
    ![EC2](../images/ec2_9.png)
