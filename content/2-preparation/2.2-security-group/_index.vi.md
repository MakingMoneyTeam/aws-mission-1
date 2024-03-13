---
title: 'Khởi tạo Security Group'
date: '`r Sys.Date()`'
weight: 2
chapter: false
pre: ' <b> 2.2. </b> '
---

## Truy cập Nhóm bảo mật (Security Group)

1. Click vào **Nhóm bảo mật** (Security Group).
       ![Security Group](../../../images/security_group_1.png)

2. Trong giao diện **Tạo nhóm bảo mật** (Create Security Group)

-   **Chi tiết cơ bản** (Basic details)

- Tên nhóm bảo mật: `WebServerSecurity`
    - Mô tả: `Cho phép truy cập lưu lượng đến ứng dụng web server`
    - VPC: **_Hãy nhớ chọn VPC mà bạn đã tạo_**
        ![Security Group](../../../images/security_group_2.png)

-   **Luật vào** (Inbound rule)

- Cho phép giao thức **SSH** - Nguồn: Địa chỉ IP của tôi
    - Cho phép **ICMP - IPV4** - Nguồn: Địa chỉ IP của tôi
    - Cho phép **TCP tùy chỉnh** - Port **8080** (port mặc định của ứng dụng Spring Boot) - Nguồn: bất kỳ

-   Giữ nguyên **Luật ra** (Outbound rule), và click vào **Tạo nhóm bảo mật** (Create security group).
        ![Security Group](../../../images/security_group_3.png)

3. Kiểm tra kết quả trong **Nhóm bảo mật** (Security groups).
      ![Security Group](../../../images/security_group_4.png)
