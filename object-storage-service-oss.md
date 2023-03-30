---
description: OSS@Ali ~ S3@AWS
---

# Object Storage Service (OSS)

OSS offers up to 99.995% service availability to protect against service outages and up to 12 nines of data durability to keep your data safe. It offers automatic scaling without effecting external services. It also offers automatic redundant data backup. And with the optional cross-region replication, it can support automatic failover. So redundancy.

There are two types of redundancy available in OSS. Local redundant storage, known as LRS and zone redundant storage known as ZRS. LRS stores the data of each object on multiple devices in the same region which ensures data durability and availability in case hardware failure. ZRS distributes user data across three zones within the same region. Even if one zone becomes unavailable, your data will still be accessible.

Following are more OSS features which are similar to S3@AWS

1. Security: RAM access, IP blacklist/whitelist and Logging
2. Cost: Pay for the volume of storage used, amount of data transfer and no. of API requests made.
3. Streaming upload/download
4. Lifecycle mngmnt
5. Archive storage
6. image processing, which supports format conversion, thumbnails, cropping, watermarks, scaling and other operations.

To access a bucket, an endpoint for the bucket is created automatically. An endpoint is the domain name used to access the bucket. OSS provides external services through HTTPS, HTTP, and RESTful APIs. Each region has its own dedicated endpoint. Access to a bucket through an intranet connection uses a different endpoint than when accessing the same bucket through the internet.

### OSS Security

Access Control: applied on bucket and objects. Private, Public Read and Public R/W are the access controls.

Bucket Policy: This allows you to grant permission on all, or just Specific resources in a bucket to RAM users from your [Alibaba Cloud](https://cloudacademy.com/library/alibaba-cloud/) account, other accounts, or anonymous accounts. Every object in OSS is enabled with HTTPS access by default. You can block HTTP access and restrict only HTTPS access. IP's can also be whitelist/blacklist. Can also whitelist domains who can access by using HTTP Referer.

Access Keys: using sts.

Server Side Encryption(SSE): OSS supports server-side encryption for uploaded data when enabled. When you upload data, OSS encrypts and stores the data. When you download data, OSS automatically decrypts the data and returns the original data to the user. The returned HTTP request header declares that the data has been encrypted on the server. KMS can be used for SSE.

RAM: roles and user policies and permissions.

