

- [Notes](#notes)
  - [Services overview](#services-overview)
    - [Regions & Availability Zones (AZs)](#regions--availability-zones-azs)
    - [Global services and regional services](#global-services-and-regional-services)
      - [Global services](#global-services)
      - [Regional service examples](#regional-service-examples)
  - [IAM Identity and Access Management](#iam-identity-and-access-management)
    - [Basic facts and best practices](#basic-facts-and-best-practices)
    - [IAM policies](#iam-policies)
    - [IAM password policies](#iam-password-policies)
    - [MFA (Multi-Factor Authentication)](#mfa-multi-factor-authentication)
  - [AWS Access](#aws-access)
    - [IAM roles](#iam-roles)
    - [IAM security](#iam-security)
    - [The shared responsibility model](#the-shared-responsibility-model)
  - [Elastic Computing Cloud (EC2)](#elastic-computing-cloud-ec2)
    - [Components](#components)
    - [EC2 types](#ec2-types)
    - [Security Groups](#security-groups)
      - [Basic facts and best practices](#basic-facts-and-best-practices-1)
      - [Policies](#policies)
    - [EC2 purchasing options](#ec2-purchasing-options)
      - [Purchasing types](#purchasing-types)
      - [Spot instances](#spot-instances)
      - [Placement Groups](#placement-groups)
    - [AMI (Amazon Machine Image)](#ami-amazon-machine-image)
    - [Storage for EC2 instances](#storage-for-ec2-instances)
      - [EBS (Elastic Block Store)](#ebs-elastic-block-store)
        - [EBS Snapshots](#ebs-snapshots)
        - [EBS types](#ebs-types)
          - [Features](#features)
        - [EBS multi-attachment](#ebs-multi-attachment)
        - [EBS encryption](#ebs-encryption)
        - [EBS RAID](#ebs-raid)
      - [EFS (Elastic File System)](#efs-elastic-file-system)
        - [Comparison of EBS and EFS](#comparison-of-ebs-and-efs)
      - [EC2 instance store](#ec2-instance-store)
    - [IP address for EC2 instances](#ip-address-for-ec2-instances)
      - [Private vs public](#private-vs-public)
      - [Elastic Network Interfaces](#elastic-network-interfaces)
    - [EC2 status (hibernation)](#ec2-status-hibernation)
    - [EC2 Nitro](#ec2-nitro)
  - [Load Balancing and Auto-scaling](#load-balancing-and-auto-scaling)
    - [Scalability & high availability (HA) concepts](#scalability--high-availability-ha-concepts)
    - [Load balancers (LB)](#load-balancers-lb)
      - [Facts and knowledge](#facts-and-knowledge)
      - [Health checks](#health-checks)
      - [Elastic load balancer (ELB) categories:](#elastic-load-balancer-elb-categories)
      - [Stickiness](#stickiness)
      - [Cross-Zone Load Balancing](#cross-zone-load-balancing)
      - [Security groups](#security-groups-1)
      - [SSL & Certificates](#ssl--certificates)
        - [Server Name Indication (SNI)](#server-name-indication-sni)
      - [Connection Draining (CLB) or Deregistration Delay (ALB & NLB)](#connection-draining-clb-or-deregistration-delay-alb--nlb)
    - [Auto Scaling Groups (ASG)](#auto-scaling-groups-asg)
      - [ASG Motivation:](#asg-motivation)
      - [ASG attributies](#asg-attributies)
      - [Auto scaling alarms](#auto-scaling-alarms)
      - [Launch configuration & launch template](#launch-configuration--launch-template)
      - [ASG scaling policies](#asg-scaling-policies)
        - [Termination policy](#termination-policy)
        - [ASG lifecycle hooks](#asg-lifecycle-hooks)
  - [Storage](#storage)
    - [RDS (Relational Database Service)](#rds-relational-database-service)
      - [Overview](#overview)
      - [RDS Backups](#rds-backups)
      - [Storage Auto Scaling](#storage-auto-scaling)
      - [RDS read replicas](#rds-read-replicas)
      - [RDS multiple AZ (disaster recovery)](#rds-multiple-az-disaster-recovery)
      - [RDS security](#rds-security)
        - [Encryption](#encryption)
        - [Network & IAM](#network--iam)
      - [Aurora](#aurora)
        - [overview](#overview-1)
        - [HA & Read Scaling](#ha--read-scaling)
        - [Aurora security](#aurora-security)
        - [Aurora serverless](#aurora-serverless)
        - [Aurora Global Database](#aurora-global-database)
        - [Aurora machine learning](#aurora-machine-learning)
    - [S3 (Simple Storage Service)](#s3-simple-storage-service)
      - [Overview](#overview-2)
      - [S3 Storage class](#s3-storage-class)
        - [Glacier & Glacier Deep Archive](#glacier--glacier-deep-archive)
      - [S3 object lock](#s3-object-lock)
      - [S3 moving between storage classes](#s3-moving-between-storage-classes)
      - [S3 analytics](#s3-analytics)
      - [S3 performance](#s3-performance)
        - [S3 performance improvement](#s3-performance-improvement)
        - [S3 byte-range fetches](#s3-byte-range-fetches)
        - [S3 Select & Glacier Select](#s3-select--glacier-select)
      - [S3 event notification](#s3-event-notification)
      - [S3 requester pays](#s3-requester-pays)
      - [S3 versioning](#s3-versioning)
      - [S3 encryption](#s3-encryption)
        - [Encryption at rest](#encryption-at-rest)
        - [Encryption in transit](#encryption-in-transit)
      - [S3 security](#s3-security)
        - [S3 bucket policy](#s3-bucket-policy)
        - [S3 security (others)](#s3-security-others)
        - [S3 replication (cross region & same region)](#s3-replication-cross-region--same-region)
      - [S3 websites](#s3-websites)
      - [S3 consistency model](#s3-consistency-model)
      - [S3 Pre-signed URLs](#s3-pre-signed-urls)
    - [ElasticCache](#elasticcache)
      - [Overview](#overview-3)
      - [Redis vs Memcached](#redis-vs-memcached)
      - [Use cases](#use-cases)
        - [DB Cache](#db-cache)
        - [User session store](#user-session-store)
      - [Cache Security](#cache-security)
      - [ElasticCache Patterns](#elasticcache-patterns)
  - [Analytics](#analytics)
    - [AWS Athena](#aws-athena)
  - [Network](#network)
    - [Route 53](#route-53)
      - [Overview](#overview-4)
      - [Route 53 as a domain registrar](#route-53-as-a-domain-registrar)
      - [Route 53 advanced features](#route-53-advanced-features)
      - [CNAME and Alias](#cname-and-alias)
      - [Routing Policies](#routing-policies)
        - [Simple routing policy](#simple-routing-policy)
        - [Weighted routing policy](#weighted-routing-policy)
        - [Latency routing policy](#latency-routing-policy)
        - [Geo location routing policy](#geo-location-routing-policy)
        - [Geoproximity Routing Policy](#geoproximity-routing-policy)
        - [Multi-value routing policy](#multi-value-routing-policy)
      - [Health Checks](#health-checks-1)
    - [AWS Elastic Beanstalk](#aws-elastic-beanstalk)
      - [Overview](#overview-5)
- [Tables and Quick Reference](#tables-and-quick-reference)
- [Solutions Architecturing](#solutions-architecturing)
  - [Developing on AWS](#developing-on-aws)
    - [EC2 instance metadata](#ec2-instance-metadata)
    - [AWS SDK](#aws-sdk)
      - [SDK credential security](#sdk-credential-security)
      - [Exponential backoff](#exponential-backoff)
  - [Classic Solution Architecture](#classic-solution-architecture)
    - [Whatisthetime.com](#whatisthetimecom)
      - [Step by step incremental improvement](#step-by-step-incremental-improvement)
    - [MyClothes.com](#myclothescom)
      - [Step by step incremental improvement](#step-by-step-incremental-improvement-1)
    - [Mywordpress.com](#mywordpresscom)
      - [Step by step incremental improvement](#step-by-step-incremental-improvement-2)
    - [Instantiating App quickly](#instantiating-app-quickly)

# Notes

For quick references, check the [Tables and Quick References](#tables-and-quick-references).

## Services overview

### Regions & Availability Zones (AZs)

Factors to consider to choose a region:

1. Compliance
2. Proximity
3. Available services
4. Pricing

Each region usually have 3 AZs, but some regions have only 2 AZs. The maximal number of AZs is 6.

### Global services and regional services

#### Global services

1. Identity and Access Management (IAM)
2. Route 53
3. CloudFront
4. WAF (Web Application Firewall)

#### Regional service examples

1. EC2
2. Elastic Beanstalk
3. Lambda

## IAM Identity and Access Management

### Basic facts and best practices

1. Root accounts shouldn't be used or shared.
2. Groups only contain users, **no hireachical groups**.
3. Policies (as JSON documents) can be assigned to users or groups.
4. Assign users to groups and assgin policies to groups.
5. Enforce MFA.
6. No keys in plaintext, use environment variables.
7. An AWS account can have multiple AWS users.

```plaintext
There are two different types of users in AWS. 
You are either the account owner (root user) or 
you are an AWS Identity and Access Management (IAM) user. 
The root user is created when the AWS account is created and 
IAM users are created by the root user or an IAM administrator for the account.
```

### IAM policies

IAM policies contain the following structures:

1. versions
2. policy id
3. statements
   1. sid
   2. effect (allow or deny)
   3. principal (user/account/role)
   4. action (actions like s3:GetObject)
   5. Resources (list of resources)

### IAM password policies

Basic facts and best practices

1. Set password requirements
2. Set password expiration
3. Prevent password re-use

### MFA (Multi-Factor Authentication)

Use MFA to avoid being compromised when password is stolen or hacked.

Either hardware or software.

## AWS Access

You can access AWS in three different ways:

1. AWS management console (password + MFA)
2. AWS CLI (acess key)
3. AWS SDK (access key)

### IAM roles

Certain AWS services can have IAM roles to perform tasks on behalf of the user. 

1. EC2 instance roles
2. Lambda function roles
3. Roles for Cloudformation

### IAM security 

1. IAM Credentials Report (**account level**)
   1. account's users' credentials
2. IAM Access Advisor (**user level**)
   1. permissions granted to services of each users
   2. good for permission revision

### The shared responsibility model

![shared responsibility model](https://d1.awsstatic.com/security-center/Shared_Responsibility_Model_V2.59d1eccec334b366627e9295b304202faf7b899b.jpg)


## Elastic Computing Cloud (EC2)

### Components

Capabilities:

1. virtual machines EC2
2. data storage on virtual drives EBS
3. load balancers ELB
4. Auto-scaling groups ASG

Storage:

1. EBS & EFS are both network-attached
2. EC2 instance store is hardware-attached

Firewall rules: use **security groups**

Bootstrap script: EC2 User Data (**not data** but a script). The script only run **once** when the instance **first** starts. It runs with the **root** user.


### EC2 types

1. General purpose (T)
2. Compute Optimized (C)
3. Memory Optimized (R X Z)
4. Storage Optimized (I D H)

Reference: https://instances.vantage.sh/


### Security Groups

#### Basic facts and best practices

1. lives outside the `EC2` instance. The instance won't be notified that traffic is blocked.
2. `time out` is security rule issue. `connection refused` is application issue.
3. All `inbound` traffic is blocked by default. All `outbound` traffic is allowed by default.
4. Good practice to have a separate security group for SSH.

#### Policies

1. security groups only contain explicit **allow** rules
    1. Access to ports
    2. authorized ip ranges
    3. control of inbound traffic
    4. control of outbound ranges

### EC2 purchasing options

#### Purchasing types

1. On-Demand 
2. Reserved (**Minimum 1 year**)
   1. reserved (long workload)
   2. convertible reserved instances (change instance type)
   3. scheduled reserved instances (within time window you reserved)
3. Spot instance (short workloads, less reliable)
   1. workloads that are resilient to failure
   2. Not suitable for critical jobs or database
4. Dedicated host (entire **physical server**)
   1. compliance requirements
   2. bring your license for server-bound softwares
   3. 3-year period reservation
   4. control instance placement
5. Dedicated instances (no other **customers** will share your hardware)
   1. no control over instance placement


#### Spot instances

1. Spot instances requests cancellation doesn't terminate instances. First cancel then terminate associated instances.

![spot instance life cylce](https://docs.aws.amazon.com/zh_cn/AWSEC2/latest/UserGuide/images/spot_request_states.png)

2. Spot fleets = set of spot instances + (optional) on-demand instances. Try to meet target capacity with price restrictions. **automatically request spot instances with lowest price**.

#### Placement Groups

Control over the EC2 Instance placement strategy

1. Cluster (low-latency group in **same availability zone**)
   1. great network, can **fail at the same time** though
   2. suitable (big data) jobs that requries fast communication and low latency
2. Spread (spread instance across underlying hardware (max **7** instances per group per AZ))
   1. across AZ, reduce failure, different hardwares
   2. suitable for jobs of high avaibility
3. Partition (max **7 partitions** per AZ, each partition can have **100s of EC2 instances**)
   1.  partition information is treated as metadata for EC2 instances
   2.  partitions failure won't affect other partitions
   3.  suitable for tasks like **Hadoop, Kafka, Cassandra**


### AMI (Amazon Machine Image)

1. public AMI
2. own AMI ( from customized, stopped instance)
3. marketplace AMI

### Storage for EC2 instances

#### EBS (Elastic Block Store)

EBS is a network drive. Can only be mounted to **one** instance at a time. Bounded to **one** AZ. EBS can be **provisioned**.

By default, root volume is deleted when terminated. Can be customized.

##### EBS Snapshots

Snapshot backs up EBS volume and can be copied **across AZ or region**.

##### EBS types

1. general purpose SSD (gp2/gp3)
2. high performance ssd (io1/ io2)
3. low cost HDD (st 1)
4. lowest cost hdd (sc 1)

###### Features

1. **gp2: volume size and IPOS are linked**. max IOPS is 16,000. 3IOPS per GB. Means **5,334** GB reaches the max IOPS.
2. gp3: IOPS and throughput are independent.
3. io 1/io2: increase Provisioned IOPS (PIOPS) up to 64,000 for Nitro EC2 instance and 32,000 for others.
4. io2 block express: sub-millisecond latency and max PIOPS 256,000 with IOPS:GiB ratio of 1,000:1.
5. stl: max throughput 500 MiB/s, IOPS **500**.
6. sc1: max throughput 250 MiB/s IOPS **250**.

**Only ssd can be used as boot volumes**.

##### EBS multi-attachment

The **io1** and **io2** types can be attached to multiple instances in the **same** AZ.

##### EBS encryption

1. data at rest is encrypted
2. data in flight between volume and instance is encrypted.
3. snapshots and recreated volumes are encrypted.
4. to encrypt unencrypted EBS volumes, use **encrypted snapshots**.
5. no manual management, minimal impact on latency.


##### EBS RAID

Motivation:

1. increase IOPS to even higher
2. mirror EBS volumes.

Common options:

1. RAID 0 (**increase performance**): combine volumes to increase total disk space and IOPS. **No redudancy**. Subject to risk of loss of data.
2. RAID 1 (**increase fault tolerance**): mirroring a volume to another.


#### EFS (Elastic File System)

1. Network file system for **multiple mounting** at the same time.
2. Across AZs.
3. High available, scalable and expensive.
4. NFSv4.1 protocol.
5. **Not compatible with Windows**.
6. Use security groups to control access.

##### Comparison of EBS and EFS

| Type      | EBS                                                                 | EFS                    |
| --------- | ------------------------------------------------------------------- | ---------------------- |
| Mount     | **One** instance at a time, io support multi-attachement in same AZ | Support 100s instances |
| Migration | take snapshot and restore snapshot in another AZ                    | No need                |
| OS        | Flexible                                                            | Linux Only             |



#### EC2 instance store

1. Better performance than EBS
2. Lose data when **stopped**, not terminated.
3. Only comes with certain EC2 instance types (**I** for example).

### IP address for EC2 instances

#### Private vs public

Public IPs are

1. identifiable on the internet
2. unique across web
3. geo-locatable
4. subject to change for restarted instances
5. All IPv6 are public

Private IPs are 

1. idenfiable in private network
2. unique across private network
3. connect to internet using a NAT + internet gateway
4. Only a specific range of IPs can be used as private IPs

Elastic IP

1. keep the **same public IP** for instance after restart
2. Default maximum **5** elastic IPs per account
3. **Avoid using EIPs**
   1. Usually poor architectural designs
   2. Use random public IPs and DNS
   3. Use load balancer 

#### Elastic Network Interfaces

A logical component in a VPC that represents a virtual network card.

Possible attributes:

1. primary IPv4 or more secondary IPv4
2. one elastic IP per private IPv4
3. One public IPv4
4. One or more security groups
5. A MAC address

### EC2 status (hibernation)

1. **Stop**: data on EBS (Elastic block store) is kept intact
2. **Terminate** : data on EBS is deleted
3. **Hibernate**: data on RAM is preserved. 
   1. Booting is much faster.
   2. Root EBS volume must be encrypted.
   3. **Doesn't** support **T** instance
   4. **Doesn't** support bare metal instances 
   5. Only for on-demand and reserved instances
   6. No hibernated more than **60** days.

### EC2 Nitro

Next generation virtualization for EC2 instances.

Higher speed EBS (64,000 EBS IOPS, currentmax 32,000 for non-Nitro instances)


## Load Balancing and Auto-scaling

### Scalability & high availability (HA) concepts

Scalability means application can handle greater loads by adapting.

1. vertical scalability
2. horizontal scalability

HA means running your application / system in at least 2 data centers (AZs).

### Load balancers (LB)

Load balancers are servers that forward internet traffic to multiple servers (EC2 Instances) downstream.

Advantanges of using a load balancer:

1. Spread load across multiple downstream instances
2. Expose a **single point of access (DNS)** to your application • Seamlessly handle failures of downstream instances
3. Do regular health checks to your instances
4. Provide SSL termination (HTTPS) for your websites
5. **Enforce stickiness with cookies**
6. High availability across zones
7. Separate public traffic from private traffic

#### Facts and knowledge

1. **4xx** errors are client induced errors 
2. **5xx** errors are server errors.
3. Load Balancer Errors **503** means at capacity or no registered target


#### Health checks

Enables LB to know status of instances

#### Elastic load balancer (ELB) categories:

1. Classic LB
   1. TCP (layer 4), HTTP, HTTPS
   2. Fixed hostname: xxx.region.elb.amazonaws.com
2. Application LB
   1. Fixed hostname: xxx.region.elb.amazonaws.com
   2. HTTP/HTTPS, WebSockets (layer 7)
   3. can redirect to containers on the same instance
   4. support port mapping feature
   5. redirect rules
      1. based on path in URL
      2. based on hostname in URL
      3. based on querystring, headers (content)
   6. target groups
      1. EC2 instances
      2. ECS tasks (containers)
      3. Lambda functions
      4. Private IP addresses
   7. application server doesn't see IP of clients, which is stored in **X-Forwarded-For** header.
3. Network LB
   1. forward TCP & UDP traffic to instance
   2. less latency ~ 100ms 
   3. has **one static IP per AZ**. (helpful for whitelisting specific IP)
   4. no free tier
4. Gateway LB (not discussed here)

#### Stickiness

1. The same client is always redirected to the same instance behind an LB
2. Could potentially introduce imbalance of load

#### Cross-Zone Load Balancing

Each load balance instance distributes **evenly across all registered instances in all AZ**

1. ALB (always on, free)
2. NLB (disabled by default, not free)
3. CLB
   1. from console (enabled by default)
   2. from CLI/API (disabled by default)
   3. free

#### Security groups

It is good practice to let application **only** receives traffic from the load balancer.

#### SSL & Certificates

An SSL Certificate allows traffic between your clients and your load balancer to be encrypted in transit (in-flight encryption).

SSL with LB

1. CLB
   1. one SSL certificate only
   2. needs multiple CLB to support multiple hostnames with multiple SSL certificates
2. ALB & NLB
   1. multiple SSL certificates with SNI


##### Server Name Indication (SNI)

SNI solves the problem of loading **multiple SSL certificates onto one web server** (to serve multiple websites)

1. Only works for ALB, NLB and CloudFront.
2. Not for CLB.

#### Connection Draining (CLB) or Deregistration Delay (ALB & NLB)

Time to complete “in-flight requests” while the instance is de-registering or unhealthy.

Allow the in-flight requests to complete. Can be disabled. If the requests are shorter, then set shorter delay time.

### Auto Scaling Groups (ASG)

#### ASG Motivation:

1. Scale out (add EC2 instances) to match an increased load
2. Scale in (remove EC2 instances) to match a decreased load
3. Ensure we have a minimum and a maximum number of machines running
4. Automatically Register new instances to a load balancer

#### ASG attributies

ASG has the following attributes

1. Launch **configuration**:
   1. AMI + instance type
   2. EC2 user data
   3. EBS volumes
   4. **security groups**
   5. SSH key pairs
2. Min/Max/Initial capacity information
3. Network + subnet
4. Scaling policies
5. LB information

Capacity information:

![ASG](https://miro.medium.com/max/487/1*uS9J8btKCQaMOhnUXp62aA.jpeg)

#### Auto scaling alarms

Alarms can be

1. based on cloudwatch alarms and directly managed by EC2,
2. based on customized metrics

Example:

1. average CPU usage
2. number of requests on the ELB per instance
3. average network in
4. average network out

#### Launch configuration & launch template

1. configuration can't be modified, must be recreated every time.
2. launch template are recommended
   1. versioned.
   2. can be reused and inherited.
   3. provisioned using on-demand or spot instances
   4. use T2 unlimited burst feature.

#### ASG scaling policies

1. target tracking scaling: average CPU usage **be** around 40%
2. simple step scaling
3. scheduled action

Scaling cooldowns makes sure that one action finishes before another one is triggered. 

##### Termination policy

Default termination policy balances the number of instances across AZ.

1. Terminate instance in the AZ with the most instances
2. Terminate instance with the oldest launch configuration

##### ASG lifecycle hooks

1. Pending state
2. Terminating state


## Storage

### RDS (Relational Database Service)

Managed DB service for DB use SQL as a query language.

#### Overview

Flavors of RDS

1. Postgres
2. MySQL
3. MariaDB
4. Oracle
5. Microsoft SQL Server
6. Aurora

Advantages:

1. Automated provisioning, OS patching
2. Continuous backups and restore to specific timestamp (Point in Time Restore)
3. Monitoring dashboards
4. **Read replicas** for improved read performance
5. Multi AZ setup for DR (Disaster Recovery)
6. Maintenance windows for upgrades
7. Scaling capability (vertical and horizontal) 
8. Storage backed by EBS (gp2 or io1)

But you **can't SSH** to the RDS instance.

#### RDS Backups

Automatic backups:

1. daily full backup
2. transaction logs backup every 5 minutes
3. 7 day default retention

#### Storage Auto Scaling

Set **Maximum storage threshold**. Storage automatically scales when certain rules are triggered.

Useful for **unpredictable workloads**.

#### RDS read replicas

1. up to 5 read replicas
2. across AZ or region
3. **ASYNC** so reads are eventually consistent
4. applications must update connection string to read from read replicas.

Use cases: replica for reporting analysis.

Cost: in-region is free, cross region needs payment.

#### RDS multiple AZ (disaster recovery)

1. replication is **SYNC**
2. One DNS name (no additional connection strings), automatical failover
3. increase availability
4. Free
5. **Not used for scaling** but for stand-by instance

#### RDS security 

##### Encryption

At rest: 

1. If master is not encrypted, the read replica can't be encrypted.
2. encrypted at launch time
3. Transparent Data Encryption available for **Oracle and SQL server**

In-flight encryption

1. SSL certificates available

un-encrypted RDS database can be encrypted by encrypting the un-encrypted snapshot

##### Network & IAM

Network security:

1. Usually deployed in private subnet
2. Leveraging security groups

Access Management

1. Controls who can manage AWS RDS
2. username/password can loginto database
3. IAM-based authentication can be used to log into **RDS MySQL & Postgres**

#### Aurora

##### overview

1. Proprietary
2. Up to 64TB
3. up to 15 replicas 
4. HA native
5. more expensive
6. support multiple-master

##### HA & Read Scaling

1. Support cross region replication
2. automatic read replica scaling
3. self healing with peer-to-peer replication
4. automated failover for master in less than 30 seconds
5. Up to 15 read replicas to serve reads
6. Support custom endpoints for specific queries

##### Aurora security

Possibility to authenticate using IAM token

##### Aurora serverless

pay per seconds
good for infrequent or unpredictable workloads

##### Aurora Global Database

1. 1 Primary Region for read/write
2. Up to **5** read-only secondary regions, replication lag < 1s.
3. Up to 16 read replicas per secodnary region.
4. RTO < 1 minute for disaster recovery

##### Aurora machine learning

Simple, optimized and secure integration between Aurora and AWS machine learning services.

1. Amazon SageMaker
2. Amazon Comprehend

### S3 (Simple Storage Service)

#### Overview

Bucket -> directory
object -> file

Buckets must have globally unique name but they are defined at region level.

Bucket naming convention:

1. no uppercase
2. no underscore
3. not an IP address.

S3 can be treated as a key-value store whose key is the path to the object.

The full path has the following pattern: `s3://bucket-name/prefix/object-name`

Max file size: 5TB. If you want to upload a file larger than 5GB, you need to use multipart upload.

#### S3 Storage class

|              | Standard                         | Standard IA                      | Standard One Zone IA                 | Intelligent Tieerng  | Glaciere (archive in valuts)        | Glacier Deep Archive |
| ------------ | -------------------------------- | -------------------------------- | ------------------------------------ | -------------------- | ----------------------------------- | -------------------- |
| Durability   | 99.999999999% across multiple AZ | 99.999999999% across multiple AZ | 99.999999999% in one AZ              | Same as Standard     |                                     |                      |
| Availability | 99.99% across multiple AZ        | 99.9% across multiple AZ         | 99.5%                                | 99.9%                |                                     |                      |
| Cost         | standard                         | lower cost than standard         | lower cost than standard IA          | has auto-tiering fee | Low cost  $0.004/GB + retrieval fee |                      |
| Use cases    | general purpose                  | disaster recovery, backup        | secondary backup and recretable data |                      | 10s of years storage                |                      |

##### Glacier & Glacier Deep Archive

Retrieval options

Glacier: minimal storage of **90** days

1. Expedited 1-5 minutes
2. Standard 3-5 hours
3. Bulk 5-12 hours

Glacier Valut lock. Adopt a WORM (write once, read many) model. Helpful for compliance and data rentention.

Glacier Deep Archieve: minimal storage of **180** days

1. Standard 12 hours
2. Bulk 48 hours

#### S3 object lock

1. must enable versioning
2. adopt a WORM (write once, read many) model
3. block object version deletion for a specific amount of time
4. Modes
   1. governance mode
   2. compliance mode

#### S3 moving between storage classes

Moving objects can be automated with lifecycle configuration

Rules can be created for certain prefix or object tags.

1. Transition actions
2. Expiration actions

#### S3 analytics 

Help determine when to transition objects from standard to standard IA.

#### S3 performance

S3 automatcially scales up to high request rates.

Can achieve at least 3,500 PUT/COPY/POST/DELETE and 5,500 GET/HEAD requests **per second per prefix** in a bucket.

KMS encryption will impact S3 performance. KMS quota persecond can be increased upon request.

##### S3 performance improvement

1. Multi-part upload
   1. recommended for file larger than 100 MB
   2. must enable for file > 5 GB
   3. parallel uploads
2. S3 Transfer Acceleration
   1. transfering file to an aws edge location first
   2. compatible with multi-part upload

##### S3 byte-range fetches

Parallel GET by requesting specific byte ranges

Use cases:

1. speed up downloads
2. retrieve partial data (head of file, etc)

##### S3 Select & Glacier Select

Use SQL to perform **server side filtering**.

1. less network transfer
2. less CPU on client side


#### S3 event notification

"S3" events like "ObjectRemoved", "ObjectCreated", etc.

#### S3 requester pays

Enabled at buckets level. Requesters must be authenticated with AWS identities. They pay for the networking cost.

#### S3 versioning

Versioning can be enabled at bucket level. Versioning can protect unintended deletes. 

Any object that was not versioned will have version null.

#### S3 encryption

##### Encryption at rest

|                     | SSE-S3                                   | SSE-KMS                                   | SSE-C                                    | **client side** encryption  |
| ------------------- | ---------------------------------------- | ----------------------------------------- | ---------------------------------------- | --------------------------- |
| Who handles the key | S3                                       | AWS KMS                                   | User                                     | Not applicable              |
| Encryption type     | AES-256                                  |                                           |                                          |                             |
| http(s) note        | "x-amz-server-side-encryption": "AES256" | “x-amz-server-side-encryption": ”aws:kms" | enforce  https and provide key in header | customer manages everything |

##### Encryption in transit

HTTPS is mandatory for SSE-C.

Both HTTP and HTTPS can be used in general.

#### S3 security

|     | User based   | Resource based                           |
| --- | ------------ | ---------------------------------------- |
|     | IAM policies | Bucket policies: **allow cross account** |
|     |              | Object ACL                               |
|     |              | Bucket ACL                               |

An IAM principal can access an S3 bucket if 

1. IAM permission allows it **OR** resource policy allows it
2. **AND** no explicit DENY.

##### S3 bucket policy

JSON based, very much like [IAM policies](#iam-policies). 

S3 bucket policy can be used to grant access to another account.

##### S3 security (others)

1. Networking: supports VPC endpoint
2. Logging and Audit:
   1. Access logs
   2. API call logs in CloudTrail
3. User security:
   1. MFA delete (must enable versioning first)
   2. Pre-signed URLs (limited time access)

MFA-Delete:

1. Only bucket owner (root account) can enable/disable MFA-Delete.
2. Can only be enabled using CLI

S3 access logs:

Any requests made to S3, from any account, authorized or denied will be logged into **another** S3 bucket.

##### S3 replication (cross region & same region)

Must enable versioning first.

1. Buckets can be in different accounts
2. asynchronous
3. needs proper IAM permission
4. not retroactive
5. optional DELETE operation replication
6. not chained

Use cases:

1. CRR: compliance, lower latency access, replication across accounts
2. SRR: log aggregation, replication between prod and dev.

#### S3 websites

S3 can host static website. If error **403**, check bucket policy to allow public reads.

Need to enable CORS if resources are in different buckets.

#### S3 consistency model

After successful write, update or delete, read and list requests will **immediately** reflect the changes.

#### S3 Pre-signed URLs

1. Valid default for 3600 seconds (1 hour). 
2. Inheret the permissions of the person who generated the URL for GET/PUT (Put must use SDK to generate).
  
Use cases:

1. allow premium resources download
2. temporarily allow uploading

### ElasticCache

#### Overview

1. managed Redis or Memcached services
2. make application stateless
3. may involve heavy application code changes

#### Redis vs Memcached

|                    | Redis                              | Memcached                           |
| ------------------ | ---------------------------------- | ----------------------------------- |
| Failover           | Multi-AZ with Auto-failover        | Multi-node for partitioning of data |
| High availability  | Yes with read replicas             | No                                  |
| Data durability    | AOF (append-only file) persistence | No                                  |
| Backup and restore | Yes                                | No                                  |
|                    |                                    | multi-threading architecture        |


#### Use cases

##### DB Cache

1. reduce load off of databases
2. must have an invalidation strategy

Gaming leaderboard example: **Redis Sorted Sets** allow unique and real-time element ranking

##### User session store

User logs into any of application
application writes session data to ElasticCache
User hits another instance and session data in ElasticCache ensure that user is logged-in.

#### Cache Security

1. **No IAM authentication**
2. **Redis AUTH** available 
3. Memcached support sasl-based authentication

#### ElasticCache Patterns

1. Lazy Loading: all read data is cached
2. Write through: adds or update data in the cache when updated to a db
3. Session store: store temporary session data in cache



## Analytics

### AWS Athena

1. **Serverless** service to perform analytics on S3 files.
2. Use SQL
3. Has JDBC/ODBC driver
4. Support CSV, JSON, ORC, Avro, Parquet


## Network

### Route 53

#### Overview

Route 53 is a managed DNS service that provides dynamic DNS resolution.

$0.5 per hosted zone (hostname suffix)

Route 53 resolves the "records" in the DNS zone to the correct IP address.

IN AWS, the most common records are:

1. A: hostname to IPv4
2. AAAA: hostname to IPv6
3. CNAME: hostname to hostname
4. Alias: hostname to AWS resources

The domain names can be:

1. public domain names one owns
2. private domain names that can be resolved by your instance in your VPCs.

#### Route 53 as a domain registrar

You can buy domain on Route 53

If you buy domain on 3rd party website

1. create a hostzone in route 53
2. update NS record on 3rd party website to use Route 53 name servers.


Every DNS record will have a TTL (time to live)

1. longer TTL: less traffic to DNS server but may be outdated
2. shorter TTL: more traffic to DNS server but easy to update DNS

#### Route 53 advanced features

1. load balancing
2. heath check
3. routing policies: simple, failover, geolocation, latency, etc.

#### CNAME and Alias

AWS resources expose AWS hostnames.

Alias is free and comes with native health check.

|          | CNAME                | Alias                           |
| -------- | -------------------- | ------------------------------- |
| pointing | hostname to hostname | hostname to an aws resource     |
| scope    | non-root domain      | root domain and non-root domain |

#### Routing Policies

##### Simple routing policy

Map a hostname to another hostname. Can't assign health check. If multiple records return, a random one will be chosen by the **client**.


##### Weighted routing policy

Control the weight of the requests that go to specific endpoint. 

1. Helpful to test new versions like A/B testing
2. Helpful to split traffic betweeen regions.
3. Can attach health check.

##### Latency routing policy

Redirect to the server that has the least latency close to clients.

1. Hepful when latency is important
2. Latency is evaluated in terms of user-aws region distance (not geologically)


##### Geo location routing policy

Routing based on user **location**. Can be hard-coded like traffic from a certain country goes to a certain endpoint, etc.

##### Geoproximity Routing Policy

based on geographic location of **users and resourcs**.

Can use **bias** to influence default traffic redirection policy.

Must use **Route 53 Traffic Flow** to use this feature.

##### Multi-value routing policy

Use when routing traffic to multiple resources. Up to **8** health records are returned. You can use it to associate health check with different resources.

However, it is not a substitute for Elastic Load Balancer.

#### Health Checks

Default health check interval: **30s** ( can set to **10s** with higher cost)

**15** health checkers check the endpoint so about **2s** average interval.

Health checks can be linked to Route 53 queries.

### AWS Elastic Beanstalk

#### Overview

Elastic Beanstalk is a developer centric view of deploying an application on AWS. Use common components but still have full control over the configuration.

Developer is only responsible for the application code.

Beanstalk is free but you pay for the underlying services.

Three architectures:

1. single instance
2. ASG + LB
3. ASG only

Three components:

1. Application
2. Application version
3. Environment name (dev, test, prod, etc)

Workflow:

![workflow EB](https://docs.aws.amazon.com/zh_cn/elasticbeanstalk/latest/dg/images/clearbox-flow-00.png)

# Tables and Quick Reference

TODO

# Solutions Architecturing

## Developing on AWS

Q: How to interact with AWS resources and services.

### EC2 instance metadata

EC2 instance can access metadata via `http://169.254.169.254/latest/meta-data`. The IAM role name can be accessed but not IAM policy.

### AWS SDK

1. AWS CLI is using Python SDK boto3.
2. SDk default region is `us-east-1`.

#### SDK credential security

1. credentials at `~/.aws/credentials`
2. instance profile credentials using IAM roles
3. environemntal variables

Never store credentials in code.

#### Exponential backoff

SDK API calls include retry mechanism with exponential backoff.

## Classic Solution Architecture

### Whatisthetime.com

Stateless web app

#### Step by step incremental improvement

1. single instance service
2. scaled both vertically & horizontally
3. add DNS server with TTL of 1 hour
4. add load balancer with health check and restricted security group rules
5. add auto-scaling group to manage EC2 instances
6. make app multi-AZ
7. reserve capacity of 2 in 2 different AZs for cost saving

### MyClothes.com

Stateful web app

Starting with LB, Route 53 and a multi-AZ ASG.

#### Step by step incremental improvement

1. Introduce stickiness
   1. introduce user cookies
   2. Add ElasticCache/DynamoDB to store and retrive user session data
2. Storing user data in Amazon RDS database
   1. Scaling reads by 
      1. adding RDS read replicas
      2. adding ElasticCache layer ( can also implement write-through)
   2. Upgrade RDS to multi-AZ to surivive disaster
3. Enforce security groups
   1. ELB to EC2
   2. EC2 to RDS
   3. EC2 to ElasticCache


### Mywordpress.com

access and display uploaded pictures.

Start with a multi-AZ LB, multi-AZ ASG and multi AZ RDS

#### Step by step incremental improvement

1. Use multi-AZ Aurora DB with read replicas
2. Store images with EBS (single instance application)
3. Store images with EFS (distributed application)

### Instantiating App quickly

EC2 instances:

1. Use a Golden AMI
2. Bootstrap using User data
3. Hybrid: mix Golden AMI and user data (Elastic Beanstalk)


RDS Database:

1. Restore from snapshot

EBS Volume:

1. Restore from snapshot


Typical 3-tier web app architecture:

![3-tier architecture](https://miro.medium.com/max/700/1*e7YeHUMESPtgjXtSzk_Ttw.png)