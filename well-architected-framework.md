# Well Architected Framework

The purpose of this document is to be a lightweight version of the more comprehensive [AWS_Well-Architected_Framework.pdf][1]. It also pick and choose the most relevant questions provided by AWS to facilitate a Well Architected review in no more than 4 hours. Italic quotes are taken directly (or highly inspired by parts) from the AWS Well Architected Framework document.

*The AWS Well-Architected Framework helps you understand the pros and cons of decisions you make while building systems on AWS. The process for reviewing an architecture is a constructive conversation about architectural decisions, and is not an audit mechanism.*


## Introduction
*At AWS, we prefer to distribute capabilities into teams rather than having a centralized team with that capability. There are risks when you choose to distribute decision making authority, for example, ensure that teams are meeting internal standards. We mitigate these risks in two ways. First, we have **practices** that focus on enabling each team to have that capability, and we put in place experts who ensure that teams raise
the bar on the standards they need to meet. Second, we implement **mechanisms** that carry out automated checks to ensure standards are being met.*


## Questions for further discussions

### Operational Excellence
*The ability to make frequent, small, reversible changes and define the infrastructure as code. Anticipate that failures will happen and continuously try to improve operations procedures. Learn and share from failures and work proactively to test possible failure scenarios.*

- How do you determine what your priorities are?
    - What are the sources that form your backlog?

- Can you describe your team and it's responsibility within cloud for your company?
    - Does your company have a defined shared responsibility model?

- How do you get help from the cloud vendor and from within your company?
    - Do you have any concerns with utilizing the AWS Support?
    - Do you see you company Cloud Center of Excellence as an enabler that help you in your cloud journey?

- What is your process for application and infrastructure provisioning?
    - Do you define Infrastructure as Code
    - How is your cloud resources and application code deployed to your environments?
    - Do you have any kind of write access to production environments for you personal (federated) users?
        
- How often do you make changes to your production environment(s)?
    - What is you *batch size* for changes in production?

- Do you keep track of your workloads by some kind of monitoring?
    - Logs? 
    - Metrics?
        - AWS Managed metrics and custom metrics
    - Alerts?

- How do you react when issues are introduced to production?
    - Rollback/forward procedures?
        - Automated
        - Manual with runbooks
    - Do you strive to minimize the impact of a failed deployment or an introduced bug?



### Security
*The ability to protect data, systems and assets from unauthorized access.*

- Do you have a Security Lead in your team?
    - Who are responsible for security in your team?

- What is the classification (sensitivity) of the data you operate?

- How do you separate development/test environments from production environment?

- What security mechanisms do you use to only allow authenticated and authorized users to access your AWS accounts?
    - Password rotation and complexity, enforce MFA?
    - Do you utilize any Long Term access keys?
        - How frequently are they rotated and where are they stored?

- Do you have any thoughts on Least Privileges (limit to only needed access) to resources

- Do you use detective controls to identify a potential security threat or incident?
    - GuardDuty (threat detection service)?
    - Analyze CloudTrail or CloudWatch logs for strange behaviors?

- Do you use any tool(s) for automated security scanning?

- Do you store access logs for sensitive parts in your architecture?
    - ELB, CloudFront, S3 access logs, CloudTrail?

- How do you protect your compute resources?
    - private subnet, security groups, NACLs, WAF?

- How do you protect data at rest?

- How do you protect data in transit?

- What would you do if you suddenly got an anomaly detection of increased cost for one of your accounts, and when logging into the account you see 50 and an increasing amount of EC2 instances being created?


### Reliability
*The ability to run workloads and make them perform their intended function correctly and consistently when it is expected to.*

- Have you ever reached a soft or hard service limit in AWS?

- Are you responsible for the network topology and Domain Name Resolution for your workloads?
    - Describe the process for how to create a new network (VPC).
    - Describe the process for DNS delegation.

- How does your components communicate between each other?
    - How do you deal with the event of high network latency that is out of your control?

- How do you monitor workload resources? 
    - Metrics, Logs?
- How do you design your workload to adapt to changes in demand?
    - Increase resources manually or automatic based on metrics?

- Do you have a consistent process to implement change?
    - Automation on all levels and Infrastructure as Code?

- Do you have defined RTO (Recovery Time Objectives) and RPO (Recovery Point Objective)?

- How is you workload designed to support your RTO and RPO when a component (e.g. a server) fail?
    - Utilizing multiple AZ, using Auto-scaling?

- Do you have a plan for Disaster Recovery?
    - What services are you using to persist data?
        - S3, RDS, etc.
    - Do you have backups of all data?
    - Have you verified and have a defined process to restore these backups?
    - Describe the process how your workload would be restored in another AWS region.




### Performance Efficiency
*The Performance Efficiency pillar includes the ability to use computing resources efficiently and to maintain that efficiency as demand changes and technologies evolve.*

- Can you describe the usage pattern of your workload?
    - Different during the day/week etc.?

- How do you select your compute solution?
    - Instances, Containers, Functions?

- How do you select your storage solution?
    - S3 (object), EFS (file), EBS (block)

- How do you select your database solution?
    - Managed service or maintain your own?
    - RDS (relational), DynamoDB (nosql), ElastiCache (memory)

- How do you configure your networking solution?
    - Network topology?
    - Placement groups
    - Edge services

- Do you keep updated with new AWS releases that might enable you to improve your architecture and performance efficiency?
    - How?

- How do you monitor your resources to ensure they are performing?
    - Metrics and dashboards? Alarms?
    - Using CloudWatch, X-Ray?

- Do you have "game days" where you simulate production problems?

- Do you do tradeoffs between **consistency and durability** for **time and latency**.
    - Do you generally do tradeoffs in efficiency versus cost? 


### Cost Optimization



[1]: https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf
