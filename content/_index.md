---
title : "Warm Standby"
date :  "`r Sys.Date()`" 
weight : 1 
chapter : false
---
# Warm Standby
In this module, you will go through the Warm Standby disaster recovery strategy. Warm Standby disaster recovery strategy has **Recovery Point Objective(RPO) / Recovery Time Objective (RTO)**  within minutes. For the warm Standby strategy secondary region, the data is live and core infrastructure is provisioned and the services are running at a reduced capacity.

Your application is currently deployed in the primary region N. Virginia (us-east-1). Oregon (us-west-2) will be your secondary.

Your test application is **Unishop**. It is a Spring Boot Java application deployed on a single Amazon Elastic Compute Cloud (EC2)  instance using a public subnet. Your datastore is an Amazon Aurora MySQL database with a frontend written using bootstrap and hosted in Amazon Simple Storage Service (S3).

This module takes advantage of Auto Scaling Groups (ASG) which will allow us to scale out in the secondary region compute instances during failover. Amazon Aurora Global Database  is used to replicate your Amazon Aurora MySQL data to the secondary region. You are also taking advantage of Amazon Aurora read replica write forwarding. With this feature enabled, writes can be sent to a read replica in a secondary region, and will be seamlessly forwarded to the writer in the primary region over a secure communication channel.

CloudFormation will be used to configure the infrastructure and deploy the application. Provisioning your infrastructure with infrastructure as code (IaC) methodologies is a best practice. CloudFormation is an easy way to speed up cloud provisioning with infrastructure as code.

![Warm Standby](/images/warmstandby.png?width=60pc)