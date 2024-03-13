---
title: 'Create jar file'
date: '`r Sys.Date()`'
weight: 2
chapter: false
pre: ' <b> 5.2 </b> '
---

### Create Jar file to deploy your application into EC2 instance

- Install **JDK 17**, or you can choose the other version of JDK which is suitable to your Java version.

```
sudo yum install java-17-amazon-corretto
```

{{% notice info %}}
Please refer to this [link](https://docs.aws.amazon.com/corretto/) to choose your version of JDK.
{{% /notice %}}

- We have already built a **Jar file** containing our application.

```
mvn clean install -DskipTests
```

- Now, we again upload file Jar into EC2 and run our application
  ![Deployment](../../images/deploy_8.png)

- To run application, we enter this command:

```
java -jar restaurantmanagement-0.0.1-SNAPSHOT.jar
```

- After run application:
  ![Deployment](../../images/deploy_9.png)

- Here we use postman to test API of our application
  ![Deployment](../../images/deploy_10.png)
