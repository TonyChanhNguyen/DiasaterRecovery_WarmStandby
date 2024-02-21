---
title : "Kiểm tra chế độ dự phòng"
date :  "`r Sys.Date()`" 
weight : 3 
chapter : false
pre : " <b> 3.3 </b> "
---

1. Đi đến [CloudFormation Stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/stackinfo?filteringText=&filteringStatus=active&viewNested=true) ở khu vực **Oregon (us-west-2)**.
2. Chọn stack tên **warm-secondary**.
3. Nhấn vào thanh chuyển hướng **Outputs**.
4. Nhấn vào đường dẫn **WebsiteURL**.
![Verify Failover](../../../images/3.failover/3.3.verifyfailover/3.3.1verifyfailover.png?width=90pc)

5. Việc đăng nhập sẽ được tự động. Sau đó, nhấn vào giỏ hàng để thấy số lượng nếu nó đang hiển thị là 0.
![Verify Failover](../../../images/3.failover/3.3.verifyfailover/3.3.2verifyfailover.png?width=90pc)

6. Tất cả sản phẩm mà bạn đã thêm trước đó sẽ xuất hiện.
![Verify Failover](../../../images/3.failover/3.3.verifyfailover/3.3.3verifyfailover.png?width=90pc)

7. Sau khi đóng trang giỏ hàng, bạn sẽ thấy số lượng của giỏ hàng hiện tại đã được cập nhật giống với trước đó.
![Verify Failover](../../../images/3.failover/3.3.verifyfailover/3.3.4verifyfailover.png?width=90pc)


#### Chúc mừng, website của bạn đã được chuyển đổi dự phòng sang vùng thứ cấp **Oregon (us-west-2)** từ vùng chính **N. Virginia (us-east-1)** thành công.