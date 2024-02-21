---
title : "Aurora"
date : "`r Sys.Date()`"
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

[Amazon Aurora Global Database](https://aws.amazon.com/vi/rds/aurora/global-database/) is designed for globally distributed applications, allowing a single Amazon Aurora database to span multiple AWS regions. It replicates your data with no impact on database performance, enables fast local reads with low latency in each region, and provides disaster recovery from region-wide outages. In disaster recovery situations, you can promote a secondary region to take full read-write responsibilities in under a minute.

With an Aurora global database, there are two different approaches to failover depending on the scenario.

**Failover** – Use this approach to recover from an unplanned outage. With this approach, you perform a cross-Region failover to one of the secondary DB clusters in your Aurora global database. The RPO for this approach is typically a non-zero value measured in seconds. The amount of data loss depends on the Aurora global database replication lag across the AWS Regions at the time of the failure.

**Switchover** – This operation was previously called "managed planned failover". Use this approach for controlled scenarios, such as operational maintenance and other planned operational procedures. Because this feature synchronizes secondary DB clusters with the primary before making any other changes, RPO is 0 (no data loss).

**Failover**, is showcased in **Pilot Light** workshop.

For this workshop we will be doing a **Switchover**.

1. Go to [RDS](https://us-west-2.console.aws.amazon.com/rds/home?region=us-west-2#databases:) in **Oregon (us-west-2)** region.
2. Look at the **warm-global** Global database. Notice how you have **warm-primary** a Primary cluster in **us-east-1** which has your **Writer instance** and **warm-secondary** a Secondary cluster in **us-west-1** which has your **Reader instance**.
![Failover Aurora](/images/3.failover/3.1.aurora/3.1.1aurora.png?width=90pc)


3. Select **warm-global** cluster.
4. Click on **Actions**.
5. Choose **Switch over or fail over global database** under **Actions**.
![Failover Aurora](/images/3.failover/3.1.aurora/3.1.2aurora.png?width=90pc)

6. Choose **Switchover**.
7. At **New primary cluster** feature, select **warm-secondary**.
8. Then, click on **Confirm**.
![Failover Aurora](/images/3.failover/3.1.aurora/3.1.3aurora.png?width=90pc)

9. It will take you several minutes to promote Secondary database to Primary.
![Failover Aurora](/images/3.failover/3.1.aurora/3.1.4aurora.png?width=90pc)

11. When the switchover is complete, notice the changes. The **Primary cluster** is now in **us-west-2** which has our **Writer instance** and the **Secondary Cluster** is now in **us-east-1** which has our **Reader instance**. 
![Failover Aurora](/images/3.failover/3.1.aurora/3.1.5aurora.png?width=90pc)