---
title: 'Import data'
date: '`r Sys.Date()`'
weight: 1
chapter: false
pre: ' <b> 5.1 </b> '
---

{{% notice info %}}
We assume that you have had **MySQL shell** or config MySQL command on your terminal.
{{% /notice %}}

### Import data from on-premise database to RDS database

In this part, we create `backup.sql` storing data of the on-premise database and import them into the RDS database.

- Open your terminal in the folder in which your backup file will be stored.
- Enter this command:
  ```
  mysqldump -u username -p database_name > backup.sql
  ```
- Now you will open your **MobaXterm**:

  - Access the **EC2 instance** which you created and copy its **public IP**.
    ![Deployment](../../images/deploy_1.png)

- Create connection by **MobaXterm**

  - Enter **public IP** of EC2 instance
  - Specify usernaem: `ec2-user`
  - import created key-pair
    ![Deployment](../../images/deploy_2.png)

- Upload the **backup.sql** file into **EC2**
  ![Deployment](../../images/deploy_3.png)

- Now, we will connect to RDS database through EC2 instance:

  - Install the mysql command-line client from MariaDB.

    ```
    sudo dnf update -y
    ```

    ```
    sudo dnf install mariadb105
    ```

  {{% notice note %}}
  The **-y** option installs the updates without asking for confirmation. To examine updates before installing, omit this option.
  {{% /notice %}}
  ![Deployment](../../images/deploy_4.png?height=400)

- Connect to the **RDS DB instance**. Enter the following command. This action lets you connect to the RDS DB instance using the **MySQL client**.

  - Go to the RDS instance which you created and copy the endpoint.
    ![Deployment](../../images/deploy_5.png)

  {{% notice note %}}
  Substitute the DB instance endpoint (DNS name) for _endpoint_, and substitute the master username. Provide the master password that you used when prompted for a password.
  {{% /notice %}}

  - run command:

    ```sql
    mysql -h endpoint -P 3306 -u username -p
    ```

    ![Deployment](../../images/deploy_6.png)

- After connecting to **RDS database**, we execute these command step by step to import our backup data:
  ```sql
  mysql> create database bistro;
  ```
  ```sql
  mysql> use bistro;
  ```
  ```sql
  mysql> source backup.sql;
  ```

You will see all executing query.
![Deployment](../../images/deploy_7.png)
