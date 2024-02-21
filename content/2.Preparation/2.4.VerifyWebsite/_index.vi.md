---
title : "Kiểm tra website"
date :  "`r Sys.Date()`" 
weight : 4
chapter : false
pre : " <b> 2.4 </b> "
---

### Vùng chính
1. Nhấn [CloudFormation Stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/outputs?stackId=arn%3Aaws%3Acloudformation%3Aus-east-1%3A170074558790%3Astack%2Fwarm-primary%2Ff3b77310-a64e-11ee-a8d3-0e16b347cb43&filteringText=&filteringStatus=active&viewNested=true) để chuyển hướng đến giao diện tại khu vực **N. Virginia (us-east-1)**.
2. Chọn stack **warm-primary**.
3. Nhấn thanh điều hướng **Output**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.1verifywebsite.png?width=90pc)

4. Nhấn vào đường dẫn **WebsiteURL** và mở nó trong trình duyệt web.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.2verifywebsite.png?width=90pc)

5. Tại trang web, nhấn **Sign up** để tạo tài khoản.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.3verifywebsite.png?width=89pc)

6. Nhập các thông tin cần thiết để tạo tài khoản.
7. Sau dó, nhấn **Signup** để hoàn tất bước này.

{{%notice warning%}}
Lưu trữ các thông tin này lại để cung cấp cho các bước tiếp theo.
{{%/notice%}}
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.4verifywebsite.png?width=90pc)

8. Nhấn **Log in**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.5verifywebsite.png?width=89pc)
9. Nhập các thông tin mà bạn đã điền.
10. Sau đó, nhấn **Login**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.6verifywebsite.png?width=90pc)

11. Sau khi đăng nhập thành công, nhấn vào sản phẩm **Unicorn** bạn muốn. Sau đó nhấn **Add to cart** để thêm vào giỏ hàng của bạn.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.7verifywebsite.png?width=90pc)

12. Sau khi thêm sản phẩm **Unicorn** vào giỏ hàng thành công, kiểm tra biểu tượng **Cart** để thấy số lượng đã được tăng lên.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.8verifywebsite.png?width=90pc)

13. Lặp lại bước 12 để thêm nhiều sản phẩm hơn vào giỏ hàng.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.9verifywebsite.png?width=90pc)

14. Sau khi hoàn tất các bước trên. Lưu lại số lượng của giỏ hàng và khu vực của nó. Chúng ta sẽ kiểm tra chúng lại sau khi thực hiện nhân bản ứng dụng web đến vùng thứ cấp.

{{%notice note%}}
Trong trường hợp này, số lượng ở giỏ hàng là **4** và khu vực là **us-east-1** (Vùng chính).
{{%/notice%}}
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.10verifywebsite.png?width=90pc)


### Vùng thứ cấp
Bạn đang tận dụng ưu điểm của việc chuyển tiếp hoạt động ghi vào bản sao ghi chỉ đọc Amazon Aurora (Amazon Aurora read replica write forwarding). Với việc kích hoạt tính nắng này, các thao tác ghi có thể được gửi đến bản sao ghi chỉ đọc ở khu vực thứ cấp, và sẽ được chuyển tiếp một cách liền mạch đến CSDL ghi trong khu vực chính thông qua kênh giao tiếp bảo mật. Đây được coi là phương pháp hay nhất để cho phép chuyển tiếp ghi trong khu vực thứ cấp của bạn cho chiến lược khắc phục thảm họa Warm Standby nhằm mục đích thử nghiệm.

1. Đi đến [CloudFormation Stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/outputs?stackId=arn%3Aaws%3Acloudformation%3Aus-west-2%3A170074558790%3Astack%2Fwarm-secondary%2F382932c0-a7b4-11ee-b063-02dd47a763df&filteringText=&filteringStatus=active&viewNested=true) tại khu vực **Oregon (us-west-2)**.
2. Chọn stack **warm-secondary** .
3. Nhấn vào thành chuyển hướng **Outputs**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.11verifywebsite.png?width=90pc)

4. Nhấn vào đường dẫn **WebsiteURL** và mở nó trong trình duyệt web.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.12verifywebsite.png?width=90pc)

5. Tại trang web bạn có thể thấy hiện giờ khu vực là **us-west-2**, sau đó nhấn **Log in**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.13verifywebsite.png?width=90pc)

6. Điền tất cả thông tin đã tạo ở vùng chính **N. Virginia (us-east-1)**.
7. Nhấn **Log in**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.14verifywebsite.png?width=90pc)

8. Bạn sẽ thấy số lượng ở giỏ hàng sẽ giống với số lượng mà bạn đã thêm ở vùng chính **N. Virginia (us-east-1)**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.15verifywebsite.png?width=90pc)

9. Hãy thêm sản phẩm vào giỏ hàng. 
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.16verifywebsite.png?width=90pc)

{{%notice note%}}
Tại thời điểm này, số lượng trong giỏ hàng là **6** và khu vực là **us-west-2** (Vùng thứ cấp).
{{%/notice%}}

10. Trở lại trang web của vùng chính **N. Virginia (us-east-1)** và kiểm tra giỏ hàng. Số lượng ở giỏ hàng hiện tại là **6**, giống tại vùng thứ cấp **Oregon (us-west-2)**.
![Verify website](../../../images/2.preparation/2.4.verifywebsite/2.4.17verifywebsite.png?width=90pc)