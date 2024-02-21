---
title : "Warm Standby"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Warm Standby
Trong bài thực hành này, bạn sẽ trải qua chiến lược khắc phục thảm họa Warm Standby. Chiến lược khắc phục thảm họa Warm Standby có thời điểm khắc phục  /  Thời gian phục hồi (**Recovery Point Objective(RPO) / Recovery Time Objective (RTO)**) trong vòng vài phút. Đối với khu vực thứ cấp của chiến lược Warm Standby, dữ liệu sẽ hoạt động và cơ sở hạ tầng cốt lõi sẽ được cung cấp và các dịch vụ chạy với công suất tối thiểu.

Các ứng dụng hiện đang được triển khai tại khu vực chính N. Virginia (us-east-1). Oregon (us-west-2) sẽ là khu vực thứ cấp của bạn.

Ứng dụng mẫu của bạn là **Unishop**. Nó là một ứng dụng Spring Boot Java được triển khai trên một máy chủ Amazon Elastic Compute Cloud (EC2) sử dụng một mạng con công cộng. Vùng chứa dữ liệu của bạn là một CSDL Amazon Aurora  MySQL với giao diện người dùng được viết bằng bootstrap và được lưu trữ trên Amazon Simple Storage Service (S3).

Bài thực hành này tận dụng ưu điểm của Auto Scaling Groups (ASG) mà bạn sẽ sử dụng để khởi tạo máy chủ Amazon EC2 của bạn. Amazon Aurora Global Database được sử dụng để nhân bản dữ liệu Amazon Aurora MySQL của bạn đến khu vực thứ cấp. Bạn cũng sẽ tận dụng ưu điểm của việc chuyển tiếp hoạt động ghi vào bản sao ghi chỉ đọc Amazon Aurora (Amazon Aurora read replica write forwarding). Với việc kích hoạt tính nắng này, các thao tác ghi có thể được gửi đến bản sao ghi chỉ đọc ở khu vực thứ cấp, và sẽ được chuyển tiếp một cách liền mạch đến CSDL ghi trong khu vực chính thông qua kênh giao tiếp bảo mật.

CloudFormation sẽ được sử dụng để cấu hình cơ sở hạ tầng và triển khai ứng dụng. Cung cấp cơ sở hạ tầng của bạn với các phương thức cơ sở hạ tầng bằng code (IaC) là phương pháp tổt nhất. CloudFormation là một cách đơn giản để tăng tốc việc cung cấp dịch vụ đám mây với cơ sở hạ tầng bằng code


![Warm Standby](../images/warmstandby.png?width=60pc)