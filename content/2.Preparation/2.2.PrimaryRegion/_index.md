---
title : "Primary region"
date : "`r Sys.Date()`"
weight : 2
chapter : false
pre : " <b> 2.2 </b> "
---

### Deploy Network Configuration using Amazon CloudFormation Templates
1. Create Network Infrastructure in primary region **N. Virginia (us-east-1)** by launching this [CloudFormation Template](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/template?stackName=network-stack&templateURL=https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/NetworkStack.yaml).
2. At CloudFormation interface, click on **Next**.
![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.1primaryregion.png?width=90pc)

3. At **Specify stack details** interface, input stack name ```network-stack```.
4. Then, click on **Next**.
![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.2primaryregion.png?width=90pc)

5. At **Configure stack options** interface. Scroll down and click on **Next**.
![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.3primaryregion.png?width=90pc)


6. At **Review network-stack** interface. Scroll down and click on **Submit**.
![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.4primaryregion.png?width=90pc)

7. Your network stack is creating.
![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.5primaryregion.png?width=90pc)

8. After a minute, your stack will be created successfully.
![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.6primaryregion.png?width=90pc)

### Deploy Application
Download template source to deploy application [here](../../WarmStandby_App.yml)
1. Go to [CloudFormation Stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1) in primary region **N. Virginia (us-east-1)**
2. At CloudFormation interface, click on **Create Stack**.
3. Then click on **With new resources (standard)**.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.7primaryregion.png?width=90pc)

4. At **Create stack** interface, choose **Template is ready** as **Prepare template**.
5. Select **Upload a template file** as **Specify template**.
6. Click on **Choose file** and select **WarmStandby_App.yml** file you had downloaded above.
7. Then, click on **Next**.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.8primaryregion.png?width=90pc)

8. At **Specify stack details** interface, input stack name ```warm-primary```.
9. Keep **yes** at **IsPrimary** parameter.
10. Keep **no** at **IsPromote** parameter.
11. Keep **/aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2** at **LatestAmiId** parameter.
12. Keep **network-stack** at **NetworkStackName** parameter unless you've changed it in the previous step.
13. Then, click on **Next**.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.9primaryregion.png?width=90pc)

14. At **Configure stack options** interface, scroll down and click on **Next**.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.10primaryregion.png?width=90pc)

15. At **Review warm-primary** interface, scroll down to the end of page.
16. Check at box **I acknowledge that AWS CloudFormation might create IAM resources with custom names.**
17. Then, click on **Submit**.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.11primaryregion.png?width=90pc)

18. Your application stack is creating. It will take you about 15 minutes to finish.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.12primaryregion.png?width=90pc)

19. After about 15 minutes, your stack had been created successfully.

![Primary Region](../../images/2.preparation/2.2.primaryregion/2.2.13primaryregion.png?width=90pc)


