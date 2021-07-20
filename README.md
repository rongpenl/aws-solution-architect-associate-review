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
  - [AWS CloudFront](#aws-cloudfront)
    - [Origins](#origins)
    - [CloudFront vs S3 Cross Region Replication](#cloudfront-vs-s3-cross-region-replication)
    - [ClounFront Signed URL & Signed Cookies](#clounfront-signed-url--signed-cookies)
    - [CloudFront Multiple Origin](#cloudfront-multiple-origin)
    - [Origin Groups](#origin-groups)
    - [CloudFront Geo Restriction](#cloudfront-geo-restriction)
    - [CloudFront Pricing](#cloudfront-pricing)
  - [AWS Global Accelerator](#aws-global-accelerator)
    - [Features:](#features-1)
    - [Unicast & anycast IP](#unicast--anycast-ip)
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
    - [AWS Snow family](#aws-snow-family)
      - [Data migration](#data-migration)
      - [Edge computing](#edge-computing)
      - [AWS OpsHub](#aws-opshub)
    - [AWS Storage Gateway](#aws-storage-gateway)
      - [File Gateway](#file-gateway)
      - [Volume Gateway](#volume-gateway)
      - [Tape Gateway](#tape-gateway)
      - [Hardware appliance](#hardware-appliance)
      - [Storage gateway exam tips](#storage-gateway-exam-tips)
    - [AWS FSx](#aws-fsx)
      - [AWS FSx for windows](#aws-fsx-for-windows)
      - [AWS FSx for Lustre](#aws-fsx-for-lustre)
      - [FSx file system deployment options](#fsx-file-system-deployment-options)
    - [AWS transfer family](#aws-transfer-family)
  - [Analytics](#analytics)
    - [AWS Athena](#aws-athena)
  - [AWS Integration & Messaging](#aws-integration--messaging)
    - [SQS](#sqs)
      - [Standard Queue](#standard-queue)
        - [Producers & Consumers](#producers--consumers)
        - [SQS with ASG](#sqs-with-asg)
        - [SQS security](#sqs-security)
        - [Message visibility timeout](#message-visibility-timeout)
      - [SQS Dead Letter Queue](#sqs-dead-letter-queue)
      - [SQS Delay queue](#sqs-delay-queue)
      - [SQS Temporary Queue](#sqs-temporary-queue)
      - [SQS FIFO Queue](#sqs-fifo-queue)
    - [SNS (Simple Notification Service)](#sns-simple-notification-service)
      - [SNS publishing](#sns-publishing)
      - [SNS security](#sns-security)
      - [SNS FIFO topic](#sns-fifo-topic)
      - [SNS message filtering](#sns-message-filtering)
    - [Kinesis](#kinesis)
      - [Overview](#overview-4)
      - [Kinesis data streams (KDS)](#kinesis-data-streams-kds)
      - [Kinesis data firehose (KDF)](#kinesis-data-firehose-kdf)
      - [KDS vs KDF](#kds-vs-kdf)
      - [Kinesis data analytics (KDA)](#kinesis-data-analytics-kda)
    - [Ordering issue](#ordering-issue)
      - [Ordering data into Kinesis (Stream)](#ordering-data-into-kinesis-stream)
      - [Ordering data into SQS](#ordering-data-into-sqs)
    - [SNS, SQS and Kinesis use cases](#sns-sqs-and-kinesis-use-cases)
      - [SNS + SQS: Fan out](#sns--sqs-fan-out)
      - [SNS FIFO + SQS FIFO Fan out](#sns-fifo--sqs-fifo-fan-out)
      - [Kinesis vs SQS FIFP ordering](#kinesis-vs-sqs-fifp-ordering)
    - [Messaging services comparison](#messaging-services-comparison)
    - [Other non cloud-native messaging services](#other-non-cloud-native-messaging-services)
      - [Amazon MA (managed Apache ActiveMQ)](#amazon-ma-managed-apache-activemq)
  - [Container](#container)
    - [Docker basics](#docker-basics)
    - [Docker conatiners management](#docker-conatiners-management)
    - [ECS (Elastic Container Service)](#ecs-elastic-container-service)
      - [IAM roles for ECS tasks](#iam-roles-for-ecs-tasks)
      - [Data volumes (EFS file system)](#data-volumes-efs-file-system)
      - [Porting](#porting)
      - [ECS rolling update](#ecs-rolling-update)
    - [Fargate (Serverless Container Platform)](#fargate-serverless-container-platform)
      - [Porting](#porting-1)
    - [ECR (AWS Elastic Container Registry)](#ecr-aws-elastic-container-registry)
    - [EKS (AWS Elastic Kubernetes Service)](#eks-aws-elastic-kubernetes-service)
  - [Serverless Overview](#serverless-overview)
    - [AWS Lambda](#aws-lambda)
      - [Lambda Benefits:](#lambda-benefits)
      - [Lambda Example:](#lambda-example)
      - [Lambda limitation](#lambda-limitation)
      - [Lambda@Edge](#lambdaedge)
    - [DynamoDB](#dynamodb)
      - [Overview](#overview-5)
      - [Basics](#basics)
      - [Provisioned throughput](#provisioned-throughput)
      - [DAX (DynamoDB Accelerator)](#dax-dynamodb-accelerator)
      - [DynamoDB Streams](#dynamodb-streams)
      - [Security and other features](#security-and-other-features)
    - [AWS API Gateway](#aws-api-gateway)
      - [Overview](#overview-6)
      - [Integration](#integration)
      - [Security](#security)
        - [IAM permissions](#iam-permissions)
        - [Lambda Authorizer](#lambda-authorizer)
        - [Cognito User Pools](#cognito-user-pools)
    - [AWS Cognito](#aws-cognito)
  - [Network](#network)
    - [Route 53](#route-53)
      - [Overview](#overview-7)
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
      - [Overview](#overview-8)
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
   1. partition information is treated as metadata for EC2 instances
   2. partitions failure won't affect other partitions
   3. suitable for tasks like **Hadoop, Kafka, Cassandra**

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

## AWS CloudFront

CloudFront is a Content Delivery Network (CDN)

1. 216 point of presense globally
2. DDoS protection, integratd with Shield, AWS WAF.
3. Can expose external https and talk to internal https backends.

### Origins

1. S3 bucket
   1. security with CloudFront Origin Access Identity (OAI)
   2. can be used as ingress
2. Custom Origin (http)
   1. ALB (must be public, EC2 behind it can be private)
   2. EC2 (must be public)
   3. S3 website
   4. any other http backends

### CloudFront vs S3 Cross Region Replication

|                | CloudFront       | S3 CRR                              |
| -------------- | ---------------- | ----------------------------------- |
| where          | Global edge      | regions where replication is set up |
| data freshness | cached for a TTL | updated near real time              |
| use cases      | static resources | dynamic content                     |

### ClounFront Signed URL & Signed Cookies

Policy can

1. include URL expiration
2. include ip ranges limitation
3. specify trusted signers ( which AWS accounts can create signed URLS)

|     | CloudFront Signed URL                               | S3 pre-signed URL                                                             |
| --- | --------------------------------------------------- | ----------------------------------------------------------------------------- |
|     | Use account wide key-pair that only root can manage | Use IAM key of the signing principal, inherent the permission of the IAM role |
|     | can filter by IP, date, expiration                  | limited lifetime                                                              |
|     | caching                                             | no caching                                                                    |

### CloudFront Multiple Origin

Match path pattern or content type to route to different kinds of origins

### Origin Groups

Increase high-availability by using multiple origins in an origin group. If the primary origin fails, the secondary origin will be used.

### CloudFront Geo Restriction

Create whitelist or blacklist

Use cases: to comply with copyright laws.

### CloudFront Pricing

1. Class All
2. Class 200 (exclude most expensive regions)
3. Class 100 (only the least expensive regions)

## AWS Global Accelerator

Allow users to leverage AWS internal network to route to your application.

Works with Elastic IP, EC2 instance, ALB, NLB, public or private.

### Features:

1. Consistent performance
   1. no issue with client cache as IP doesn't change
   2. intelligent routing
2. Health check
3. Security
   1. only 2 external IP
   2. DDoS protection with AWS shield.

### Unicast & anycast IP

1. unicast IP: one server holds one IP address
2. anycast IP: all servers hold the same IP address

AWS Global accelerator create 2 anycast IP for your application and anycast IP send traffic directly to edge locations, which forward traffic to your application.

|     | CloudFront                                          | Global Accelerator                                                                       |
| --- | --------------------------------------------------- | ---------------------------------------------------------------------------------------- |
|     | both cacheable content and dynamic content like API | wider range of applications over TCP or UDP                                              |
|     | content served at the edge                          |                                                                                          |
|     |                                                     | good fit for non-http use like gaming, IOT or voice over IP                              |
|     |                                                     | good for http cases that require static IP address, deterministic fast regional failover |

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

|              | Standard                         | Standard IA                      | Standard One Zone IA                 | Intelligent Tieerng  | Glaciere (archive in valuts)       | Glacier Deep Archive |
| ------------ | -------------------------------- | -------------------------------- | ------------------------------------ | -------------------- | ---------------------------------- | -------------------- |
| Durability   | 99.999999999% across multiple AZ | 99.999999999% across multiple AZ | 99.999999999% in one AZ              | Same as Standard     |                                    |                      |
| Availability | 99.99% across multiple AZ        | 99.9% across multiple AZ         | 99.5%                                | 99.9%                |                                    |                      |
| Cost         | standard                         | lower cost than standard         | lower cost than standard IA          | has auto-tiering fee | Low cost $0.004/GB + retrieval fee |                      |
| Use cases    | general purpose                  | disaster recovery, backup        | secondary backup and recretable data |                      | 10s of years storage               |                      |

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

|                     | SSE-S3                                   | SSE-KMS                                   | SSE-C                                   | **client side** encryption  |
| ------------------- | ---------------------------------------- | ----------------------------------------- | --------------------------------------- | --------------------------- |
| Who handles the key | S3                                       | AWS KMS                                   | User                                    | Not applicable              |
| Encryption type     | AES-256                                  |                                           |                                         |                             |
| http(s) note        | "x-amz-server-side-encryption": "AES256" | “x-amz-server-side-encryption": ”aws:kms" | enforce https and provide key in header | customer manages everything |

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

### AWS Snow family

Snowball can't import to Glacier directly. Must go through S3 first in combination with S3 lifecycle policy.

#### Data migration

1. Snowcone
2. Snowball Edge
3. SNowmobile

|                | Snowcone (smallest)         | Snowball Edge (have compute optimized or storage optimized versions) | Snowmobile              |
| -------------- | --------------------------- | -------------------------------------------------------------------- | ----------------------- |
|                | 8TB                         | 80TB                                                                 | < 100 PB                |
| migration size | < 24 TB, online and offline | up to petabytes, offline                                             | up to exabytes, offline |
| datasync agent | builtin                     | no                                                                   | no                      |

#### Edge computing

1. Snowcone
2. Snowball Edge

#### AWS OpsHub

A software to manage AWS snow family devices.

### AWS Storage Gateway

AWS is pushing for hybrid cloud, connecting on-premise data storage with AWS cloud.

Three types on the user side:

1. Volume (EBS, EC2 instance store)
2. File (EFS, FSx)
3. Object (S3, Glacier)

Three major services on the AWS side:

1. EBS
2. S3
3. Glacier

#### File Gateway

Configure S3 bucket with NFS and SMB protocols. Support S3 standard, S3 IA and S3 one zone IA. Can mount on any servers.

Can integrate with **Active Directory** for user authentication.

![NFS protocol file gateway](https://d1.awsstatic.com/cloud-storage/Amazon%20S3%20File%20Gateway%20How%20It%20Works%20Diagram.96e9f7180c6ec8b6212b4d6fadc4a9ac4507b421.png)

#### Volume Gateway

Block storage using iSCSI protocol backed by S3.
Backed by EBS snapshots which can help restore on-premises volumes.

1. cached volumes: low latency access to most recent data
2. stored volumes: entire dataset is on premise

![volume gateway](https://d1.awsstatic.com/cloud-storage/volume-gateway-diagram.eedd58ab3fb8a5dcae088622b5c1595dac21a04b.png)

#### Tape Gateway

Virtual Tape Library (VTL) backed by Amazon S3 and Glacier.

#### Hardware appliance

1. on-premise virtualization
2. storage gateway hardware appliance

#### Storage gateway exam tips

| Keywords                           | Services           |
| ---------------------------------- | ------------------ |
| On-premise storage to the cloud    | Storage gateway    |
| File access, NFS, active directory | File gateway       |
| Volumes/Blocks                     | Volume gateway     |
| VTL tape                           | Tape gateway       |
| no on-premise virtualization       | hardware appliance |

### AWS FSx

#### AWS FSx for windows

Fully managed windows file system share drive with active directory integration.

Can be configured to be multiple AZ.

#### AWS FSx for Lustre

Linux + cluster -> Luxtre

Parallel distributed file system for high performance computing (HPC).

#### FSx file system deployment options

- Scratch file system

Temporary storage without duplication for short-term processing, optimizing cost.

- Persistent file system

Long-term storage with duplicated data in same AZ. Replace failed files within minutes.

### AWS transfer family

For file transfer into and out of Amazon S3 or Amazon EFS using the FTP protocol.

1. AWS Transfer for FTP
2. AWS Transfer for FTPS
3. AWS Transfer for SFTP

![AWS transfer family](https://d1.awsstatic.com/cloud-storage/aws-transfer-family-s3-efs-how-it-works-diagram.6ff1dc0d717f63d4207ce4670a729aabb85d0d70.png)

## Analytics

### AWS Athena

1. **Serverless** service to perform analytics on S3 files.
2. Use SQL
3. Has JDBC/ODBC driver
4. Support CSV, JSON, ORC, Avro, Parquet

## AWS Integration & Messaging

SQS, SNS and Kinesis to decouple applications.

1. Simple Queue Service (SQS): queue model
2. Simple Notification Service (SNS): pub/sub model
3. Kinesis: realtime streaming model

### SQS

#### Standard Queue

1. oldest offering.
2. limitation of 256KB per message sent.
3. default message retention is 4 days, maximum is 14 days.
4. unlimited throughput and number of messages in queue.

5. Can have duplicate messages: **at least once delivery**
6. Can have out of order messages: **not FIFO**

##### Producers & Consumers

Producer using SDK.

Consumers poll SQS for messaging (up to 10 messages at a time).

Delete messages after consuming.

##### SQS with ASG

Cloudwatch can monitor the queue length to autoscale the number of EC2 instances consuming the queue.

##### SQS security

Encryption:

1. In-flight using https
2. at-rest using KMS keys

Access control:

1. IAM policies to regulate access to the SQS API

SQS access policy:

1. cross-account access
2. allowing other services to write to an SQS queue

##### Message visibility timeout

After a message is polled by a consumer, it becomes invisibile to other consumers. The default message visibility timeout is **30 seconds**. If after 30 seconds the processing is not complete, the message is visibile again for other consumers.

1. too low message visibility timeout, message may be processed twice.
2. too high visibility timeout, reprocessing when crash will take long time (less efficient)

#### SQS Dead Letter Queue

After certain amount of times of retrying, a message is moved to a dead letter queue. Default retention is **14** days. Useful for debugging.

#### SQS Delay queue

Delay a message up to **15 minutes**. The default is 0 seconds.

#### SQS Temporary Queue

Leverage virtual queues to create/delete virtual queues with lower overhead. Useful for building request-response systems with high throughput.

#### SQS FIFO Queue

1. First in first out
2. throughput is limited to 300 msg/s (without batching) and 3000 msg/s (with batching)
3. exactly-once

### SNS (Simple Notification Service)

Send one message to **many** receivers.

As many event listeners as we want. Up to 10,000,000 subscriptions per topic with 100,000 topic limit.

Subscribers can be

1. SQS
2. http/https
3. Lambda
4. Emails
5. SMS messages
6. Mobile notification

#### SNS publishing

1. Topic publish (manage topics/ publish to topics/ create subscriptions using SDK)
2. direct publish (for **mobile** apps SDK)

#### SNS security

Encryption:

1. In-flight using https
2. at-rest using KMS keys

Access control:

1. IAM policies to regulate access to the SNS API

SQS access policy:

1. cross-account access
2. allowing other services to write to an SNS queue

#### SNS FIFO topic

1. ordering by group ID
2. deduplication using deduplication ID or content based deduplication.

SNS FIFO can only have SQS FIFO as a subscriber.

Same throughput as SQS FIFO.

#### SNS message filtering

JSON policy used to filter messages based on certain fields.

### Kinesis

#### Overview

Collect, process and analyze streaming data in real-time.

1. Kinesis data streams
   1. capture, process and store data streams
2. Kinesis data firehose
   1. **load** data streams into **aws data stores**
3. Kinesis data analytics
   1. **analyze** data streams using SQL or Apache Flink
4. Kinesis video streams
   1. capture, process and store **video** streams

#### Kinesis data streams (KDS)

1. Ability to **reprocess** data.
2. Rentention can be as long as 365 days.
3. Data is immutable.
4. Billing is per **shard** provisioned, can have as many shards as wanted.

#### Kinesis data firehose (KDF)

1. Fully managed, automatic scaling, **serverless**
2. Pay for data going through firehose
3. Near real time processing
4. support many data formats and customized data **transformation** using AWS lambda.
5. No data rentention

#### KDS vs KDF

| Kinesis data stream                                  | Kinesis data firehose                                        |
| ---------------------------------------------------- | ------------------------------------------------------------ |
| **streaming** services for ingesting                 | **load** streaming data into S3, Redshift, ES, http endpoint |
| **provisioned**, SDK to write producer/customer code | fully **managed** with automatic scaling                     |
| real-time                                            | near real-time                                               |
| **retention** up to 365 days                         | no retention                                                 |
| support **replay** capability                        | doesn't support replay capabilities                          |

#### Kinesis data analytics (KDA)

1. Perform real-time analytics on Kinesis streams
2. automatically scaling/serverless
3. create analytics streams out of the real-time queries

### Ordering issue

#### Ordering data into Kinesis (Stream)

Shard-wise ordering: add partition key to the message to ensure same key
always go to the same shard.

#### Ordering data into SQS

For standard SQS, there is no ordering.

For SQS FIFO, if there is only one consumer, there is no ordering.

For multiple consumers with SQS FIFO, add a group ID to the messages (equivalent to the partition key) to fan-out the messages to consumers. Each group maintain in-group ordering.

### SNS, SQS and Kinesis use cases

#### SNS + SQS: Fan out

Publish once in SNS, receive in all SQS queus that are subscribers.

SNS topic -> SQS queues.

Make sure that access policy of SQS allows for SNS to write.

Application: S3 event to multiple SQS queues with SNS topic fan-out.

#### SNS FIFO + SQS FIFO Fan out

1. deduplication
2. fan out
3. ordering

#### Kinesis vs SQS FIFP ordering

Kinesis maintains ordering in each shard. SQS FIFO maintains order by assigining a group ID to each message.

### Messaging services comparison

|     | SQS                                    | SNS                            | Kinesis                    |
| --- | -------------------------------------- | ------------------------------ | -------------------------- |
|     | Csonsumers pull data                   | Push data to subscribers       | Standard: pull data        |
|     | No data persistence                    | No data persistence            | data persistent for replay |
|     | no provision                           | no provision                   | provision throughput       |
|     | ordering for FIFO                      | ordering for FIFO              | ordering at shard level    |
|     | can have as consumers as we want (asg) | up to 12.4 million subscribers | enhanced fan-out           |

### Other non cloud-native messaging services 

#### Amazon MA (managed Apache ActiveMQ)

1. Doesn't scale as much as SQS/SNS 
2. Have both queue feature and topic feature

## Container 

### Docker basics 

Pass

### Docker conatiners management 

1. ECS: Elastic container service
2. AWS fargate: serverless container platform
3. EKS: AWS managed kubernetes  

### ECS (Elastic Container Service)

1. One must provision & maintain the EC2 instances that are running the ECS cluster.
2. Integrated with ALB (Application Load Balancer)

#### IAM roles for ECS tasks

1. EC2 instance profile (used by the ECS agent)
   1. EC2 instance level to interact with ECS services
2. ECS task role
   1. allow each task to have specific roles 
   2. defined in the **task definition**

#### Data volumes (EFS file system)

1. Works for both EC2 tasks and fargate tasks
2. across AZ
3. Fargate + EFS = serverless application and data

#### Porting 

ECS uses **dynamic port number**. ALB supports finding the right port automatically but permission must be granted so ALB can access any EC2 instance ports in the EC2 instance security group policy.

#### ECS rolling update

Specify min, max to rolling out instance upgrades.

### Fargate (Serverless Container Platform)

1. No need to provision the infrastructure
2. AWS runs containers based on CPU /RAM needed.

#### Porting 

Each task will have a unique **IP**. The ALB should be able to access the **task port** of the ENI (Elastic network interface).


### ECR (AWS Elastic Container Registry)

1. Store, manage and deploy containers on AWS
2. Pay for what you use
3. Support image vulnerability scanning, version, tag, image lifecycle, etc.


### EKS (AWS Elastic Kubernetes Service)

1. Launch managed Kubernetes clusters on AWS
2. Supports both EC2 or fargate

## Serverless Overview 

This section may also contain some contents that are discussed somewhere else.

Serverless services on AWS

1. AWS Lambda
2. DynamoDB
3. AWS Cognito
4. API Gateway
5. S3
6. SNS & SQS 
7. Kinesis Data Firehose
8. Aurora Serverless
9. Step functions 
10. Fargate

### AWS Lambda 

1. no servers to manage
2. short executions with time limitation
3. run on demand 
4. automatically scaling

#### Lambda Benefits:

1. easy pricing with free tier computing resources
   1. pay per calls
   2. pay per duration
2. integrated with whole AWS suite of services
3. Easy monitoring with CloudWatch
4. Support multiple languages
   1. JS
   2. Python
   3. Ruby
   4. java
   5. etc

#### Lambda Example:

1. serverless thumbnail creation
2. serverless cron jobs

#### Lambda limitation

1. Execution
   1. memory allocation 128 MB - 10 GiB
   2. execution time: 15 mins
   3. environmental variables: 4 KB
   4. disk capacity in the function container: 512 MB
   5. concurrency execution: 1000
2. deployment
   1. deployment size: 50 MB 
   2. size of uncompressed deployment (code + dependencies): 250 MB

#### Lambda@Edge

deploy AWS Lambda as deploying CDN

1. more responsive application
2. deployed globally
3. customize the CDN content
4. Pay only for what you use

Lambda can be **inserted** to multiple stages in the request-response process between user, cloudfront and origin.

### DynamoDB

#### Overview

1. **NoSQL** database
2. fully managed, scales to massive workloads
3. integrated with IAM for security, authorization and administration
4. event-driven programming with dynamoDB streams
5. Low cost and auto scaling capabilities.

New features:

1. Transactions: all or nothing
2. On demand: automatical scales
   1. 2.5 times more expensive than provisioned capacity
   2. suitable for unpredictable spikes

#### Basics 

DynamoDB is made of **tables** whose rows are called **items**. Items have **primary keys** and attributes.

Common data types include string, number, binary, list, map, set, etc.

#### Provisioned throughput

Must have provisioned read and write capacity

1. RCU (Read capacity unit):
   1. 1 strongly consistent read of 4KB per second
   2. 2 eventually consistent read of 4KB per second
2. WCU:
   1. 1 write of 1KB per second

Throughput can be exceeded temporarily using **burst credit**.

#### DAX (DynamoDB Accelerator)

1. Cache for DynamoDB. Micro second latency for cached reads & queries.
2. Default TTL 5 min
3. Solves hot key problem

#### DynamoDB Streams

Changes in DynamoDB can end up in a DynamoDB Stream, which can be consumed by AWS Lambda, etc. 

Streams have a 24 hour retention.

#### Security and other features

Security:

1. VPC endpoint available
2. KMS for at-rest, SSL/TLS for in-transit
3. IAM to manage access

Backup & Restore

1. Point in time
2. No performance impact

Global table: multiple regions, fully replicated with high performance

1. Active replications
2. **Must enable DynamoDB Streams**

Local development available.

DMS can be used to migrate to DynamoDB.

### AWS API Gateway

#### Overview

1. Support websocket protocol 
2. Handle API versioning
3. Handle different environment 
4. Handle security 
5. Create API keys that handle request throttling
6. Swagger/Open API importing
7. Generate SDK and API specifications
8. Transform and validate API responses
9. Cache API responses

#### Integration

1. Lambda functions
2. HTTP endpoint
3. AWS Services

Classification by endpoint spatial type

1. edge-optimized (default)
   1. through cloud front edge location 
2. regional
   1. for clients within the same region
3. private 
   1. only be accessed from your VPC using ENI
   2. can use resource policy to define access

#### Security 

##### IAM permissions

1. Create IAM policy authentication and authorization and attach to user/roles. 
2. Leverage "Sig v4" capacity where IAM credentials are in the headers.

##### Lambda Authorizer

1. Use AWS Lambda to validate the token in header. 
2. Both authentication and authorization
3. Helps to use Oauth SAML and 3rd party type of authentication.
4. Lambda must return an IAM policy for the user, very **flexible**


##### Cognito User Pools

1. Cognito fully manges user life-cylce
2. API gateway verifies identity automatically from AWS Cognito
3. Only **authentication**, not **authorization**, which requires customized code.

### AWS Cognito


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
