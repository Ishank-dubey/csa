# csa

Creating Placement in AZ and plce EC2 instances within that group for lower latency
True or False? Amazon S3 buckets in all Regions provide read-after-write consistency for PUTS of new objects and eventual consistency for overwrite PUTS and DELETES. - true\Placement Groups can be created across 2 or more Availability Zones.- false
You can add multiple volumes to an EC2 instance and then create your own RAID 5/RAID 10/RAID 0 configurations using those volumes.
It is possible to transfer a reserved instance from one Availability Zone to another.-true
RDS -AZ can be decided
DynamoDDB - AZ can nit be selected.

card - 
1. Cards create
2. move 
3. tit;e
4. color , delete , copy


functionality., css

1. Power Users cannot manage groups and users within IAM.
2. Root user has Administrator Access.
3. First thing to create an AWS account is to set up a/c usinfg company email address.
4. MFA can be applied on new users alike as root account.
5. New User do not have any access by default.
6. For S3 performance its good to not to have similr names as that can overwhelm the S3 prerformance so we can add some kind of Random Alphabet or Numerical before such data name.
7. S3 durability 11 x 9s and availability 99.9 SLA
8. S3 - Infrequently Accessed - but when needed its needed fast and a retrival fees is charged.(durability is 11 x 9s)
9. S3 Reduced Redundancy Storage with less durability i.e. 99.99% and same availavibity but very cheap.(facility failure is 1 and data in S3 must stay for 30 days atleast)
10. S3 Glacier - Data Archival - Low cost (data must stay in S3 for 90 minimum)
11. Transfer Acceleration helps transfer data in S3 between various regions using AWS Cloud Front edge locations.
12. Subresourses - ACL and Torrent
13. Bucket names are to be in lower case	
14. Any ewly created Bucket or Object is default - Private
15. S3 can be Encrypted using - S3 master key or AWS KMS master key.
16. Versioning after being turned on can only be disabled and not removed.
17. To make an object publically available the object itself shall have the pubic-read permission even if the bucket aleardy has public- read permission.
18. Versioning maintains all the versioned files so the storage in a Bucket keeps on increasing - may like to apply life cycle to other objects so as to save the space.
19. If a version is deleted it can not be restored back but an object can be using Delete Marker(Delete the delet marker make it appear in the console).
20. To prevent accidental deletes we can also enable Versioning's MFA  delete capability.
21. For cross region replication - versioning must be turned on. only The new or updated objects are replicated - Multiple region replication and transitive are not possible.
22. In S3 Cross region replication the Delete marker and version delitions are not replicated.
23. For Life Cycle amangement the versioning may be on or off(128 KB after 30 days).
24. Cloud front has - Origin(like S3, EC2, ELB etc.), Edge locations(seperate from AWS region or AZ) and Distribution(Collection of Edge Locations - Web Distributtion and RTMP).
25. Cloud front works with non aws Origin Server and can have multiple origins
26. Edge locations are Read/Write, Object can be cleared before TTL but there is a charge on that.
27. A Cloud front can have multiple origins and viewer access can be restricted via signed urls/cookies
28. Buckets can be secured viaBucket (Policy/Access control list), Encryption can be
    - In transit(SSL/TLS)
    - At rest
    - Server Side
      - SSE S3(Master key rotates, AES 256)
      - SSE KMS(more transparency but costs- order Trail)(Envelope key- key to master key)
      - SSE Customer(SSE C, key is managed by us and AWS manages encryption)
      - Client side is when client encrypts and sends to server.

29. Storage Gateway
       - NFS(flat files)File gateway(accessd theough NFS mount point)(On permise App -- NFS-Storage Gateway--Inernet or Direct Connect or AWS VPC--S3, stored on S3)
       - Volume Gateway(iSCSI,a virtual hard disk is backed up as incremantal snapsots on a EBS snapshot in cloud)
        - Stored Volumes -> entire data is available locally and the provides low latency access to data on premise- 1 to 16 TB(backedup on S3)
        - Cached Volumes-> S3 can be used as primary storage and frequently accessed data is retained locally(32 TB)
       - Tape Gateways(VTL- backup and archival)(instead of physical tape, virtual tapes are being used, netbackup, backup exac, Veeam)
Remember: Direct Connect is the direct data line between Data center and AWS

30. Snowball (Earlier AWS import/Export where we send pur own disk and thatwas used by AWS but due to different  firmats it became difficult)
      - An appliance that customer can store data in and send to Amazon and then the AWS can use that appliance to transfer the data to S3(the box provides secure data transfer and AWS does a s/w erasure of the data) 
      - Snowball Edge(has compute capacity as well like a data center like running lambda functions like a data acuisition device)
      - Snowmobile(a Truck and is for Extremely big amount of data) 
      - Snowball can import/export to and from S3
31. Transfer Acceleration 
      - S3 transfer acceleration uses the cloud front edge n/w (url format- bucketname.s3-accelerate.amazonaws.com and bucket static website BUCKETNAME.S3-website.REGION.amazonaws.com )
      - S3 bucket URL format - http://s3-REGION.amazonaws.com/BUCKETNAME	
32. S3 files size is 0 to 5TB
33. In life cycle-
      - Transition to IA after 30days (128KB)
      - Transition to Glacier(after 30 days in IA)
      - Object can be moved to Glacier directly for S3 if IA is not used the next day itself
      - Delete finally
34. Edge location has 50 locations accross world, edge locations can be READ/WRITE, TTL is in seconds(default 24 hours)
35. Access buckets can used to create access logs to log all the requests made to S3 bucket that can be stored in another bucket(same account or other account).
36. Multipart upload is possible in S3.
37. Minimim size in a S3 file is 1Byte.
38. EC2 options
      - On Demand: allows to pay a fixed rate by hour w/o committment, low cost, short spike
      - Reserved: capacity reservation (1 to 3 year contract will give cost advantage), predicatable usage
      - Spot: bid and starts when price goes lesser than bid, flexible timings are needed
      - Dedicated Hosts: Physical EC2 server that are dedicated physical machine(existing licances can be used and we can pay hourly) 
39.  In Spot instance the charges are on per hour basis- if the instance is terminated before an hour the charges wont be applied however if we terminated than we need to pay for the entire hour.
40. EC2 instance types(currentlt there is 10 types)
     - D2: Dense Storage- File servers/Data Ware House/Hadoop
     - R4: Memory Optimized- Memory intensive Apps/DBs - RAM
     - M4: General Purpose - Application Servers - main choice for GPIO
     - C4: Compute Optimized - CPU intensive - COMPUTE
     - G2: Graphics Intensive- Video Encoding/3D Application - GRAPHICS
     - I2: High Speed Storage- NoSQL storage - IOPS	
     - F1: Field Programmable Gate Array- Hardware Acceleration for your code - FPGA
     - T2: Loweset Cost, General Purpose- Web servers /Small DBs - T2 Micro
     - P2: Graphics/General Purpose GPU- Machine Learning/Bit coins mining - GRAPHICS
     - X1: Memory Optimized- SAP Hanna/Apache Spark - Extreme Memory
41. EBS
      - Placed in a specific AZ but replicated(stotage Array is replicated).
42. EBS Types
      - General Purpose SSD(upto 10,000 IO{S and burst of 3000 IOPS for extended periods of time)
      - Provisioned IOPS SSD: IO intensive Apps i.e. Large RDS or NoSQL(>10000 IOPS < 20000 IOPS)
      - Throughput optimized HDD(Magnetic): Big data, ware houses, log processing, CAN not BOOT from, frequently accessed workloads 
      - Cold HDD: Lowest cost, File Server, infrequently accessed, can NOT BOOT from them, less frequently accessed workloads 
      - Magnetic (standard): BOOTABLE and lowest cost, infrequently accessed, lowest cost on storage
43. 1 EBS can be mounted in 1 EC2 not multiple
44. Security Group is present by default when a default VPC is created and when a new AWS a/c is created
45. Accidental termination protection can be checked when creating a EC2 instance
46. Root volume - has to be bootable - can be only General Purpose SSD, Provisioned IOPS, Magnetic(Standard)
47. We can add volumes
48. By default the attached root volume is Deleted on Termination of EC2 instance
49.Security group is a virtual firewall, they have SSH -22, HTTP-80, HTTPS-443, RDP-3389, MySQL/Aurora-3306
50. CMOD 400 MyKeyPair.pem , ssh ec2-user@IP -i myKeyPair.pem, sudo su, yum update -y, yum install httpd, dc /var/www/html, nano index.html, service httpd start, chkconfig httpd on
51. The Root volume of a EC2 instance can be Encrypted by using normal creation ways(default AMIs), additional volumes can be.
52. One EC2 instance can have multiple SG
53. The change in SG will apply immediately
54. SG are stateful- both ways are configured inbound and outbound rules, everything else is blocked by default and no deny possible and dependes on region as well
55. EC2 instance- Actions - Change Security groups to edit SG accociated with EC2 instance

		
