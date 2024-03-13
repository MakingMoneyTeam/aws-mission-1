---
title: 'Khởi tạo CloudFormation'
date: '`r Sys.Date()`'
weight: 1
chapter: false
pre: ' <b> 2.1. </b> '
---

### 1. Chuẩn bị file khởi tạo CloudFormation

-   Bạn có thể sử dụng template có sẵn và tùy chỉnh nó theo tài liệu CloudFormation: CloudFormation Document: [https://docs.aws.amazon.com/codebuild/latest/userguide/cloudformation-vpc-template.html](https://docs.aws.amazon.com/codebuild/latest/userguide/cloudformation-vpc-template.html).

-   Hoặc bạn có thể sử dụng template mà chúng tôi cung cấp trong [mã nguồn](https://github.com/MakingMoneyTeam/cheese-bistro).

Với template được cung cấp của chúng tôi, nó triển khai một VPC, bao gồm một subnet public và một cặp subnet private trải rộng trên hai **Vùng sẵn sàng (Availability Zone)**, một **Internet Gateway** với một route mặc định trên các subnet public.

#### Cấu hình bao gồm:

-   EnvironmentName: `JourneyToCloud`
-   PrivateSubnet1CIDR: `10.192.21.0/24`
-   PrivateSubnet2CIDR: `10.192.20.0/24`
-   PublicSubnet1CIDR: `10.192.10.0/24`
-   VPC CIDR: `10.192.0.0/16`

### 2. Tạo CloudFormation Stack

1. Truy cập vào **AWS Management Console** của bạn.
2. Tìm **CloudFormation**.
3. Click vào **Stacks** (Các Stack).

![CloudFormation Stacks](../../../images/cloud_formation_stack_1.png)

{{% notice note %}}
Trong workshop này, chúng tôi sẽ sử dụng **vùng Singapore (ap-southeast-1)**. Nếu bạn muốn sử dụng một Vùng khác, hãy đảm bảo chuyển Vùng về Vùng bạn muốn sử dụng khi tạo các tài nguyên liên quan đến workshop.
{{% /notice %}}

4. Click **Tạo Stack** (Create stack).
      ![CloudFormation Stacks](../../../images/cloud_formation_stack_2.png)

5. Trong giao diện **Tạo Stack** (Create stack), chúng tôi chọn các thông số sau:

-   **Điều kiện tiên quyết - Chuẩn bị template**
      - Chuẩn bị template: **_Template đã sẵn sàng_**
-   **Chỉ định template**

-   Nguồn template: **_Tải lên file template_**

-   Tải lên file template: _Tải lên file có sẵn của bạn_

-   Click **Tiếp theo** (Next)
      ![CloudFormation Stacks](../../../images/cloud_formation_stack_3.png)

6. Trong giao diện **Chỉ định chi tiết Stack** (Specify stack details)

-   **Cung cấp tên stack**
      - Tên Stack: `AWSWorkshop`
-   **Tham số** (Parameters): Giống với tất cả các thuộc tính mà chúng tôi đã cung cấp trong file YML.

-   Click **Tiếp theo** (Next)

![CloudFormation Stacks](../../../images/cloud_formation_stack_4.png)

7. Trong giao diện **Cấu hình tùy chọn Stack** (Configure stack options)

-   Giữ nguyên lựa chọn mặc định với **Tags** (Nhãn), **Permissions** (Quyền) và **Stack failure options** (Tùy chọn thất bại Stack).

![CloudFormation Stacks](../../../images/cloud_formation_stack_5.png)

-   Click **Tiếp theo** (Next).

![CloudFormation Stacks](../../../images/cloud_formation_stack_6.png)

8. Trong giao diện **Xem xét và tạo** (Review and create), chúng tôi xem xét lại các tùy chọn của mình một lần nữa để đảm bảo mọi thứ được thiết lập chính xác như mong đợi. Sau đó, nhấp vào **Gửi** (Submit).

9. Sau khi gửi, chúng ta sẽ đợi cho đến khi quá trình hoàn tất. Sau đó, nhấp vào **Outputs** (Đầu ra) để xem kết quả.

![CloudFormation Stacks](../../../images/cloud_formation_stack_7.png)
![CloudFormation Stacks](../../../images/cloud_formation_stack_8.png)
