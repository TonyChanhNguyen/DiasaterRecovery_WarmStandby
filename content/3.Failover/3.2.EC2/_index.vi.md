---
title : "EC2"
date :  "`r Sys.Date()`" 
weight : 2 
chapter : false
pre : " <b> 3.2 </b> "
---

### Cập nhật Launch Configuration và Auto Scaling Group (ASG)

1. Nhấn [CloudFormation Stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks) để chuyển hướng đến trang chủ trong khu vực Oregon (us-west-2).
2. Chọn stack tên **warm-secondary**.
3. Sau đó, nhấn **Update**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.1ec2.png?width=90pc)

4. Tại trang **Update stack**, nhấn **Next**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.2ec2.png?width=90pc)

5. Tại trang **Specify stack details**, chọn **yes** tại **IsPromote**.
6. Sau đó, nhấn **Next**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.3ec2.png?width=90pc)

7. Tại trang **Configure stack options**, cuộn xuống và nhấn **Next**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.4ec2.png?width=90pc)

8. Tại trang **Review warm-secondary**, cuộn xuống cuối trang. Tích chọn ô **I acknowledge that AWS CloudFormation might create IAM resources with custom names.**
9. Sau đó, nhấn **Submit**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.5ec2.png?width=90pc)

10. Stack của bạn đang được cập nhật. Sẽ mất khoảng 5 phút để hoàn tất.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.6ec2.png?width=90pc)

11. Sau 5 phút, stack của bạn sẽ được cập nhật thành công.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.7ec2.png?width=90pc)


### Auto Scaling Group (ASG)
Sau khi bạn cập nhật CloudFormation template, sẽ có nhưng thay đổi như sau:
+ Launch Configuration được chỉnh sửa để kết nối tới ứng dụng của bạn với cụm Aurora mới được nâng cấp.
+ Auto Scaling Group được chỉnh sửa để mở rộng quy mô số lượng EC2 từ 1 lên 2 máy chủ bằng với lượng máy chủ của vùng chính N. Virginia (us-east-1).
Chúng ta bây giờ có thể tự tin rằng khi quá trình phục hồi, vùng thứ cấp Oregon (us-west-2) có thể xử lý tốt lưu lượng truy cập ở quy mô sản phẩm.
1. Đi đến [Auto Scaling Groups](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#AutoScalingGroups:) tại khu vực **Oregon (us-west-2)**.
2. Chọn ASG tên **warm-secondary-WebServerGroup-XXXXXXXXXXXX**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.8ec2.png?width=90pc)

3. Nhấn thanh chuyển hướng **Activity**.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.9ec2.png?width=90pc)

4. Tại tính năng **Activity history**, kiểm tra thấy rằng có một hoạt động mở rộng quy mô sô lượng máy chủ EC2 của bạn từ 1 lên 2.
![Failover EC2](/images/3.failover/3.2.ec2/3.2.10ec2.png?width=90pc)








