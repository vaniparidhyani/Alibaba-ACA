---
description: ECS@Ali ~ EC2@AWS
---

# ECS

ECS instances provide a host of built-in security solutions, such as Virtual Firewalls, Internal network isolation, public IP Access, Anti-Virus and Denial of Service Attack protection.

Alibaba uses XEN and KVM Virtualisation to provision its ECS Instances. These instances, in turn, run on top of the X-Dragon Compute Platform and the Apsara distributed file system called Pangu, which provides the storage system.

The instance types follow a naming convention which depicts the instance family, instance generation and instance size, for Example, ecs.g5.large. ecs is a prefix (All ECS instances have this in the name), ‘g’ denotes instance family (in this case general purpose), 5 denotes the instance generation and implies the CPU to RAM ratio, in this case, a ratio of 1 to 4 (this means that for each CPU there is 4 GB RAM), and large denotes the instance size.
