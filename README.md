# Cloud Adoption Framework

A collection of learnings and especially questions for discussion when companies are about to adopt public Cloud.

The big public Cloud providers have their own version of Cloud Adoption Framework (CAF) publicly described:

 - [Cloud Adoption Framework - AWS][1]
   - Six perspectives
     - Business, People, Governance, Platform, Security, Operations
 - [Cloud Adoption Framework - Azure][2]
 - [Cloud Adoption Framework - Google][3] - [Whitepaper from Google][6]
   - Four capabilities
     - Learn, Lead, Scale & Secure

This documentation aim to summarize a lightweight version of these. Based on real world implementations.

## Questions for discussions

### What are your motivations for moving to cloud?

### Do you have a Cloud First strategy?

### How much do you strive for autonomous teams vs centralized operations?

### CCoE - Mission

 - Cloud Foundation
 - IAM
 - Integration
 - DevTools
   - VCS
   - Artifactory
   - CI/CD
   - Vault
   - ...
  
### CCoE - Enablements

||AWS tooling|Third party tooling example|
|-------------|-------------|-------------|
|IAM - Federated access to cloud|AWS SSO|-|
|IAM - Restrictions|Service Control Policies|-|
|Email|AWS SES|-|
|Certificate validations|AWS ACM|-|
|Cloud API trail|AWS CloudTrail|-|
|Cost management - Cost distribution within the company|-|-|
|Cost management - Cost trend|AWS Trusted Advisor, Cost Explorer|Cloudability|
|Cost management - Anomaly detection|AWS Cost Anomaly Detection|Cloudability|
|Security compliance & notifications|AWS Trusted Advisor / Config|Cloudguard|
|Automatic DNS delegation for .cloud.corporate.com|AWS Route53|-|
|Disaster Recovery|AWS S3|-|
|Patch management|AWS Systems Manager|-|
|Limit Exposure & enable OWASP protection|AWS Firwall Manager & WAFv2|-|
|Threat detection|AWS GuardDuty|-|
|Network log|AWS VPC Flowlogs|-|
|Corporate inventory of Cloud usage|AWS Config|-|
|On-Prem connectivity|AWS VPN & Direct Connect|-|
|Cloud provider maintenance and other notifications|AWS Health|-|
|Well Architected Workshops/Reviews|-|-|


### Enforce these practices from the start?

 - ReadOnly for humans in Production
 - Centralized management of email
 - Patch management
 - Chaos monkey in prod accounts
 - ...
 

*...more to come :)*


[1]: https://aws.amazon.com/professional-services/CAF
[2]: https://docs.microsoft.com/en-gb/azure/cloud-adoption-framework
[3]: https://cloud.google.com/adoption-framework
[6]: https://services.google.com/fh/files/misc/google_cloud_adoption_framework_whitepaper.pdf
