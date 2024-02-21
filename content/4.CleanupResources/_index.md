---
title : "Cleanup resources"
date : "`r Sys.Date()`"
weight : 4
chapter : false
pre : " <b> 4. </b> "
---

### S3 Cleanup
1. Go to [S3](https://s3.console.aws.amazon.com/s3/home).
2. Select the **warm-primary-uibucket-xxxx**.
3. Click **Empty**.
![Cleanup Resources](/images/4.cleanup/4.1cleanup.png?width=90pc)

4. Input ```permanently delete```.
5. Then, click on **Empty**.
![Cleanup Resources](/images/4.cleanup/4.2cleanup.png?width=90pc)

6. Repeat those step for bucket name **warm-secondary-uibucket-xxxx** also.


### Database Cleanup
#### Primary region
1. Go to [RDS](https://us-west-1.console.aws.amazon.com/rds/home?region=us-east-1#databases:) in **N. Virginia (us-east-1)** region.
2. Select **unishop-warm** database under **warm-primary** cluster.
3. Click on **Action**.
4. Then click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.3cleanup.png?width=90pc)
5. Enter ```delete me```.
6. Click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.4cleanup.png?width=90pc)

7. After **unishop-warm** database was deleted, select **warm-primary** cluster.
8. Click on **Actions**.
9. Click on **Remove from global database**.
![Cleanup Resources](/images/4.cleanup/4.5cleanup.png?width=90pc)

10. Click **Remove and promote**.
![Cleanup Resources](/images/4.cleanup/4.6cleanup.png?width=90pc)

11. After remove from global database, select **warm-primary** cluster.
12. Click on **Actions**.
13. Click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.7cleanup.png?width=90pc)


14. Uncheck **Create final snapshot** box.
15. Check **I acknowledge that upon instance...** box.
16. Input ```delete me```.
17. Then, click on **Delete DB sluster**.
![Cleanup Resources](/images/4.cleanup/4.8cleanup.png?width=90pc)

#### Secondary region
1. Go to [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:) in **Oregon (us-west-2)** region.
2. Repeat all above steps to delete **unishop-warm** database first, then delete **warm-secondary** cluster.

After databases and clusters were deleted, now we will delete **Global database**.

3. Select **warm-global**.
4. Click on **Actions**.
5. Click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.9cleanup.png?width=90pc)

6. Input ```delete me```.
7. Click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.10cleanup.png?width=90pc)


### CloudFormation Secondary Region Cleanup
1. Go to [CloudFormation stacks](https://us-west-2.console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/outputs?filteringText=&filteringStatus=active&viewNested=true) in the **Oregon (us-west-2)** region.
2. Select stack name **warm-secondary**.
3. Then click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.11cleanup.png?width=90pc)

4. Click on **Delete** to confirm. 
![Cleanup Resources](/images/4.cleanup/4.12cleanup.png?width=90pc)

5. After stack **warm-secondary** was deleted, select stack name **network-stack**.
6. Then click on **Delete**.
![Cleanup Resources](/images/4.cleanup/4.13cleanup.png?width=90pc)

7. Click on **Delete** to confirm.
![Cleanup Resources](/images/4.cleanup/4.14cleanup.png?width=90pc)

### CloudFormation Primary Region Cleanup
1. Go to [CloudFormation stacks](https://us-east-1.console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks?filteringText=&filteringStatus=active&viewNested=true) in the **N. Virginia (us-east-1)** region.

2. Repeat these steps to delete stack name **warm-primary** first, then delete stack name **network-stack**.

### S3 bucket Cleanup
1. Go to [S3](https://s3.console.aws.amazon.com/s3/home).
2. Select bucket name **cf-templates-xxxxxxxxxxxxx-us-east-1**.
3. Click on **Empty**.
![Cleanup Resources](/images/4.cleanup/4.15cleanup.png?width=90pc)

4. Input ```permanently delete```.
5. Then, click on **Empty**.
![Cleanup Resources](/images/4.cleanup/4.16cleanup.png?width=90pc)

6. Select bucket name **cf-templates-xxxxxxxxxxxxx-us-east-1** again.
7. Click on **Delete**.

![Cleanup Resources](/images/4.cleanup/4.17cleanup.png?width=90pc)

8. Input its bucket name.
9. Click on **Delete bucket**.
![Cleanup Resources](/images/4.cleanup/4.18cleanup.png?width=90pc)

10. Repeat those steps with bucket name **cf-templates-xxxxxxxxxxxxx-us-west-2**.


#### Congratulations, you had finished this workshop! 