---
title : "Vùng chính"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 2.2 </b> "
---

### Triển khai cấu hình mạng sử dụng Amazon CloudFormation Templates
1. Tạo cấu hình mạng trong vùng chính **N. Virginia (us-east-1)** bằng việc khởi tạo [CloudFormation Template](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=network-stack&templateURL=https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/NetworkStack.yaml).
2. Tại trang CloudFormation, nhấn **Next**.
![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.1primaryregion.png?width=90pc)

3. Tại trang **Specify stack details** interface, nhập tên stack ```network-stack```.
4. Sau đó, nhấn **Next**.
![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.2primaryregion.png?width=90pc)

5. Tại trang **Configure stack options**. Cuộn xuống và nhấn **Next**.
![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.3primaryregion.png?width=90pc)


6. Tại trang **Review network-stack**. Cuộn xuống và nhấn **Submit**.
![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.4primaryregion.png?width=90pc)

7. Stack hạ tầng mạng của bạn đang được khởi tạo.
![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.5primaryregion.png?width=90pc)

8. Sau khoảng 1 phút, stack của bạn sẽ được tạo thành công.
![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.6primaryregion.png?width=90pc)

### Triển khai ứng dụng
Tải mẫu tài nguyên để triển khai ứng dụng [tại đây](../../../WarmStandby_App.yml)
1. Đi đến [CloudFormation Stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1) trong vùng chính **N. Virginia (us-east-1)**
2. Tại trang CloudFormation, nhấn **Create Stack**.
3. Sau đó nhấn **With new resources (standard)**.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.7primaryregion.png?width=90pc)

4. Tại trang **Create stack**, chọn **Template is ready** tại **Prepare template**.
5. Chọn **Upload a template file** tại **Specify template**.
6. Nhấn **Choose file** và chọn tệp **WarmStandby_App.yml** mà bạn vừa tải xuống.
7. Sau đó, nhấn **Next**.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.8primaryregion.png?width=90pc)

8. Tại trang **Specify stack details**, nhập tên stack ```warm-primary```.
9. Giữ **yes** tại **IsPrimary**.
10. Giữ **no** tại **IsPromote**.
11. Giữ **/aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2** tại **LatestAmiId**.
12. Giữ **network-stack** tại **NetworkStackName** nếu bạn không thay đổi gì ở bước trước đó.
13. Sau đó, nhấn **Next**.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.9primaryregion.png?width=90pc)

14. Tại trang **Configure stack options**, cuộn xuống và nhấn **Next**.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.10primaryregion.png?width=90pc)

15. Tại trang **Review warm-primary**, cuộn xuống cuối trang.
16. Tích chọn ô **I acknowledge that AWS CloudFormation might create IAM resources with custom names.**
17. Sau đó, nhấn **Submit**.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.11primaryregion.png?width=90pc)

18. Stack ứng dụng của bạn đang được tạo. Nó sẽ mất khoảng 15 phút để hoàn tất.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.12primaryregion.png?width=90pc)

19. Sau khoảng 15 phút, stack của bạn được tạo thành công.

![Primary Region](../../../images/2.preparation/2.2.primaryregion/2.2.13primaryregion.png?width=90pc)