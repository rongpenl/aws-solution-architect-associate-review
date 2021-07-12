

- [Notes](#notes)
  - [Services overview](#services-overview)
    - [Regions & Availability Zones (AZs)](#regions--availability-zones-azs)
    - [Global services and regional services](#global-services-and-regional-services)
      - [Global services](#global-services)
      - [Regional service examples](#regional-service-examples)
  - [Identity and Access Management (IAM)](#identity-and-access-management-iam)
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
- [Tables and Quick Reference](#tables-and-quick-reference)

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

## Identity and Access Management (IAM)

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

|            | EBS                                                             | EFS |
| ---------- | --------------------------------------------------------------- | --- |
| Attachment | **One** instance at a time, io support multi-attachement in same AZ |  Support  |
| Migration  | take snapshot 




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

# Tables and Quick Reference