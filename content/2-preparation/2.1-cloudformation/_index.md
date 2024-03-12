---
title: 'Create CloudFormation'
date: '`r Sys.Date()`'
weight: 1
chapter: false
pre: ' <b> 2.1. </b> '
---

### 1. Prepare file to initialize CloudFormation

- You can use the template and modify it from the [CloudFormation Document](https://docs.aws.amazon.com/codebuild/latest/userguide/cloudformation-vpc-template.html).

- Or you can use the template that we provide in our [source code]().

With our provided template, it deploys a VPC, with a public and a pair of private subnets spread across two **Availability Zones (AZ)**.

It deploys an **internet gateway**, with a default route on the public subnets.

#### The configuration includes:

- EnvironmentName: `JourneyToCloud`
- PrivateSubnet1CIDR: `10.192.21.0/24`
- PrivateSubnet2CIDR: `10.192.20.0/24`
- PublicSubnet1CIDR: `10.192.10.0/24`
- VPC CIDR: `10.192.0.0/16`

### 2. Create the CloudFormation Stack

1. Access to your **AWS Management Console**.
2. Find the **CloudFormation**.
3. Click **Stacks**.

![CloudFormation Stacks](../../images/cloud_formation_stack_1.png)
{{% notice note %}}
In this workshop, we will use the **Singapore region (ap-southeast-1)**. If you want to use another Region, be sure to move the Region back to the Region you want to use when creating workshop-related resources.
{{% /notice %}}

4. Click **Create stack**.
   ![CloudFormation Stacks](../../images/cloud_formation_stack_2.png)

5. Under **Create stack** Interface, we choose the following parameters:

- **Prerequisite - Prepare template**
  - Prepare template: **_Template is ready_**
- **Specify template**

  - Template source: **_Upload a template file_**

  - Upload a template file: _Upload your available file_

- Click **Next**
  ![CloudFormation Stacks](../../images/cloud_formation_stack_3.png)

6. Under the **Specify stack details** interface

- **Provide a stack name**
  - Stack name: `AWSWorkshop`
- **Parameters**: It is similar to all attributes that we provided in the YML file.

- Click **Next**

![CloudFormation Stacks](../../images/cloud_formation_stack_4.png)

7. Under the **Configure stack options** interface

- With the **Tags**, **Permissions**, and **Stack failure options**, we remain the default choice.

![CloudFormation Stacks](../../images/cloud_formation_stack_5.png)

- Click **Next**.

![CloudFormation Stacks](../../images/cloud_formation_stack_6.png)

8. Under the **Review and create** interface, we review our options again to ensure everything is set up properly as we expect. Then click **Submit**.

9. After submitting, we will wait until the progress is completed. Then click **Outputs** to see the result.

![CloudFormation Stacks](../../images/cloud_formation_stack_7.png)
![CloudFormation Stacks](../../images/cloud_formation_stack_8.png)
