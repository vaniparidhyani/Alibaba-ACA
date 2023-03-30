---
description: ECS@Ali ~ EC2@AWS
---

# ECS - Not ReadMe

ECS instances provide a host of built-in security solutions, such as Virtual Firewalls, Internal network isolation, public IP Access, Anti-Virus and Denial of Service Attack protection.

Alibaba uses XEN and KVM Virtualisation to provision its ECS Instances. These instances, in turn, run on top of the X-Dragon Compute Platform and the Apsara distributed file system called Pangu, which provides the storage system.

The instance types follow a naming convention which depicts the instance family, instance generation and instance size, for Example, ecs.g5.large. ecs is a prefix (All ECS instances have this in the name), ‘g’ denotes instance family (in this case general purpose), 5 denotes the instance generation and implies the CPU to RAM ratio, in this case, a ratio of 1 to 4 (this means that for each CPU there is 4 GB RAM), and large denotes the instance size.

ecs.g5.large is the smallest instance in the general-purpose family and this instance has 2 CPUs, so with a ratio of CPU to RAM of 1 to 4 this instance has 2 CPUs and therefore 8GB of RAM.

#### ECS Types

**X86-Architecture**

**Entry Level (Shared Burstable):** You can accumulate CPU credits for your burstable instances, and consume those credits to increase the computing power of your workloads when required. Used for Web application servers, Lightweight applications, and development and testing environments.

**General Purpose:** Used for Websites, application servers, Game servers, Small and medium-sized database systems.

**Memory Optimised:** Used for data analysis and mining, and other memory-intensive enterprise applications.

**Big Data:** Used for Enterprises that need to compute, store, and analyze large volumes of data.

**Local SSD:** Used for Online transaction processing (OLTP) and high-performance databases.

**High Clock Speed:** Used for on-screen video and telecom data forwarding, High-performance scientific and engineering apps.

**Heterogenous Computing**

**GPU-based compute-optimized:** Used for Rendering and multimedia encoding and decoding, Machine learning, high-performance computing, and high-performance databases, Other server-high end workloads that require powerful concurrent floating-point compute capabilities.

**Field-Programable-Gate-Array-based compute-optimized:** Used for Deep learning and reasoning, Genomics research, Financial analysis, Image transcoding, Computational workloads such as real-time video processing, and security management.

#### ECS Storage

ECS Storage provides architecture-based Cloud disks for your operating system disks and data disks.

System disk sizes can be 20GB and 500GB.

Data Disks sizes can be between 20GB and 32TB and up to 16 Data Disks can be attached to a single ECS Instance. Cloud Disks can be mounted to any instance in the same zone, but cannot be mounted to instances across zones.

Cloud Disks are based on the **Apsara distributed file system called** “**Pangu**”. **Three** redundant copies are stored on different physical servers under different switches in the datacentre. This provides high data reliability in the case of a failure.

Currently, there are 3 types of Cloud Disk:

* **Ultra Disk**: Cloud disks with high cost-effectiveness, medium random IOPS performance, and high data reliability.
* **Standard SSD:** High-performance disks that feature consistent and high random IOPS performance and high data reliability.
* **Enhanced SSD:** ESSDs are ultra-high performance disks based on the next-generation distributed block storage architecture. Each ESSD can deliver up to 1 million of random IOPS and has low latency.

#### ECS Snapshots

Snapshots of disks can be taken for:

1. Disaster recovery and backup
2. Environment clone
3. Data development for mining, querying, etc
4. Enhanced fault tolerance

Snapshots can be created manually or automatically by creating a snapshot policy. Up to 64 snapshots can be created per disk and each snapshot is an incremental copy of the previous snapshot. When the maximum number of snapshots has been reached the oldest snapshot is deleted as a new one is created.

#### ECS Security Groups

They are Stateful Packet Inspection and packet filtering of network protocol, port, and source IP traffic to **allow or deny access.** You can configure security group rules to control the inbound and outbound traffic of ECS instances in the group.

There are 2 types of SG:

1. Basic security group: A basic security group is a virtual firewall that provides Stateful Packet Inspection (SPI), also known as dynamic packet filtering. You can configure security group rules to allow or deny ECS instances in basic security groups to access the Internet or intranet. Basic security groups support up to 2000 private IP
2. Advanced security group: They are a new type of security group. Compared with a basic security group, an advanced security group can contain more ECS instances and an unlimited number of private IP addresses. Security group rules in advanced security groups are easier to configure and maintain than those in basic security groups. Advanced security groups are applicable to enterprise-level users who own a large number of ECS instances or ENIs and require high maintenance efficiency.

ECS Instances cannot belong to both basic and advanced security groups at the same time, however. ECS instances in the same security group can communicate with each other through the internal network. ECS instances in different security groups are isolated from each other.

#### ECS Networking

1. VPC same as AWS
2. VSwitch is like the Subnets in AWS. You give them CIDR's, decide their AZ, assign them a route table and a NACL. Not all resources are aviable in all AZ's of a region, hence choose AZ accordingly! A VPC can have a maximum of 24 VSwitches.

ECS instances support two public IP address types. The first is NATPublicIP, which is assigned to a VPC-Connected ECS instance. This type of address can be released only, and cannot be disassociated from the instance. And the second is Elastic IP Address (EIP). An Elastic IP Address (EIP) is an independent public IP address that you can purchase and use.
