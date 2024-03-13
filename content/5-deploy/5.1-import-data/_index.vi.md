---
title: 'Import data'
date: '`r Sys.Date()`'
weight: 1
chapter: false
pre: ' <b> 5.1 </b> '
---



{{% notice info %}}
Giả sử bạn đã có **MySQL shell** hoặc cấu hình lệnh MySQL trên terminal của mình.
{{% /notice %}}

### Import dữ liệu từ database on-premise sang database RDS

Trong phần này, chúng ta sẽ tạo `backup.sql` lưu trữ dữ liệu của database on-premise và import chúng vào database RDS.

- Mở terminal trong thư mục mà file backup sẽ được lưu trữ.
- Nhập lệnh này:
```sql
mysqldump -u username -p database_name > backup.sql
```
- Bây giờ bạn sẽ mở **MobaXterm**:
    - Truy cập **EC2 instance** mà bạn đã tạo và copy **địa chỉ IP public** của nó.
  ![Deployment](../../../images/deploy_1.png)

- Tạo kết nối bằng **MobaXterm**
    - Nhập **địa chỉ IP public** của EC2 instance
    - Chỉ định username: `ec2-user`
    - Import key-pair đã tạo
    ![Deployment](../../../images/deploy_2.png)

- Upload file **backup.sql** lên **EC2**
![Deployment](../../../images/deploy_3.png)

- Bây giờ, chúng ta sẽ kết nối đến database RDS thông qua EC2 instance:
    - Cài đặt client dòng lệnh mysql từ MariaDB.
    ```
    sudo dnf update -y
    ```
    ```
    sudo dnf install mariadb105
    ```

  {{% notice note %}}
  Tùy chọn **-y** cài đặt các bản cập nhật mà không yêu cầu xác nhận. Để kiểm tra các bản cập nhật trước khi cài đặt, hãy bỏ qua tùy chọn này.
  {{% /notice %}}
  ![Deployment](../../../images/deploy_4.png?height=400)

  Nhập lệnh sau để kiểm tra: 
    ```sql
    mysql —version
    ```

- Kết nối đến **RDS DB instance**. Nhập lệnh sau. Hành động này cho phép bạn kết nối đến RDS DB instance sử dụng **MySQL client**.

  - Truy cập RDS instance mà bạn đã tạo và copy endpoint.
  ![Deployment](../../../images/deploy_5.png)

 {{% notice note %}}
  Thay thế **endpoint** (tên DNS) của DB instance và thay thế **username** chính. Cung cấp mật khẩu chính mà bạn đã sử dụng khi được yêu cầu nhập mật khẩu.
 {{% /notice %}}

  - Chạy lệnh:
    ```sql
    mysql -h endpoint -P 3306 -u username -p
    ```

    ![Deployment](../../../images/deploy_6.png)

- Sau khi kết nối đến **RDS database**, chúng ta thực hiện các lệnh này từng bước để import dữ liệu backup:
```sql
mysql> create database bistro;
```
```sql
mysql> use bistro;
```
```sql
mysql> source backup.sql;
```
Bạn sẽ thấy tất cả các truy vấn đang được thực thi.
![Deployment](../../../images/deploy_7.png)


