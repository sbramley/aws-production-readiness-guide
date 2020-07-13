# Production Readiness Guide: AWS

# Architecture Design Review

It&#39;s important to start with a strong understanding of the original design specifications and expected architecture. This provides a baseline to compare deviation and to reconcile gaps.

If these design resources don&#39;t currently exist, the following guide can help facilitate the design of the documentation.

- Clear description of the core design principals. Often this is defined by the company&#39;s already established expectations, processes and best practices.
- Clear description of application-specific requirements. Frameworks, service dependencies, database needs and other functional components required by the application.
- Flow charts or diagrams depicting the expected architectural components. This would include hosting resources, networking configuration, IAM policy permissions and other logical pathways between resources and external services.
- Infrastructure as Code can help augment the above documentation by validating the resources that have been provisioned.
- Security review and expectations. The security review will provide guidance on how the networking, access and IAM policies should be structured and enforced.
- Application and Infrastructure deployment strategy. List of tools and description of deployment process.

## Notes:

Which design documents are missing?
\
\
\
\
What deviation is currently known from original design?
\
\
\
\
Is there a clear deployment method?
\
\
\
\
Does the product appear to follow a company best-practice (design, networking, naming, security)?
\
\
\
\
&nbsp;
### Reserved for Links and/or Attachments to Design Documentation
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
\
&nbsp;

# Operational Checklists

## Basic Operations Checklist


- Use AWS Identity and Access Management (IAM) to provide user-specific, rather than shared credentials for making AWS infrastructure requests.
\
\
\
&nbsp;
- We understand which of our instances is Amazon Elastic Block Store (Amazon EBS)- backed versus instance store-backed, have intentionally chosen the most appropriate type of storage, and understand the implications to data persistence, backup and recovery.
\
\
\
&nbsp;
- We understand AWS dynamic IP addressing and have ensured that our application will function when application components are restarted (e.g., using 3rd -party or Elastic Load Balancing, Amazon Virtual Private Cloud (Amazon VPC) static address assignments, elastic IP addresses, or dynamic DNS).
\
\
\
&nbsp;
- We use separate Amazon EBS volumes for the operating system and application/database data where appropriate
\
\
\
&nbsp;
- We regularly back up our Amazon Elastic Compute Cloud (Amazon EC2) instances using Amazon EBS snapshots or another 3rd -party backup tool.
\
\
\
&nbsp;
- We regularly test our process of recovering our Amazon EC2 instances or Amazon EBS volumes when they fail, either through customized8 &quot;golden&quot; Amazon Machine Images (AMIs), Amazon EBS snapshots, bootstrapping, or using our own backup and recovery tools.
\
\
\
&nbsp;
- We have deployed critical components of our applications across multiple availability zones, are appropriately replicating data between zones, and have tested how failure within these components affects application availability.
\
\
\
&nbsp;
- We understand how failover will occur across application components deployed in multiple availability zones and are using 3rd -party or Elastic Load Balancing and elastic IP addresses where appropriate
\
\
\
&nbsp;
- We regularly test our process for patching, updating, and securing our Amazon EC2 operating system, applications, and customized AMIs.
\
\
\
&nbsp;
- We use appropriate operating system user account access credentials and are not sharing the AWS instance key pair private key with all systems administrators.
\
\
\
&nbsp;
- We have implemented secure Security Group rules and nested Security Groups to create a hierarchical network topology where appropriate.
\
\
\
&nbsp;
- We use &quot;CNAME&quot; records to map our DNS name to our Elastic Load Balancing or Amazon S3 buckets and NOT &quot;A&quot; records.
\
\
\
&nbsp;
- Before sharing our customized Amazon Machine Images with others, we removed all confidential or sensitive information including embedded public/private instance key pairs and reviewed all SSH &#39;authorized\_keys&#39; files.
\
\
\
&nbsp;
# Production Readiness Guide: AWS

# Architecture Design Review

It&#39;s important to start with a strong understanding of the original design specifications and expected architecture. This provides a baseline to compare deviation and to reconcile gaps.

If these design resources don&#39;t currently exist, the following guide can help facilitate the design of the documentation.

- Clear description of the core design principals. Often this is defined by the company&#39;s already established expectations, processes and best practices.
- Clear description of application-specific requirements. Frameworks, service dependencies, database needs and other functional components required by the application.
- Flow charts or diagrams depicting the expected architectural components. This would include hosting resources, networking configuration, IAM policy permissions and other logical pathways between resources and external services.
- Infrastructure as Code can help augment the above documentation by validating the resources that have been provisioned.
- Security review and expectations. The security review will provide guidance on how the networking, access and IAM policies should be structured and enforced.
- Application and Infrastructure deployment strategy. List of tools and description of deployment process.

## Notes:

Which design documents are missing?
\
\
\
\
What deviation is currently known from original design?
\
\
\
\
Is there a clear deployment method?
\
\
\
\
Does the product appear to follow a company best-practice (design, networking, naming, security)?
\
\
\
\
&nbsp;
### Page Reserved for Links and/or Attachments to Design Documentation


# Operational Checklists

## Basic Operations Checklist


- Use AWS Identity and Access Management (IAM) to provide user-specific, rather than shared credentials for making AWS infrastructure requests.
\
\
\
&nbsp;
- We understand which of our instances is Amazon Elastic Block Store (Amazon EBS)- backed versus instance store-backed, have intentionally chosen the most appropriate type of storage, and understand the implications to data persistence, backup and recovery.
\
\
\
&nbsp;
- We understand AWS dynamic IP addressing and have ensured that our application will function when application components are restarted (e.g., using 3rd -party or Elastic Load Balancing, Amazon Virtual Private Cloud (Amazon VPC) static address assignments, elastic IP addresses, or dynamic DNS).
\
\
\
&nbsp;
- We use separate Amazon EBS volumes for the operating system and application/database data where appropriate
\
\
\
&nbsp;
- We regularly back up our Amazon Elastic Compute Cloud (Amazon EC2) instances using Amazon EBS snapshots or another 3rd -party backup tool.
\
\
\
&nbsp;
- We regularly test our process of recovering our Amazon EC2 instances or Amazon EBS volumes when they fail, either through customized8 &quot;golden&quot; Amazon Machine Images (AMIs), Amazon EBS snapshots, bootstrapping, or using our own backup and recovery tools.
\
\
\
&nbsp;
- We have deployed critical components of our applications across multiple availability zones, are appropriately replicating data between zones, and have tested how failure within these components affects application availability.
\
\
\
&nbsp;
- We understand how failover will occur across application components deployed in multiple availability zones and are using 3rd -party or Elastic Load Balancing and elastic IP addresses where appropriate
\
\
\
&nbsp;
- We regularly test our process for patching, updating, and securing our Amazon EC2 operating system, applications, and customized AMIs.
\
\
\
&nbsp;
- We use appropriate operating system user account access credentials and are not sharing the AWS instance key pair private key with all systems administrators.
\
\
\
&nbsp;
- We have implemented secure Security Group rules and nested Security Groups to create a hierarchical network topology where appropriate.
\
\
\
&nbsp;
- We use &quot;CNAME&quot; records to map our DNS name to our Elastic Load Balancing or Amazon S3 buckets and NOT &quot;A&quot; records.
\
\
\
&nbsp;
- Before sharing our customized Amazon Machine Images with others, we removed all confidential or sensitive information including embedded public/private instance key pairs and reviewed all SSH &#39;authorized\_keys&#39; files.
\
\
\
- We have fully tested our AWS-hosted application, including performance testing, prior to going live.
\
\
\
&nbsp;
- We have signed our production AWS accounts up for business or enterprise support and have a plan for incorporating AWS Trusted Advisor18 reports into our ongoing operational reviews.
\
\
\
&nbsp;
## Enterprise Operations Checklist

- Has your organization developed a strategy for managing AWS API, console, operating system, network, and data access?
\
\
\
&nbsp;
- Does your organization have a strategy for identifying and tracking AWS provisioned resources?
\
\
\
&nbsp;
- Does the implemented AWS solution meet or exceed the application&#39;s high availability and resilience requirements?
\
\
\
&nbsp;
- Does the implemented AWS solution meet or exceed the application&#39;s disaster recovery (DR) and backup requirements?
\
\
\
&nbsp;
- Has your organization instrumented appropriate monitoring tools and integrated your AWS resources into its incident management processes?
\
\
\
&nbsp;
- Does your organization have a configuration and change management strategy for its AWS resources?
\
\
\
&nbsp;
- Has your organization determined how it will integrate application releases and deployments with its configuration and change management strategy?
\
\
\
&nbsp;
# Security Review

## AWS Credentials Strategy

- How will your administrators, systems and/or applications authenticate their AWS infrastructure requests to AWS API?
\
\
\
&nbsp;
- Has your organization established internal credential management policies and procedures for creating, distributing, rotating and revoking AWS access credentials?
\
\
\
&nbsp;
- How will your organization manage application AWS credentials?
\
\
\
&nbsp;
- Does your organization leverage Identity Federation using an identity provider such as Active Directory, Okta, SAML provider or other application?
\
\
\
&nbsp;
## Networking

- Does your organization create VPCs, Subnets, Route Tables and Internet Gateways based on the AWS Well Architected framework?
\
\
\
&nbsp;
- Is your organization hosting resources inside of Public Subnets and/or assigning services Elastic IP addresses directly?
\
\
\
&nbsp;
- Is your organization leveraging transport encryption protocols for external or cross-aws data transversal?
\
\
\
&nbsp;
- Does your organization have an established process for provisioning security groups and security group rules?
\
\
\
&nbsp;
- Does your organization leverage ACL (access control lists) rulesets?
\
\
\
&nbsp;
## Resource Security

- Does your organization have an established policy for S3 bucket permissions?
\
\
\
&nbsp;
- Does your organization follow established access control policies for resources that may be provisioned with public endpoints (RDS, ElasticSearch, Redis, Kabana etc)?
\
\
\
&nbsp;
- Does your organization leverage shared security groups or IAM roles across multiple resources?
\
\
\
&nbsp;
# Asset Management and Tracking

- Is your organization leveraging AWS provided instance and service specific metadata as part of its asset management strategy?
\
\
\
&nbsp;
- Is your organization leveraging customer resource tags to track and identify AWS resources?
\
\
\
&nbsp;
- Does your organization have a resource tagging strategy?
\
\
\
&nbsp;
# Application Resilience

- Has your organization provisioned hosting resources across multiple Availability Zones?
\
\
\
&nbsp;
- Does your organization leverage Elastic Load Balancing for load balancing across multiple Availability Zones?
\
\
\
&nbsp;
- Does your organization leverage Auto Scaling and Auto Scaling rules for automated instance recovery and scaling?
\
\
\
&nbsp;
- Does your organization leverage CloudWatch for metrics monitoring and alarms?
\
\
\
&nbsp;
- Does your organization create point-in-time snapshots of EBS volumes (non-ephemeral data)?
\
\
\
&nbsp;
- Does your organization use CloudFront when hosting static assets inside of S3?
\
\
\
&nbsp;
- Does your organization leverage data replication technologies like database mirroring and read/write replicas?
\
\
\
&nbsp;
- Does your organization leverage Application Performance Monitoring tools to help optimize the use of AWS resources?
\
\
\
&nbsp;
# Application DR/Backup

## Overview

Each application has specific disaster recovery requirements that should best fit the requirements and availability of the application. An effective DR strategy will fit the specific application use case and thus may look different but, still follow basic design principles. Thus, this section will follow design recommendations and testing best practices as opposed to questionnaire form. At a high level, an effective DR strategy would include regional redundancy, global traffic management or load balancing, monitoring and region – to – region recovery. The following are AWS Services and techniques that your organization can consider as a part of a DR strategy.

- Store data, AMIs, or run additional instances in multiple AWS regions
- Use Route 53 for DNS-based regional fail-over.
- Leverage asynchronous data replication technologies like database log shipping.
- Use EBS snapshots and/or AMI copies, cross region.
- Leverage S3 Bucket versioning.
- Leverage S3 lifecycle policies to archive data for easy recovery.

## AWS DR References

- [Designing Fault-Tolerant Applications in the Cloud](http://d36cz9buwru1tt.cloudfront.net/AWS_Building_Fault_Tolerant_Applications.pdf)
- [Using AWS for Disaster Recovery](http://d36cz9buwru1tt.cloudfront.net/AWS_Disaster_Recovery.pdf)
- [S3 Lifecycle Policies](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-archival.html)
- [S3 Versioning](http://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html)
- [EBS Snapshots](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-snapshot.html)

# Monitoring, Alerting and Logging

## Monitoring

- Is your organization currently employing a consistent monitoring solution across all critical components and applications?
\
\
\
&nbsp;
- Do the monitoring metrics and thresholds match tested bounds of the application and infrastructure?
\
\
\
&nbsp;
- Does your organization implement application performance monitoring tools?
\
\
\
&nbsp;
- Do current monitoring solutions provide feedback to the application and enable self-healing or Auto Scaling?
\
\
\
&nbsp;
## Alerting

- What incident response process and/or system does your organization implement for reacting to issues or outages?
\
\
\
&nbsp;
- Does your organization use an incident tracking platform, process or system to track and store issues?
\
\
\
&nbsp;
- How quickly (on average) does your organization respond to critical incidents?
\
\
\
&nbsp;
- How much, if any automation is used by your organization to react to alerts (auto scaling, automated deployments, automatic failovers etc.)?
\
\
\
&nbsp;
## Logging

- Does your organization use a standardized logging solution, tool or methodology?
\
\
\
&nbsp;
- Does your organization have a best practice on configuring what to log vs. what not to log?
\
\
\
&nbsp;
- What is your organizations practice or policy on log retention?
\
\
\
&nbsp;
- Does your organization use logs to trigger alerts or other automated actions?
\
\
\
&nbsp;
- What would your organization estimate as the total percentage of all logs that are &quot;noise&quot; or otherwise non-beneficial?
\
\
\
&nbsp;
- We have fully tested our AWS-hosted application, including performance testing, prior to going live.
\
\
\
&nbsp;
- We have signed our production AWS accounts up for business or enterprise support and have a plan for incorporating AWS Trusted Advisor18 reports into our ongoing operational reviews.
\
\
\
&nbsp;
## Enterprise Operations Checklist

- Has your organization developed a strategy for managing AWS API, console, operating system, network, and data access?
\
\
\
&nbsp;
- Does your organization have a strategy for identifying and tracking AWS provisioned resources?
\
\
\
&nbsp;
- Does the implemented AWS solution meet or exceed the application&#39;s high availability and resilience requirements?
\
\
\
&nbsp;
- Does the implemented AWS solution meet or exceed the application&#39;s disaster recovery (DR) and backup requirements?
\
\
\
&nbsp;
- Has your organization instrumented appropriate monitoring tools and integrated your AWS resources into its incident management processes?
\
\
\
&nbsp;
- Does your organization have a configuration and change management strategy for its AWS resources?
\
\
\
&nbsp;
- Has your organization determined how it will integrate application releases and deployments with its configuration and change management strategy?
\
\
\
&nbsp;
# Security Review

## AWS Credentials Strategy

- How will your administrators, systems and/or applications authenticate their AWS infrastructure requests to AWS API?
\
\
\
&nbsp;
- Has your organization established internal credential management policies and procedures for creating, distributing, rotating and revoking AWS access credentials?
\
\
\
&nbsp;
- How will your organization manage application AWS credentials?
\
\
\
&nbsp;
- Does your organization leverage Identity Federation using an identity provider such as Active Directory, Okta, SAML provider or other application?
\
\
\
&nbsp;
## Networking

- Does your organization create VPCs, Subnets, Route Tables and Internet Gateways based on the AWS Well Architected framework?
\
\
\
&nbsp;
- Is your organization hosting resources inside of Public Subnets and/or assigning services Elastic IP addresses directly?
\
\
\
&nbsp;
- Is your organization leveraging transport encryption protocols for external or cross-aws data transversal?
\
\
\
&nbsp;
- Does your organization have an established process for provisioning security groups and security group rules?
\
\
\
&nbsp;
- Does your organization leverage ACL (access control lists) rulesets?
\
\
\
&nbsp;
## Resource Security

- Does your organization have an established policy for S3 bucket permissions?
\
\
\
&nbsp;
- Does your organization follow established access control policies for resources that may be provisioned with public endpoints (RDS, ElasticSearch, Redis, Kabana etc)?
\
\
\
&nbsp;
- Does your organization leverage shared security groups or IAM roles across multiple resources?
\
\
\
&nbsp;
# Asset Management and Tracking

- Is your organization leveraging AWS provided instance and service specific metadata as part of its asset management strategy?
\
\
\
&nbsp;
- Is your organization leveraging customer resource tags to track and identify AWS resources?
\
\
\
&nbsp;
- Does your organization have a resource tagging strategy?
\
\
\
&nbsp;
# Application Resilience

- Has your organization provisioned hosting resources across multiple Availability Zones?
\
\
\
&nbsp;
- Does your organization leverage Elastic Load Balancing for load balancing across multiple Availability Zones?
\
\
\
&nbsp;
- Does your organization leverage Auto Scaling and Auto Scaling rules for automated instance recovery and scaling?
\
\
\
&nbsp;
- Does your organization leverage CloudWatch for metrics monitoring and alarms?
\
\
\
&nbsp;
- Does your organization create point-in-time snapshots of EBS volumes (non-ephemeral data)?
\
\
\
&nbsp;
- Does your organization use CloudFront when hosting static assets inside of S3?
\
\
\
&nbsp;
- Does your organization leverage data replication technologies like database mirroring and read/write replicas?
\
\
\
&nbsp;
- Does your organization leverage Application Performance Monitoring tools to help optimize the use of AWS resources?
\
\
\
&nbsp;
# Application DR/Backup

## Overview

Each application has specific disaster recovery requirements that should best fit the requirements and availability of the application. An effective DR strategy will fit the specific application use case and thus may look different but, still follow basic design principles. Thus, this section will follow design recommendations and testing best practices as opposed to questionnaire form. At a high level, an effective DR strategy would include regional redundancy, global traffic management or load balancing, monitoring and region – to – region recovery. The following are AWS Services and techniques that your organization can consider as a part of a DR strategy.

- Store data, AMIs, or run additional instances in multiple AWS regions
- Use Route 53 for DNS-based regional fail-over.
- Leverage asynchronous data replication technologies like database log shipping.
- Use EBS snapshots and/or AMI copies, cross region.
- Leverage S3 Bucket versioning.
- Leverage S3 lifecycle policies to archive data for easy recovery.

## AWS DR References

- [Designing Fault-Tolerant Applications in the Cloud](http://d36cz9buwru1tt.cloudfront.net/AWS_Building_Fault_Tolerant_Applications.pdf)
- [Using AWS for Disaster Recovery](http://d36cz9buwru1tt.cloudfront.net/AWS_Disaster_Recovery.pdf)
- [S3 Lifecycle Policies](http://docs.aws.amazon.com/AmazonS3/latest/dev/object-archival.html)
- [S3 Versioning](http://docs.aws.amazon.com/AmazonS3/latest/dev/Versioning.html)
- [EBS Snapshots](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-creating-snapshot.html)

# Monitoring, Alerting and Logging

## Monitoring

- Is your organization currently employing a consistent monitoring solution across all critical components and applications?
\
\
\
&nbsp;
- Do the monitoring metrics and thresholds match tested bounds of the application and infrastructure?
\
\
\
&nbsp;
- Does your organization implement application performance monitoring tools?
\
\
\
&nbsp;
- Do current monitoring solutions provide feedback to the application and enable self-healing or Auto Scaling?
\
\
\
&nbsp;
## Alerting

- What incident response process and/or system does your organization implement for reacting to issues or outages?
\
\
\
&nbsp;
- Does your organization use an incident tracking platform, process or system to track and store issues?
\
\
\
&nbsp;
- How quickly (on average) does your organization respond to critical incidents?
\
\
\
&nbsp;
- How much, if any automation is used by your organization to react to alerts (auto scaling, automated deployments, automatic failovers etc.)?
\
\
\
&nbsp;
## Logging

- Does your organization use a standardized logging solution, tool or methodology?
\
\
\
&nbsp;
- Does your organization have a best practice on configuring what to log vs. what not to log?
\
\
\
&nbsp;
- What is your organizations practice or policy on log retention?
\
\
\
&nbsp;
- Does your organization use logs to trigger alerts or other automated actions?
\
\
\
&nbsp;
- What would your organization estimate as the total percentage of all logs that are &quot;noise&quot; or otherwise non-beneficial?
\
\
\
&nbsp;
