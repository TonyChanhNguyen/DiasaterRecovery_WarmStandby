---
title : "EC2"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 3.2 </b> "
---
### Update Launch Configuration and Auto Scaling Group (ASG)

1. Click [CloudFormation Stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks) to navigate to the dashboard in the Oregon (us-west-2) region.
2. Select stack name **warm-secondary**.
3. Then, click on **Update**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.1ec2.png?width=90pc)

4. At **Update stack** interface, click on **Next**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.2ec2.png?width=90pc)

5. At **Specify stack details** interface, select **yes** as **IsPromote**.
6. Then, click on **Next**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.3ec2.png?width=90pc)

7. At **Configure stack options** interface, scroll down and click on **Next**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.4ec2.png?width=90pc)

8. At **Review warm-secondary** interface, scroll down at the end of page. Check **I acknowledge that AWS CloudFormation might create IAM resources with custom names.** box.
9. Then, click on **Submit**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.5ec2.png?width=90pc)

10. Your stack is updating. It will take you about 5 minutes to complete.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.6ec2.png?width=90pc)

11. After 5 minutes, your stack is updated successfully.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.7ec2.png?width=90pc)


### Auto Scaling Group (ASG)
The following changes were made when you updated your CloudFormation template:
+ Launch Configuration was modified in order to connect your application to the newly promoted Aurora cluster.
+ Auto Scaling Group  was modified in order to scale out your EC2 capacity from 1 instance to 2 instances to match your primary region N. Virginia (us-east-1) EC2 capacity.
We can now be confident that when we failover, our secondary region Oregon (us-west-2) can handle production level request traffic.
1. Go to [Auto Scaling Groups](https://us-west-2.console.aws.amazon.com/ec2/home?region=us-west-2#AutoScalingGroups:) at region **Oregon (us-west-2)**.
2. Click on ASG name **warm-secondary-WebServerGroup-XXXXXXXXXXXX**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.8ec2.png?width=90pc)

3. Click on tab **Activity**.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.9ec2.png?width=90pc)

4. At **Activity history** feature, verify that there is an scale out activity your EC2 capacity from 1 instance to 2 instances.
![Failover EC2](../../images/3.failover/3.2.ec2/3.2.10ec2.png?width=90pc)












