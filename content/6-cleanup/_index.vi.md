---
title: 'Dọn dẹp tài nguyên'
date: '`r Sys.Date()`'
weight: 6
chapter: false
pre: ' <b> 6. </b> '
---

## Dọn dẹp tài nguyên

Hãy thực hiện theo các bước sau để dọn dẹp tài nguyên:

1. **Terminate EC2 instance**

- Truy cập **Bảng điều khiển quản lý EC2**.
- Trong thanh điều hướng bên trái, chọn **Instances (Các phiên bản)**.
- Chọn các **Phiên bản EC2 đã tạo** liên quan đến bài thực hành.
- Click **Actions (Hành động)**.
- Click **Manage Instance State (Quản lý trạng thái phiên bản)**.
- Chọn **Terminate (Kết thúc)**.
- Click **Change State (Thay đổi trạng thái)**.
  ![Deployment](../../images/cleanup_1.png)

2. **Xóa Stack của CloudFormation**

- Truy cập **Bảng điều khiển CloudFormation**.
- Chọn **Stack (Ngăn xếp)** liên quan đến bài thực hành.
- Click **Delete (Xóa)**.
  ![Deployment](../../images/cleanup_2.png)

3. **Xóa VPC**

- Truy cập **Bảng điều khiển VPC**.
- Chọn **VPC** liên quan đến bài thực hành.
- Click **Delete (Xóa)**.

{{% notice info %}}
Khi bạn xóa **Stack (Ngăn xếp)** và **VPC**, tất cả các tài nguyên liên quan như Subnets (Mạng con), Route table (Bảng tuyến), Internet Gateway (Cổng internet) cũng sẽ bị xóa.
{{% /notice %}}

4. **Xóa DB Instance (Phiên bản DB)**

- Truy cập **Bảng điều khiển quản lý RDS**.
- Trong thanh điều hướng bên trái, chọn **Databases (Cơ sở dữ liệu)**.
- Chọn tất cả các **DB Instances (Phiên bản DB)** liên quan đến bài thực hành.
- Click **Actions (Hành động)**.
- Click **Delete (Xóa)**.
- Nhập `delete me` vào ô trống.
- Click **Delete (Xóa)**.
  ![Deployment](../../images/cleanup_3.png)
- Bạn cũng cần truy cập **Subnet groups (Nhóm mạng con)** và **xóa** nhóm liên quan.
  ![Deployment](../../images/cleanup_4.png)

5. **Xóa Snapshot (Bản chụp) RDS**

- Truy cập **Bảng điều khiển quản lý RDS**.
- Trong thanh điều hướng bên trái, chọn **Snapshots (Bản chụp)**.
- Chọn tất cả các **Snapshots (Bản chụp)** liên quan đến bài thực hành.
- Click **Actions (Hành động)**.
- Click **Delete snapshot (Xóa bản chụp)**.
- Click **Delete (Xóa)**.
  ![Deployment](../../images/cleanup_5.png)

6. **Xóa Security Groups (Nhóm bảo mật)**

- Truy cập **Bảng điều khiển VPC**.
- Trong thanh điều hướng bên trái, chọn **Security Groups (Nhóm bảo mật)**.
- Chọn tất cả các **Security Groups (Nhóm bảo mật)** liên quan đến bài thực hành.
- Click **Actions (Hành động)**.
- Click **Delete security groups (Xóa nhóm bảo mật)**.
- Click **Delete (Xóa)**.
  ![Deployment](../../images/cleanup_6.png)
