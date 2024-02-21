---
title : "Dọn dẹp tài nguyên"
date :  "`r Sys.Date()`" 
weight : 4 
chapter : false
pre : " <b> 4. </b> "
---

### Dọn dẹp S3 
1. Đi đến [S3](https://s3.console.aws.amazon.com/s3/home).
2. Chọn **warm-primary-uibucket-xxxx**.
3. Nhấn **Empty**.
![Cleanup Resources](/images/4.cleanup/4.1cleanup.png?width=90pc)

4. Nhập ```permanently delete```.
5. Sau đó, nhấn **Empty**.
![Cleanup Resources](/images/4.cleanup/4.2cleanup.png?width=90pc)

6. Lặp lại các bước trên với bucket tên **warm-secondary-uibucket-xxxx**.


### Dọn dẹp CSDL
#### Vùng chính
1. Đi đến [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-east-1#databases:) in **N. Virginia (us-east-1)** region.
2. Chọn CSDL **unishop-warm** bên dưới cụm **warm-primary**.
3. Nhấn **Action**.
4. Sau đó nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.3cleanup.png?width=90pc)
5. Nhập ```delete me```.
6. Nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.4cleanup.png?width=90pc)

7. Sau khi CSDL **unishop-warm** đã được xóa, chọn cụm **warm-primary**.
8. Nhấn **Actions**.
9. Nhấn **Remove from global database**.
![Cleanup Resources](/images/4.cleanup/4.5cleanup.png?width=90pc)

10. Nhấn **Remove and promote**.
![Cleanup Resources](/images/4.cleanup/4.6cleanup.png?width=90pc)

11. Sau khi loại bỏ khỏi CSDL toàn cầu, chọn cụm **warm-primary**.
12. Nhấn **Actions**.
13. Nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.7cleanup.png?width=90pc)


14. Bỏ chọn ô **Create final snapshot**.
15. Chọn ô **I acknowledge that upon instance...**.
16. Nhập ```delete me```.
17. Sau đó, nhấn **Delete DB sluster**.
![Cleanup Resources](/images/4.cleanup/4.8cleanup.png?width=90pc)

#### Vùng thứ cấp
1. Đi đến [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:) ở khu vực **Oregon (us-west-2)**.
2. Lặp lại tất cả các bước trên để xóa CSDL **unishop-warm** trước tiên, sau đó xóa cụm **warm-secondary**.

Sau khi CSDL và cụm đã được xóa, chúng ta tiến hành xóa **Global database**.

3. Chọn **warm-global**.
4. Nhấn **Actions**.
5. Nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.9cleanup.png?width=90pc)

6. Nhập ```delete me```.
7. Nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.10cleanup.png?width=90pc)


### Dọn dẹp CloudFormation ở vùng thứ cấp
1. Đi đến [CloudFormation stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/outputs?filteringText=&filteringStatus=active&viewNested=true) ở khu vực **Oregon (us-west-2)**.
2. Chọn stack tên **warm-secondary**.
3. Sau đó nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.11cleanup.png?width=90pc)

4. Nhấn **Delete** để xác nhận xóa. 
![Cleanup Resources](/images/4.cleanup/4.12cleanup.png?width=90pc)

5. Sau khi stack **warm-secondary** được xóa, chọn stack tên **network-stack**.
6. Sau đó nhấn **Delete**.
![Cleanup Resources](/images/4.cleanup/4.13cleanup.png?width=90pc)

7. Nhấn **Delete** để xác nhận xóa. 
![Cleanup Resources](/images/4.cleanup/4.14cleanup.png?width=90pc)

### Dọn dẹp CloudFormation ở vùng chính
1. Đi đến [CloudFormation stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringText=&filteringStatus=active&viewNested=true) ở khu vực **N. Virginia (us-east-1)**.

2. Lặp lại các bước tên để xóa stack tên **warm-primary** trước tiên, sau đó xóa stack tên **network-stack**.

### Dọn dẹp S3 bucket
1. Đi đến [S3](https://s3.console.aws.amazon.com/s3/home).
2. Chọn bucket tên **cf-templates-xxxxxxxxxxxxx-us-east-1**.
3. Nhấn **Empty**.
![Cleanup Resources](/images/4.cleanup/4.15cleanup.png?width=90pc)

4. Nhập ```permanently delete```.
5. Sau đó, nhấn **Empty**.
![Cleanup Resources](/images/4.cleanup/4.16cleanup.png?width=90pc)

6. Sau đó chọn lại bucket tên **cf-templates-xxxxxxxxxxxxx-us-east-1**.
7. Nhấn **Delete**.

![Cleanup Resources](/images/4.cleanup/4.17cleanup.png?width=90pc)

8. Nhập tên bucket để xác nhận xóa.
9. Nhấn **Delete bucket**.
![Cleanup Resources](/images/4.cleanup/4.18cleanup.png?width=90pc)

10. Lặp lại các bước tên với bucket tên **cf-templates-xxxxxxxxxxxxx-us-west-2**.


#### Chúc mừng, bạn đã hoàn thành bài thực hành này! 