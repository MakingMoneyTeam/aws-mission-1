---
title: 'Khởi tạo DB Group Subnet'
date: '`r Sys.Date()`'
weight: 4
chapter: false
pre: ' <b> 2.4. </b> '
---

## Truy cập RDS và Tạo Nhóm Subnet cho Database

1. Truy cập giao diện **RDS** (Relational Database Service).

-   Nhấp vào **Nhóm subnet** (Subnet groups).
-   Nhấp vào **Tạo nhóm subnet DB** (Create DB subnet group).
        ![DB Group Subnet](../../../images/db_group_subnet_1.png)

2. Trong giao diện **Tạo nhóm subnet DB** (Create DB subnet group)

-   **Chi tiết nhóm subnet** (Subnet group details)

    -   Tên: `db-subnet-group`
    -   Mô tả: `Nhóm subnet Database Bistro`
    -   VPC: Chọn **VPC đã tạo**
        ![DB Group Subnet](../../../images/db_group_subnet_2.png)

-   **Thêm subnet** (Add subnets)
    -   Vùng sẵn sàng (Availability Zones): **ap-southeast-1a** và **ap-southeast-1b**
    -   Subnet: Chọn **2 CIDR subnet riêng** được đặt trong **2 vùng sẵn sàng khác nhau**
-   Nhấp vào **Tạo** (Create)
        ![DB Group Subnet](../../../images/db_group_subnet_3.png)
