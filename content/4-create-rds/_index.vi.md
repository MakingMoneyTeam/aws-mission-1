---
title: 'Khởi tạo RDS'
date: '`r Sys.Date()`'
weight: 4
chapter: false
pre: ' <b> 4. </b> '
---


1. Truy cập bảng điều khiển **Amazon RDS** (Relational Database Service)

- Nhấp vào **Tạo database** (Create database)

![RDS](../../images/rds_1.png)

2. Trong giao diện **Tạo database** (Create database)

- **Chọn phương thức tạo database** (Choose a database creation method)
    - Chọn **Tạo tiêu chuẩn** (Standard create)
    ![RDS](../../images/rds_2.png?height=200)

- Tùy chọn Engine
    - Loại Engine: Chọn **MySQL**
    ![RDS](../../images/rds_3.png?height=500)
    - Phiên bản: **MySQL Community**
    - Phiên bản Engine: Chọn phiên bản phù hợp của bạn. Trong trường hợp này, phiên bản là **MySQL 8.0.35**
    ![RDS](../../images/rds_4.png?height=400)

- Template: Chọn **Free tier** (Hạng miễn phí)
    ![RDS](../../images/rds_5.png?height=400)

- **Cài đặt** (Settings)
    - Nhãn định danh instance DB: `bistro-database`
    - Cài đặt thông tin đăng nhập
        - Tên người dùng master: **tên người dùng của bạn**
        - Mật khẩu master: **mật khẩu của bạn**

![RDS](../../images/rds_6.png?height=500)

- **Cấu hình Instance** (Instance configuration)
    - Lớp Instance DB: **db.t3.micro**
    ![RDS](../../images/rds_7.png?height=400)

- **Kết nối** (Connectivity)
    - Tài nguyên tính toán: **Kết nối với tài nguyên tính toán EC2**
    - Instance EC2: Chọn **EC2 đã tạo - BistroCheese**
    ![RDS](../../images/rds_8.png?height=500)

- Nhóm subnet DB: **Chọn nhóm hiện tại**
- Nhóm subnet DB hiện tại: **db-subnet-groups** (đây là nhóm subnet mà chúng ta đã tạo trong phần chuẩn bị)
- Nhóm bảo mật VPC (tường lửa): **Create new**
- Tên nhóm bảo mật VPC mới: `rds-ec2-sg`
{{% notice note %}}
Đây sẽ tạo một nhóm bảo mật (security group) mới cho phép lưu lượng truy cập đến trên cổng 3306 (cổng mặc định của MySQL) từ bất kỳ địa chỉ IP nào. Bạn cũng có thể chọn **Choose existing** và chọn một nhóm bảo mật hiện có có cùng quy tắc. Bạn cũng có thể sửa đổi quy tắc sau này để giới hạn quyền truy cập vào cơ sở dữ liệu của mình từ các địa chỉ IP hoặc khối CIDR cụ thể.
{{% /notice %}}
    ![RDS](../../images/rds_9.png?height=500)

- **Xác thực Database** (Database authentication)
    - Tùy chọn xác thực Database: **Xác thực bằng mật khẩu (Password authentication)** 

{{% notice note %}}
Bạn cũng có thể chọn **Xác thực IAM** (IAM authentication) nếu bạn muốn sử dụng **Identity and Access Management (IAM)** của AWS để quản lý quyền truy cập vào database của bạn.
{{% /notice %}}

![RDS](../../images/rds_10.png?height=300)

{{% notice note %}}
Trong phần **Giám sát** (Monitoring), chọn **Bật Giám sát nâng cao (Enable Enhanced Monitoring)**  và nhập **60** làm mức chi tiết. Tùy chọn này sẽ kích hoạt tính năng giám sát nâng cao của Amazon RDS, tính năng này sẽ thu thập và hiển thị các số liệu về instance database của bạn cứ 60 giây. Bạn cũng có thể chọn **Vô hiệu hóa Giám sát nâng cao (Disable Enhanced Monitoring)**  nếu bạn không muốn sử dụng tính năng này. Bạn cũng có thể sửa đổi vai trò giám sát và các cài đặt số liệu bổ sung sau này.
{{% /notice %}}

- **Cấu hình bổ sung** (Additional configuration)
    - Tên database ban đầu: `bistro-database`
    - Thời gian lưu giữ sao lưu: chọn **7 ngày**

{{% notice note %}}
Tùy chọn này sẽ kích hoạt tính năng sao lưu tự động của Amazon RDS, tính năng này sẽ chụp ảnh nhanh database của bạn hàng ngày và lưu trữ chúng trong 7 ngày. Bạn cũng có thể chọn **Vô hiệu hóa sao lưu tự động** (Disable automatic backups) nếu bạn không muốn sử dụng tính năng này. Bạn cũng có thể sửa đổi cửa sổ sao lưu và cài đặt mã hóa sao lưu sau này.
{{% /notice %}}

![RDS](../../images/rds_11.png?height=500)

{{% notice info %}}
Hiện tại, sao lưu tự động chỉ được hỗ trợ cho engine lưu trữ InnoDB. Nếu bạn đang sử dụng MyISAM, hãy tham khảo chi tiết tại đây
{{% /notice %}}

- Click **Create database**
  ![RDS](../../images/rds_12.png?height=700)

{{% notice note %}}
Khi database của bạn được tạo hoàn tất, nếu bạn kiểm tra Nhóm bảo mật (Security group), bạn sẽ thấy 2 nhóm bảo mật mới (ec2-rds-1, rds-ec2-1) được tạo tự động để cho phép lưu lượng truy cập từ EC2 đến database MySQL.
{{% /notice %}}