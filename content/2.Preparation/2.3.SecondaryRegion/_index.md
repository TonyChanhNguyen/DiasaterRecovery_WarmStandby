---
title : "Secondary region"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 2.3 </b> "
---

### Deploy Network Configuration using Amazon CloudFormation Templates
1. Create Network Infrastructure in secondary region **Oregon (us-west-2)** by launching this [CloudFormation Template](https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/template?stackName=network-stack&templateURL=https://ws-assets-prod-iad-r-pdx-f3b3f9f1a7d6a3d0.s3.us-west-2.amazonaws.com/6b7a41c6-3cae-45f2-bf2c-72c64b55d920/NetworkStack.yaml).
2. At CloudFormation interface, click on **Next**.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.1secondaryregion.png?width=90pc)


3. At **Specify stack details** interface, input stack name ```network-stack```.
4. Then, click on **Next**.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.2secondaryregion.png?width=90pc)

5. At **Configure stack options** interface. Scroll down and click on **Next**.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.3secondaryregion.png?width=90pc)

6. At **Review network-stack** interface. Scroll down and click on **Submit**.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.4secondaryregion.png?width=90pc)

7. Your network stack is creating.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.5secondaryregion.png?width=89pc)

8. After a minute, your stack will be created successfully.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.6secondaryregion.png?width=89pc)

### Deploy Application
1. Go to [CloudFormation Stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2) in secondary region **Oregon  (us-west-2)**.
2. At CloudFormation interface, click on **Create Stack**.
3. Then click on **With new resources (standard)**.

![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.7secondaryregion.png?width=89pc)

4. At **Create stack** interface, choose **Template is ready** as **Prepare template**.
5. Select **Upload a template file** as **Specify template**.
6. Click on **Choose file** and select **WarmStandby_App.yml** file you had downloaded above.
7. Then, click on **Next**.

![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.8secondaryregion.png?width=89pc)

8. At **Specify stack details** interface, input stack name ```warm-secondary```.
9. Change to **no** at **IsPrimary** parameter.
10. Keep **no** at **IsPromote** parameter.
11. Keep **/aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2** at **LatestAmiId** parameter.
12. Keep **network-stack** at **NetworkStackName** parameter unless you've changed it in the previous step.
13. Then, click on **Next**.

![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.9secondaryregion.png?width=89pc)

14. At **Configure stack options** interface, scroll down and click on **Next**.

![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.10secondaryregion.png?width=89pc)

15. At **Review warm-secondary** interface, scroll down to the end of page.
16. Check at box **I acknowledge that AWS CloudFormation might create IAM resources with custom names.**
17. Then, click on **Submit**.
![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.11secondaryregion.png?width=89pc)

18. Your application stack is creating. It will take you about 15 minutes to finish.

![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.12secondaryregion.png?width=90pc)

19. After about 15 minutes, your stack had been created successfully.

![Secondary Region](/images/2.preparation/2.3.secondaryregion/2.3.13secondaryregion.png?width=90pc)