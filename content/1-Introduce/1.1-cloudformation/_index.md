---
title: 'CloudFormation'
date: '`r Sys.Date()`'
weight: 1
chapter: false
pre: ' <b> 1.1. </b> '
---

#### Definition

**CloudFormation** is an **Infrastructure as Code (IaC)** service offered by Amazon Web Services (AWS). It allows you to define and manage your entire AWS infrastructure using human-readable templates written in JSON or YAML format.

![CloudFormation](../../images/Working-of-AWS-CloudFormation.png)

#### Benifits

- **Simplify infrastructure management**: CloudFormation allows you to define your infrastructure resources (like EC2 instances, S3 buckets, security groups, etc.) and their configurations in a human-readable template file (YAML or JSON). This template acts as a blueprint for your infrastructure, eliminating the need for manual configuration through the AWS console or CLI.
- **Quickly replicate your infrastructure**: Reusing your CloudFormation template to create your resources in a consistent and repeatable manner. To reuse your template, describe your resources once and then provision the same resources over and over in multiple regions.
- **Easily control and track changes to your infrastructure**: When you provision your infrastructure with CloudFormation, the CloudFormation template describes exactly what resources are provisioned and their settings. Because these templates are text files, you simply track differences in your templates to track changes to your infrastructure, similar to the way developers control revisions to source code.
