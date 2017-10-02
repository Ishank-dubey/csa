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
56. lsblk(volumes that are mounted), mkfs -t ext4 /dev/xvdb, mkdir /aDirectory, mount  /dev/xvdb /aDirectory, lsblk, cd /aDirectory, umount /dev/xvdb
57. Detaching can be done from Volumes tab of the Web Console or Force Detach if the volume  is mounted 
58. Detach the Volume, Take Snapshot, Restore a Volume from the Snap shot (change the stoarage or upgrade) and the then got to volumes, select te restored volume and Attach(a way to upgrade volume)
59. lsblk will reveal the volume, check the fles in a volume by file -s /dev/xvdf, mount to the /aDirectory
60. If we change volume on the fly we must wait 6hours before making another change
61. EBS volumes can be scaled up only
62. Volumes must be in the same AZ as the EC2 instance
63. RAID
     - Redundant Array of Independent Disks
          - RAID 0 -Good Performance but NO Redundency, Stripped
          - RAID 1-Mirrored, Redundancy,
          - RAID 5-Good for Reads, Bad for Writes and its use is discouraged(parity checkss can be performed using this)
          - RAID 10- Combination of RAID0 and RAID 1
     - RAID is used to get a desired IOPS performance
     - New EC2 instance with Windows AMI - Add RDP permission to SG(port 3389)- RDP into instance (Get Windows Password, username- Administrator)and Add Disk to a Volume(Stripped- RAID0)
     - RAID Snapshot - While taking a snapshot Cached Data is not stored so in RAID its a problem - Need Application Consistent Snapshot
         - Stop Application from Writing to Disk
         - Flush cache Data to disk
          - Freeze the file system
          - Unmount the RAID array
          - Shutting the down the EC2 instance(easiest)
64. AMI Creation(useful way to encrypt the root volume)
     - Stop Ec2(Essential for Application Consistent Backup)
     - Volumes -Select root volume - Actions- Create Snapshot(can not encrypt still) now this Snapshot can be copied, Image created(While doing that we get am option to Encrypt the copy then we can create an Image in AMI                tab)
     - Only unencryped Snapshots can be Shared
65. EBS are more durable and Instance Stores are Ephimeral, Instance Stores can only be Rebooted or Terminated`and if the underlying host fails we loose it and by default the root volume goes on Termination.
66. All AMIs are either EBS backed or Instance Store Backed so Provisioning Time is low for EBS backed AMI	
67. In Reboot the data is safe in bith EBS and Instance Store
68. Load Balancers
     - Application Load Balancers(layer 7 i.e. http and https)
     - Classic Load Balancers(layer 4)
69. No Public IP address available for ELB but DNS Name
70. Application Load Balanver has Target Group, same EC2 can be registered in more than one ELB
      - Instances are inService or OutOfService in the Load Balancer - Health Check
71. Cloud Watch -Dashboards - Add Widgets and all the Services supported by Cloud Watch and used by user wil be visible.
      - Dashboard -For EC2 we have CPU, Disk, Status (EC2 leveal and Hypervisor), Network related metrices, We can also have cistome metrice(for RAM for Example)(in Host layer)
      - Alarm -Select Metric - Create Alaram - Notification Method when a Threshold is reached
      - Events - Respond to State Changes in AWS Resourses(e.g. When EC2 is running run Lambda)
      - Logs -Monitor at Application Level and log events and store as well
      - Metrices
      - Standard Monitering is 5 mins, detailed Monitoring is 1 mins 
      - CLoud watch is for logging , monitering and storing logs vs Cloud Trail is for auditing i.e. moniter AWS Environment - Like a new user, new role, new S3 are logged using Trail
72. AWS CLI
     - aws s3 ls (unable to locate creds)
     - aws  config -Enter access key id, Scret Access Key, region(eu-west-2) 
     - aws s3 ls (shows the buckets all around the world as S3 is global)
     - To Find the creds in the EC2 - cd ~, ls -a, cd .aws, ls(shows config and credentials of the user with programmatic access to Admin)
     - aws ec2 describe-instances(all the instance even terminated ones)  
     - aws ec2 terminate-instances --instance--ids INSTANCEID
     - Roles are created Globally
     - Attaching the IAM role to possible on a running EC2
73. S3 CLI and Regions
     - aws s3 cp --recursive s3://aclloudguru /home/aDir --region 	REGIONof EC2
     -#!/bin/bash (for bash script the path to interpretor)
74. EC2 Meta data
     - From the SSHed cli type- curl http://169.254.169.254/latest/meta-data
75. Auto Sclaing
     - Create Launch Config(as good as creating a Ec2 instance) - Link with ELB and may be autoscaling policies
76. EC2 Placements Groups 
     - Logical Gropu of EC2 instances in a AZ and help avail low latency n/w 
     - Can not span across multi AZ as we want latency to be low
     - Only some types such as - compute optimized, GPU, Memory optimized, Stprage Optimized and homogenous instances are recommended
     - Can not merge placement groups
77. EFS(Elastic Files System)
     - Block based and can be shared across Ec2 inatances, not need to pre provosion and charges are based on memory used
     - Its spread across AZ in a region`
     - Run the mount command in the Ec2 instances and the same EFS is available to all the mounted EC2
     - Good for File Server  can be mounted across Ec2 unlike EBS thats mounted in on Single Ec2
77. EFS(Elastic Files System)
     - Block based and can be shared across Ec2 inatances, not need to pre provosion and charges are based on memory used
     - Its spread across AZ in a region`
     - Run the mount command in the Ec2 instances and the same EFS is available to all the mounted EC2
     - Good for File Server  can be mounted across Ec2 unlike EBS thats mounted in on Single Ec2 
78. Lambda
     - Takes care of Provisioning, event driven compute source, Compute service in responce to HTTP calls, multiple lambda invocations do happen, scaling is taken care, scale up(eg RAM) , Scale out(increase EC2)
     - Compute - Lambda- Create Lambda Function - Blank Function - API Gateway(trigger- SNS, DynamoDB, Cloud Front, Cloudwatch Events, Logs, Code Commit, Alexa Skills lit, Kinesis, Congnito Sync, Alexa Smart Home, AWS IoT ) -
     - To HTTP request invoke different Lambda functions but code is identical,
     - Pricing is per request, Duration(begining for Start to end/terminate , 5 mins is max time duration for a request for Lambda)
     - Instant scaling and one function can trigger another function i.e. X functions from an Event
     - AWS X-Ray allows to debug AWS Lambda, can do things globally i.e. Manage S3
79. The route 53-record set- Alias -  can be S3, ELB, CouldFront
80. EC2 Root volumes can NOT be encrypted by Default we need Bitlocker
81. Snapshots exist on S3 i.e. Snapshot of a volume
82. Sanpshots are incremental so first Snapshot can take more time
83. Volumes of Encrypted Snapshots are Encrypted and Snapshots of Encrypted Volumes are Encrypted
84.  Instance Store backed root volume will be deleted when EC2  is stopped.
85. AMI are stored as per region but can be shared using console or Amazon Ec2 API
86. Roles can be assigned to an EC2 instance also after its been provisioned using CLI or AWS console
87. Roles are UNIVERSAL
88. EFS supports NFSv4
89. Create SnapShots of an EBS volume via CLI - ec2-create-snapshot
90. We can change the permissions to a role, even if that role is already assigned to an existing EC2 instance, and these changes will take effect immediately
91. Sanpshot can be deleted after deregistering from AMI.	 
92. DNS
     - Convert human readable form to an IP address(common IPv4 - 32 bits and IPv6 - 128 bits)
     - Top level domanin name(.com, .uk) - Are maintained by IANA(INternet Assigned Number Authority) 	   
93. Domain Registrars- Registers each domain name in a central db known as WhoIS database
94. SOA(Start Of Authority) - Name of the server that supplied data to the zone, administrator of zone
95. NS(Name Server)record- Helps redirect to Content DNS server which has authoritative DNS records
96. A Records- Fundamental DNS record , A stands for Address, this will translate the domain name to IP address
97. TTL is time to live in the DNS servers so can be lowered to 5 mins(300 seconds) when doing DNS migration
98. CNAMES- Canonical name and can be used to resolve one domain name to another
99. Alias Records- We can map a DNS name with a Target DNS name, C Name can not be used with naked domain name the naked domain name must have A Record or an Alias
100. If there is a change in record sets the Alias record is updated as soon	 
101. CNAME is chargable and not suitable for Naked Domain name whereas Alias can resolve the naked domain name and are not charged   
102. When ELB maintains 2 connections-one with the client and other with the EC2 instance
103. The Maximum size of a VPC is /16 and Minimum is /28
104. Cloud front can have origins- S3, Ec2 http server and http server that on premise as well.   
105. S3 and DynamoDB are designed for multi AZ
106. AMI and instance types are specified while creating a EC2
107. SNS can work for Email JSON, HTTP, Lambda but NOT DynamoDB
108. Loose Coupling=> Asynchronous Integration=> Where immediate response is not neededbut only a request registered info will suffice.
109. An ARN is created as soon a SNS is created
110. Autoscaling group needs AMI, Instance, Configuration Name
111. A VPC reduces the ncessary internet access points, obfuscates the necessary internet access point to a level that untrusted end users cannot access them.
112. Security group i a region can have 100 rules and 500 Security groups in a region per account
113. Route 53 Routing Policies(Global Service like IAM where users are global)
       - Simple - When there is only one web server- Create Record Set- Alias- Alias Target Name- Routing Policy- Simple
       - Weighted - Lets you split the traffic based on Weights you assign(not necessarily same region) (Specify the weight and ID)
       - Latency - Allows to route traffic on Latency(go to lowest Latency)(Give Region and ID)
       - Failover - Detect failed (In Route 53 - create health check for ELB may be using ELB DNS name and may be associate Health Check)
       - Geolocation - Route depending on Geopraphic location(give Location and ID,  Default indicates "Everywhere" else)
114. ELB do cost and Public IPAddress is not Exposed by AWS!
115. Route 53 support MX(Mail Server) records 
116. Route 53 Support Sone Apex records(naked domain names)
117. There is 50 domain names available by default, however it is a soft limit and can be raised by contacting AWS support. 
118. A PTR is a reverse DNS Record(converts an IP to DNS name)
119. Cloud Watch gives System Wide Visibility for Monitoring Resourses, Application Performance, Operational Health.
120. Hybrid Deployment extends and existing on-premise into cloud
121. Restricting Data Access S3-Pre Signed URL, S3 ACl, Buckey Policy
122. ELB is configured with Listeners to accept traffic.
123. Multi AZ is supported in MySQL, Microsoft SQL, Oracle, PostgresSQL, Aurora
124. AWS Beanstalk automatically handles the deployment details
126. RDS - Create instance - MySQL - Select the multi AZ , instance class, storage type, instance identifier, username, passcode, security group
        - In security group make sure that the inbound rule in db securithy group to SQL Port 3306 has source defined to our Security             Group
        - End point of DB is used to connect to DB(PHP, Nodejs, java)
        - When deleting the RDS, an option to Take a Final Snapshots appears
127. Backups
       - Automated Backups- Allow recover Database to any point in time in the retention period, 1-35 days, take a full daily snapshots          and store transaction logs, recovery leads to choosing the most recent Backup and then applying the transaction log                      leading to second within.
       - Automated backups are enabled by default and the size of the backup storage is the size of RDS, IO may get slow while backup is          going on so take backup in a defined window. 
       - Snapshots are done manually and stored even of the the RDS is deleted
       - After a restore from both Snapshot and Automatic backup a new DB is created and end is new as well, Multi AZ etc.
       - Encryption
         - Encryption at rest is supported in MySQL, Oracle, SQL, Postgres and Maria using AWS KMS
         - Encrypting an existong DB is not supported if need to this do a migration or restore 
         - Action on a RDS->
           - Take Snapshot(Migrate to say Aurora, copy to another region, share, delete, restore and increase DB instance are some actions tha can be performed on a Snapshot), 
           - Migrate
           - Point in Time
           - Read Replica
128. Multi AZ in RDS
       - Exact copy goes to another Zone so that in even of Planned Maintainance , DB instance failure or AZ failure the RDS will                failover to standby.
       - Multi AZ is for Disaster recovery not for performance optimization, use Read Replicas for that!
       - Microsoft SQL server seems not having multi - AZ(only SQL, Oracle, MySQL, PostGres, MariaDB and Aurora anyways store copies)
129. Read Replica
       - Database can have upto 5 replicas
       - Read Replica is read only copy of production database. 
       - Supported- MySQL, PostGres, MariaDB	
       - Read Replicas must have automated backups turned on	
       - Read Replica of Read Replica have more latency
       - Each Read Replica has own End Point
       - Read Replica have no Multi AZ they are in same AZ as that of the database
       - Read Replicas can be promoted 
       - Read Replicas can be promoted to become own databases and the replication is broken
       - Read Replica can be in other region only for MariaDb and MySQL and not for PostgresSQL
130. Scaling RDS is a task but its a Push action in a DynamoDB w/o any downtime
131. DynamoDB - Fast and flexible data model
       - Stored Across 3 geographically distinct data centers(different facility)
       - Stored in SSD
       - Eventual Consistent Reads
         - Across all copoies is reached after a second(best for Read perfornamce)
       - Strongly Consistent reads
         - Returns a result that reflects all writes that received a success response prior to read
132. DynamoDB has provisioned throughput capacity, expensive for Write and cheap for Reads
133. Create DynamoDB table - name - primary key(String, number, binary)- provisioned capacity- ARN is created, We can Reserve Capacity, We get a flexible data model(dynamically add columns)
134. DynamoDB capacity can be scaled on the Run.
135. While scaling is happening there is not going to any downtime.
136. REDSHIFT- Ware housing  service
       - Online Analytics Processing(OLAP is an example)
       - Single Node(160Gb, small business)
       - Multi-Node(big business)
         - Leader Node(client or receives queries)
         - Compute Node(perform queries and do computing upto 128 compute nodes)
         - REDSHIFT stores data as columns and stored sequential so a better I/O
         - Advanced data compresion as column is of same data type
         - AWS REDSHIFT will analyse data and apply appropriate compression
         - Multi Node has Massively Prallel Processing(MPP)
         - Price - Compute Node Hours, Backup and Data Transfer
         - Encryption at Transit and Rest are possible
         - Available in One AZ only
         - Can restore to a NEW AZ if there is Outage
137. Elasticache
     - Easy to deploy and scale by allowing to retive info from fast, in memory, managed Caches, improves I/O intensive queries
     - Memcached
       - Existing Memcached Environmants will work seemlessly with AWS Memcached
     - REDIS
       - Key Value Store and supports Lists and Sets
       - Master Slave replication and Multi AZ so as to achieve Multi AZ redundency
       - REDIS has Multi AZ but not Memcached
138. Aurora
     - Aurora can not be installed else where except its a service on the AWS cloud only
       - MySQL compatible
       - Upto 5 times performance than SQL
       - Cost is lesser than Oracle
       - Scaling
          - 10 Gb is initial and scales to 64Tb when Autoscaling
          - Scaling do have a downtime but its quick in Aurora
          - 2 copies of data is contained in each AZ and minimum is 3 AZ i.e. min 6 copies
          - handles transparently the failure of 2 copies for Write availability and 3 copies failure for Read Consistency
          - Auto healing
139. Aurora Replica
     - Aurora Replica(upto 15, failover occurs)
     - MySQL Replica(upto 5, failover wont occur)
     - Available in some region(US east) - Specify DB instance class - Multi AZ - DB indentifier - credentials - failover -                    Priority(tier0 to tier15)
     - Instance Actions - Create Aurora Replica - Reader - Replication Role
     - Cluster Endpoints will failover to next good End Point(Instances)
140. Multi AZ has a failover 
142. When replicating data from your primary RDS instance to your secondary RDS instance, what is the charge? Its Free		
143. When you add a rule to an RDS security group you do not need to specify a port number or protocol? FALSE
144. If you are using Amazon RDS Provisioned IOPS storage with MySQL and Oracle database engines what is the maximum size RDS volume you      can have by default? - 6Tb
145. What happens to the I/O operations while you take a database snapshot - Suspended even of the Read Replica is there
146. In RDS when using multiple availability zones, can you use the secondary database as an independent read node? - NO
147. By default, the maximum provisioned IOPS capacity on an Oracle and MySQL RDS instance (using provisioned IOPS) is 30,000 IOPS.	 	

148. VPC can span AZ not Regions, a logically isolated section in AWS cloud, have complete control of the n/w env.
        - Hardware Virtual Private Network is connection between corporate data center and VPC = Hybrid Cloud 
        
149.   For a VPC the private n/w ranges are
          - 10.0.0.0 to 10.255.255.255 (10/8)
          - 172.16.0.0 to 172.31.255.255(17.16/12)
          - 192.168.0.0 to 192.168.255.255(192.168/16)(Max size in AWS VPC)
          - One Subnet is span in ONE AZ
          - SG and ACL and Route Table can Span Acoss AZ
          - One Internet Gateway per VPC
          - SG are stateful and ACL are stateless
          -  Default VPC is created by default in Every region so that EC2 are provisioned easily
             - All Subnets inside have internet access
             - Each EC2 instance has public and private IP address
             - Delete of Default VPC can be undone by contacting AWS
          - VPCs in different regions can be connected via direct network route using private ip address(VPC Peering)
             - Instances behave as if they are in same private network
             - Peering can be done in same as welll as different AWS accounts
             - Peering is a Star configuration so NOT TRANSITIVE
151. VPC - Your VPC - Name and CIDR(between /16 and /28) and Tenancy - Creates Route Table, ACL and SG but no new Subnet(SG and ACl can span multiple AZ but not Subnet)
       - Reserved are 3 by default and 2 can not be used anyways
       - Internet gateway - detached by default - Attach to VPC(only one IGW per VPC as they are highly durable)
       - Instead of using default Route Table we create a new route table and set Destination(0.0.0.0/0) and target(IGW) - Subnets Associations(internet access to subnets)
       - For a subnet we need to turn 'Turn on auto assign public ip' so that EC2  instances get public ip when provisioned
       - Start Instance	- Network (Subnet-specify own subnet) - AUto Assign public ip address
       - Subnets can communicate with each other by default

152. For private subnet we can configure SSH, MySQL and ICMP(for pings) with Source as the public subnet address range , note private ip address of private subnet so we can ping and ssh via public EC2

153. NAT(Network Address Translator)
     - NAT Instance - EC2 - create - choose NAT - Give VPC and public subnet - SG is needed while for NAT Gateway its not            needed to be added by us - Action - Disable - Change Source/Destination check - Attach to Default Route Table                  with Source(0.0.0.0/0) and Target(NAT instance). 
     - Amount of Traffic depends on the instance size and type
     - Behind the SG
     - NAT Gateway 
       - Scale automatically 
       - VPC - create a NAT Gateway - Public subnet - Allocate Elastic IP - include in Route Table (default in our case)
       - SG are taken care automatically in NAT Gateways
       - No Security Patches required
       - Highly Available
       - Redundency
       - 10 GBps vs Instance depends on instance type
       - Slightly Expensive
       
154. High availability can be created using Autoscaling groups, multiple subnets in multiple AZ and a script to automate the        failover       
155. ACL vs SG
       - SG works on Instance level, ACL works on Subnet level 
       - SG supports Allow rules, ACL has both Allow and Deny rules
       - SG are Stateful, ACL in not stateless
       - Numerical Order in ACL
       - ACL applies to instances in a subnet automatically
       - Deault ACL has in out traffic is allowed
       - Custom ACL has all denied
       - One Subnet will have only One ACL
       - Ephimeral ports need to be added to custom ACL for public facinig subnets
       - Lower Number rule takes effect in ACL
       - Each Subnet must have a ACL		  
       - Block particular IP address using ACL not SG    

156. When we do a high availability app using ELB, its a good to have two public subnets and two private subnets also in            different AZ because AZ can go down.

157. NATs vs Bastions
     - NATs are used to provide internet access to an instance in private subnet
     - Bastion are used to administer the instanses in private subnets via SSH or RDP

158. VPC FLOW LOGS
     - VPC - ACTIONS - Create Flow Log - create logs - log the traffic data within the VPC

159. VPC and Subnets
     - 5 VPC are allowed by default in each AWS Region
     - 200 Subnets per VPC
     - 5 NAT Gateways per AZ

160. SQS
     - Distributed Queue System that can be consumed by other component
     - SQS is a PULL based system
     - Example - S3->Lambda->SQS->EC2
     - Even when the EC2 fails the message is still in SQS and can be comsumed by another SQS
     - The message goes to timeout when its queried, size is 256Kb any text format and can be retrived programatically by SQS        API
     - Types
       - Standard Queue
         - Unlimited Transactions per second
         - One or more messages may reach out of order
         - Best effort ordering but not guaranteed
       - FIFO Queue
         - 300 transactions per second
         - Order is guaranteed
         - Message is delivered once and remains until the consumer deletes it and so no duplicates
       Messages can be kep in queue from 1 minute to 14 days, 4 days is default
     -Visibility Timeout- the time for which the message is invisible in the queue before it is visible again so if the             timeout occurs before the processing the same message can be taken by another consumer i.e. same message might be             delivered twice. 
     - Max visibility timeout is 12 hours
     - Long polling is way in which EC2 can query SQS for messages
     - Message Oriented API

161. SWF (Simple Workflow Service) 
     - Cordinate work across distribution application components.
     - Execute via code or human action or scripts
     - Retention upto 1 year
     - Task oriented
     - Task is assigned only once, keeps track of tasks and events
     - SWF Actors
       - Starters- Website, App
       - Deciders - control the flow of activity
       - Workers - Carry activity task
     
162. SNS(Simple Notification Service)
     - Publish messages from app and deliver them to subscribers
     - Lambda can be associated with SNS
     - Push messaging System
     - Multiple recipients, formatted copies, stored in Multi AZ
     - Create Topic- Create Subscription- Protocol(HTTP, HTTPS,Email, Email JSON, SQS, Application, Lambda)- Endpoint-                conformation
     - Useful in Autoscaling 
     - No polling- Push instantly 
     - Delivery Over Multiple protocol
     
163. Elastic Transcoder
     - Convert media file into other formats and charges on the minutes encoded and resolution
     - Example- Upload a file to S3- invoke a lambda function -  Invokes Transcoder - Save transcoded file to S3
     
164. API Gateway
     - Publish, maintain and moniter API at any scale
     - Example - API Gateway - Triggers Lambda or functions in EC2
     - API Caching
       - Cache the endpoint response, API gateway caches the response for a TTL and gives better performance
       - Low cost and efficient
       - Scales but throttle to prevent attacks
       - Can be configured in cloud watch to see logs
       - Cross Origin Resource Sharing needs to be enabled in the API Gateway
       
165. Kinesis
     - Streaming Data- Data that is generated continously and sent in small sizes
     - Kinesis helps load and analyse streaming data
     - Three kinesis services
       - Kinesis Streams
         - Data producers - Kinesis Streams - Stores for 24 hours default and extedn upto 7days
         - Shards are used to store - Consumers like EC2 - then S3 etc
         - The capacity of the Stream is the sum of capacities of all the shards
       - Kinesis Firehose
         - Data Producers - Streams but no shrads - Data is Analysed or Send to S3 or Redshift for example and not stored in              Stream(no need to manage Shards and retention)  
       - Kinesis Analytics
         - Helps run SQL type queries on Kinesis(Kinesis Streams or Firehose) Data and save to S3, Redshift or Elastic Search            Cluster

166. SWF(ensures task is done once only) is Task Oriented, SQS and SNS are Message Oriented

167. SNS subscribers - HTTP, HTTPS, Email JSON, Email, SQS, Application and Lambda

168. SES - Simple Email Service

169. AWS Resource Name is created when a SNS Topic is created

170. SWF Domain - Collection of related workflows

171. S3 url format - https://s3-region.amazonaws.com/bucket-name

172. 11 Regions currently, China has one AZ and mostly 3 AZs

173. Compliance -
     - SOC 1/ SSAE 16, ISAE 3402
     - SOC 2,
     - SOC 3
     - FISMA, DIACAP, FedRAMP
     - PCI DSS Level 1
     - ISO 27001
     - ISO 9001
     - ITAR
     - FIPS 140-2
     
174. Security 
     - Shared Security Model
     - AWS is responsible for facility
     - AWS is responsible for the security configuration of its managed services like DynamoDB, RDS, Redshift, Elastic map            reduce, Amazon Workspaces
     - AWS S3, EC2, VPC etc are under user control
     - Managed services user needs to have account managenent and user access, MFA and user activity logging using                    CloudTrail(could Watch beig Monitering)
     - Storage Decommissioning includes - degaussed and physically destroying the storage device
     
175. Network Monitering and Protection
     - DDoS,
     - Man in the middle attacks
     - Ip spoofing - Host based firewall, ip can be own
     - Port Scanning - request advance permission for Scans of own instance
     - Packet Sniffing by other tenants
     
176. Credentials 
     - Passwords-root a/c or IAM users need to login to aws console
     - MFA- root or IAM user need to login to aws console.
     - Access keys- digital sign for programatical access
     - Key Pairs - to ssh EC2 or Cloud front signed urls
     - X.509 - Digitally Signed SOAP request to AWS APIs or HTTPS SSL server certification
     - AWS Trusted Advisor- helps close common security gaps, save money improve system performance like- 
       not using IAM, not using MFA, S3 being open to public, not having CloudTrail

177. Instance Isolation - 
     - Different instances running on the same physical machine are seperated by Xen hyperisor and a firewall
     - Each instance has access to virtual hard disk and guest menory is used in other processes only after memory scrubbing
     - In a SG all ingress traffic is denied whereas outgoing is allowed
     
178. Guest Operating System-
     - User has the root pernission, encrytion of data is a good practice(Encryption is available on EC2's more powerful              instances eg.- M3, C3, R3, G2)
     
179. SSL termination of Load Balancer is supported (i.e. data wont be encrypted between the ELB and the web server)and allows      to know the ip address of any client that connects in ELB
     
179. Direct Connect - Helps bypass the internet service providers usinf cross connect, have a Rackspace and connect to an AWS      direct connect equipment and also has virtual interfaces that help allow the access to public and private ip space

180. Risk and Compliance
     - Stratergic risk management is 2 times in a year
     - AWS security scans are for underlying infra

181. Storage Options-
     - Storage Gateway
       - Gateway cached and Gateway Stored volumes that can be mounted to iSCSI on the on premise applications
       - Gateway Cached gives low latency access to frequently accessed data(32 Tb)
       - Gateway Storages all the primary data while doing the backup async(1 Tb)
       - Snapshot storage, Volume, Data Transfer, number of Gateways are cost deciding factors for Storage Gateways
       
182. Elasticity
     - Proactive(Salaray day)
     - Proactive Event Scaling(Black friday sales)
     - Auto Scaling(based on demand)
     
183. Web Tier(allow 80 -http 443-https), Application Server(SSH port 22), DB Layer(only Applocation layer has access)  

184. SQL Server's atorage can nit be increased and Auto Backup is enabled by default

185. To run a DB on EC2 instance - EBS is suitble

186. EBS snapshots are accessable via APIs and AWS console, CLI

187. A Policy is a document that provides a formal statement of one or more permissions

188. In a default VPC, all Amazon EC2 instances are assigned 2 IP addresses at launch, public and private ip address

189. If an Amazon EBS volume is the root device of an instance, I can not detach it without stopping the instance
     I can not move a reserved instance from one region to another, In RDS the maximum size for a Microsoft SQL Server      DB      Instance with SQL Server Express edition is 10Gb per DB
     
190. I can "force" a failover for any RDS instance that has Multi-AZ configured, Reserved instances are available for multi-AZ      deployments, MySQL installations default to port number 3306

191. If an Amazon EBS volume is an additional partition (ie not the root volume) , I can detach it without stopping the            instance but it will take some time

192. What are the four levels of AWS premium support - Basic, Deleloper, Business, Enterprise

193. AZ - distinct locations within Region that are isolated from fail overs

194. Individual instances are provisioned in AZ

195. How many copies of my data does RDS - Aurora store by default - 6

196. 1 hr is the maximum response time for a Business Level Premium Support Case

197. Design Principles(5 pillars)
     - Security
       - Apply security at all layers(Subnets, ACL, SG, Patching at times)
       - Tracebility
       - Customer secures in the could(IAM config, OS config, N/w config, Firewall config, Encryption)
       - AWS takes care of Security in the cloud(Regions, AZ, Edge Locations)
       - Data Protection- classification-> shall the data be public, private, restricted
         - Encryption cam be done using S3, RDS, ELB, EBS
       - Privilage Management
         - ACL, Passcode management -rotation, strength, Roles, Groups, IAM, MFA
       - Infra Protection
         - VPC, Host-N/W boundary likw Bastions or Jump Boxes
       - Detective controls
         - CloudTrail(Reginal Service), ClouldWatch, AWS Config
         - AWS Logs need to captured and analysed
     - Reliability
       - Dynamically have resources, Recovery from Service/infra failures
       - Scaling horizontally- distrubuting system into small resources         
       - Foundations
         - Comm links between HQ and datacenter
         - N/W topology
       - Change Management
         - CloudWatch and Autoscaling that react to change in Environment, ClouDTrail
       - Failure Management
         - Cloud Formation?
     - Performance Efficiency
       - Compute
         - CPU, Memory, Auto scaling
       - Storage
         - Block based, Object based, Throughput, Random, Sequential, Availability
       - DB
         - RDS, DunanoDB, Redshift
       - Space time trade off
         - RDS Read Replicas, Elasicache, CloudFront, Direct Connect
     - Cost Optimization
       - Lowest price and still achieve the business goal
       - Transparent Attribute expenditure
       - AWS Blog, Trusted Advisor can help
       - EC2 reserved instances can help optimize costs whereas SNS and CloudWatch can help in expenditure awareness
     - Operational Excellence
       - AWS Config helps track and respond to changes in your AWS environment
       - Tagging for easy identification
 198. Kinesis -Big Data consumer and large social media stream, Redshift for BI and Elastic Map Redice for BigData                   processing
      - Instance Store volumes can not be detached and attach to another instance whereas EBS(Can be stopped) can be
 199. OpsWorks 
      - Orchestration service that uses Chef that has a receipe/cookBooks to maintain a consistent state
 200. curl or get http://169.254.169.254/latest/meta-data gives META DATA like public ip address
