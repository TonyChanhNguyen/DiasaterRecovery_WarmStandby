---
title : "Verify failover"
date : "`r Sys.Date()`"
weight : 3
chapter : false
pre : " <b> 3.3 </b> "
---

1. Go to [CloudFormation Stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/stackinfo?filteringText=&filteringStatus=active&viewNested=true) in the **Oregon (us-west-2)** region.
2. Click on stack name **warm-secondary**.
3. Click on **Outputs** tab.
4. Click on **WebsiteURL** link.
![Verify Failover](/images/3.failover/3.3.verifyfailover/3.3.1verifyfailover.png?width=90pc)

5. It will be logged in automatically. After that, click on Cart shop to see the quantity if your Cart now is 0.
![Verify Failover](/images/3.failover/3.3.verifyfailover/3.3.2verifyfailover.png?width=90pc)

6. All of items that you added before will appear. 
![Verify Failover](/images/3.failover/3.3.verifyfailover/3.3.3verifyfailover.png?width=90pc)

7. After closing Cart page, you will see the quantity of Cart shop now is same as before.
![Verify Failover](/images/3.failover/3.3.verifyfailover/3.3.4verifyfailover.png?width=90pc)


#### Congratulations, your website had been done failover to Secondary Region **Oregon (us-west-2)** from Primary Region **N. Virginia (us-east-1)** successfully.