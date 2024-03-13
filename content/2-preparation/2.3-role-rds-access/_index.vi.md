---
title: 'Khởi tạo quyền truy cập RDS'
date: '`r Sys.Date()`'
weight: 3
chapter: false
pre: ' <b> 2.3. </b> '
---

## Truy cập IAM và tạo Role cho EC2 truy cập RDS

1. Truy cập giao diện **IAM** và nhấp vào **Roles** (Vai trò).

![Role RDS Access](../../../images/role_rds_1.png)

-   Click vào **Tạo Role** (Create role).

![Role RDS Access](../../../images/role_rds_2.png)

2. Trong giao diện **Tạo Role** (Create role)

-   **Select trusted entity**
    -   Trusted enty type: **Dịch vụ AWS** (AWS service).
        ![Role RDS Access](../../../images/role_rds_3.png)
    -   Use case: **EC2**.
    -   Click vào **Tiếp theo** (Next).
        ![Role RDS Access](../../../images/role_rds_4.png)

-   **Thêm quyền** (Add permissions)
    -   Tìm kiếm `AmazonRDSFullAccess`
    -   Chọn **hộp kiểm** bên cạnh nó.
    -   Click vào **Tiếp theo** (Next).
            ![Role RDS Access](../../../images/role_rds_5.png)

-   **Đặt tên, xem xét và tạo** (Name, review, and create)

    -   Tên: `ec2-rds-role`
    -   Mô tả: `Cho phép các instance EC2 gọi các dịch vụ AWS RDS`
        ![Role RDS Access](../../../images/role_rds_6.png)
    -   Kiểm tra cấu hình của bạn và nhấp vào **Tạo Role** (Create role).
        ![Role RDS Access](../../../images/role_rds_7.png)

3. Kiểm tra Role IAM đã tạo của bạn
      ![Role RDS Access](../../../images/role_rds_8.png)
