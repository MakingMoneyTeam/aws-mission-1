---
title: 'CloudFormation'
date: '`r Sys.Date()`'
weight: 1
chapter: false
pre: ' <b> 1.1. </b> '
---

#### Định nghĩa

**CloudFormation** là một dịch vụ **Infrastructure as Code (IaC)** được cung cấp bởi Amazon Web Services (AWS). Nó cho phép bạn định nghĩa và quản lý toàn bộ infrastructure trên AWS của mình bằng cách sử dụng các template dễ đọc viết bằng định dạng JSON hoặc YAML.

![CloudFormation](../../../images/Working-of-AWS-CloudFormation.png)

#### Lợi ích

- **Đơn giản hóa việc quản lý infrastructure**: CloudFormation cho phép bạn định nghĩa các tài nguyên infrastructure (như instance EC2, bucket S3, nhóm bảo mật, v.v.) và cấu hình của chúng trong một file template dễ đọc (YAML hoặc JSON). Template này hoạt động như một bản thiết kế cho infrastructure của bạn, loại bỏ sự cần thiết cấu hình thủ công thông qua AWS console hoặc CLI.

- **Nhanh chóng nhân rộng infrastructure**: Tái sử dụng template CloudFormation của bạn để tạo các tài nguyên theo cách nhất quán và có thể lặp lại. Để tái sử dụng template, hãy mô tả các tài nguyên của bạn một lần và sau đó cung cấp chính xác các tài nguyên đó nhiều lần trong nhiều vùng khác nhau.

- **Dễ dàng kiểm soát và theo dõi các thay đổi đối với infrastructure**: Khi bạn cung cấp infrastructure của mình bằng CloudFormation, template CloudFormation mô tả chính xác những tài nguyên nào được cung cấp và cài đặt của chúng. Vì các template này là file văn bản, bạn chỉ cần theo dõi các khác biệt trong template của mình để theo dõi các thay đổi đối với infrastructure, tương tự như cách các nhà phát triển kiểm soát các phiên bản của mã nguồn.
