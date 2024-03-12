---
title: 'Amazon RDS'
date: '`r Sys.Date()`'
weight: 2
chapter: false
pre: ' <b> 1.2. </b> '
---

#### Định nghĩa

**Amazon Relational Database Service (Amazon RDS)** là một tập hợp các dịch vụ được quản lý giúp đơn giản hóa việc thiết lập, vận hành và mở rộng quy mô cơ sở dữ liệu trên đám mây. Amazon RDS hỗ trợ nhiều engine database phổ biến, chẳng hạn như MySQL, PostgreSQL, Oracle, SQL Server và MariaDB.

![Amazon RDS](../../../images/AmazonRDS.png)

#### Lợi ích

- **Sao lưu, phục hồi và chụp nhanh tự động**: Tự động sao lưu, phục hồi và tạo ảnh chụp nhanh của cơ sở dữ liệu.
- **Cập nhật và vá lỗi phần mềm tự động**: Áp dụng các bản vá lỗi và cập nhật phần mềm cho engine database tự động.
- **Tự động mở rộng dung lượng lưu trữ và tài nguyên tính toán**: Tự động điều chỉnh dung lượng lưu trữ và tài nguyên tính toán cần thiết cho cơ sở dữ liệu.
- **Thất bại tự động và tính khả dụng cao**: Tự động chuyển đổi sang bản sao dự phòng trong trường hợp sự cố và đảm bảo tính khả dụng cao của cơ sở dữ liệu.
- **Mã hóa và bảo mật tự động**: Tự động mã hóa dữ liệu và áp dụng các biện pháp bảo mật cho cơ sở dữ liệu.
- **Giám sát và thu thập dữ liệu tự động**: Tự động theo dõi và thu thập các số liệu về tình trạng hoạt động của cơ sở dữ liệu.

Amazon RDS cũng cung cấp cho bạn tính linh hoạt để **_tùy chỉnh_** các cài đặt cơ sở dữ liệu của mình, chẳng hạn như:

- Lựa chọn engine database và phiên bản
- Lựa chọn loại và kích thước instance
- Lựa chọn loại và kích thước lưu trữ
- Lựa chọn vùng sẵn sàng (Availability Zone) và vùng (Region)
- Lựa chọn nhóm bảo mật (Security Group) và VPC
- Lựa chọn nhóm tham số (Parameter Group) và nhóm tùy chọn (Option Group)
- Lựa chọn cửa sổ bảo trì và cửa sổ sao lưu

Với Amazon RDS, bạn có thể tập trung vào logic ứng dụng và dữ liệu của mình, mà không cần lo lắng về infrastructure nền tảng và việc quản trị cơ sở dữ liệu.

Ngoài ra, bạn còn có thể tận dụng khả năng tích hợp của Amazon RDS với các dịch vụ AWS khác, chẳng hạn như Amazon EC2, Amazon S3, Amazon Lambda và Amazon CloudFormation.
