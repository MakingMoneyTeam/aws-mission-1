---
title: 'Khởi tạo EC2'
date: '`r Sys.Date()`'
weight: 3
chapter: false
pre: ' <b> 3. </b> '
---


1. Truy cập bảng điều khiển **EC2 Instances** (Các Instance EC2)

- Tìm **EC2** và nhấp vào **Instances** (Các Instance) để truy cập vào giao diện Instances
  ![EC2](../../images/ec2_1.png)

- Nhấp vào **Khởi chạy Instance** (Launch Instance)
  ![EC2](../../images/ec2_2.png)

2. Trong giao diện **Khởi chạy Instance** (Launch an instance)

- **Tên và nhãn** (Name and tags)

    - Tên: `ec2-application`
    ![EC2](../../images/ec2_3.png)

- **Ảnh ứng dụng và hệ điều hành (Amazon Machine Image)** (Application and OS Images (Amazon Machine Image))

    - Khởi động nhanh: **Amazon Linux**
    - Amazon Machine Image (AMI): **Amazon Linux 2023 AMI**
    - Kiến trúc: **64-bit (x86)**
    ![EC2](../../images/ec2_4.png)

- **Loại Instance** (Instance type)

    - Loại Instance: **t2.micro**

- **Cặp khóa** (Key pair)
    - Tên cặp khóa: Chọn cặp khóa khả dụng hoặc tạo cặp khóa mới với định dạng **.pem**.
        ![EC2](../../images/ec2_5.png)
{{% notice note %}}
Cặp khóa (key pair) bao gồm một khóa công khai (public key) và một khóa riêng tư (private key) được sử dụng để mã hóa và giải mã giao tiếp giữa phiên bản của bạn (instance) và thiết bị của bạn. Bạn cần tải xuống và lưu tệp khóa riêng tư (.pem) vào thiết bị của mình và thay đổi quyền của nó để chỉ bạn có thể đọc được. Bạn cũng cần sử dụng terminal hoặc chương trình shell hỗ trợ SSH, chẳng hạn như PuTTY hoặc Git Bash.
{{% /notice %}}

- **Cài đặt mạng** (Network settings)

    - Nhấp vào **Chỉnh sửa** (Edit)
    - VPC: Chọn VPC đã tạo
    - Subnet: Chọn subnet công khai
    - Tự động gán IP công khai: bật
    - Tường lửa: Chọn nhóm bảo mật hiện tại
    - Nhóm bảo mật chung: WebServerSecurity - Nhóm bảo mật cho subnet công khai
    ![EC2](../../images/ec2_6.png)

- Nhấp vào **Khởi chạy Instance** (Launch instance)
  ![EC2](../../images/ec2_7.png)

- Quay lại bảng điều khiển **EC2** của bạn.

    - Trong bảng điều hướng, chọn **Instances** (Các Instance) và chọn instance bạn đã tạo ở phần trước. Sau đó, từ **Actions** (Hành động), chọn **Security** (Bảo mật) và **Modify IAM Role** (Sửa đổi Role IAM).
    ![EC2](../../images/ec2_8.png)

    - Trên trang **Modify IAM Role** (Sửa đổi Role IAM), chọn role bạn đã tạo trong các bước trước đó từ danh sách thả xuống **IAM role** (Role IAM). Sau đó chọn **Apply** (Áp dụng).
    ![EC2](../../images/ec2_9.png)
