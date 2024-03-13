---
title: 'Create JAR file'
date: '`r Sys.Date()`'
weight: 2
chapter: false
pre: ' <b> 5.2 </b> '
---

## Tạo file Jar để deploy ứng dụng lên EC2 instance

- Truy cập EC2 instance bằng **MobaXterm** 
- Cài đặt **JDK 17**, bạn cũng có thể chọn phiên bản JDK khác phù hợp với phiên bản Java của bạn.

```
sudo yum install java-17-amazon-corretto
```

{{% notice info %}}
Vui lòng tham khảo link: [https://docs.aws.amazon.com/corretto/](https://docs.aws.amazon.com/corretto/) để chọn phiên bản JDK phù hợp.
{{% /notice %}}

- Chúng ta đã build một **file Jar** chứa ứng dụng của mình.

```
mvn clean install -DskipTests
```

- Bây giờ, chúng ta lại upload file Jar lên EC2 và chạy ứng dụng
  ![Deployment](../../../images/deploy_8.png)

- Để chạy ứng dụng, chúng ta nhập lệnh này:

```
java -jar restaurantmanagement-0.0.1-SNAPSHOT.jar
```

- Sau khi chạy ứng dụng:
  ![Deployment](../../../images/deploy_9.png)

- Tại đây, chúng ta sử dụng Postman để kiểm tra API của ứng dụng
  ![Deployment](../../../images/deploy_10.png)


