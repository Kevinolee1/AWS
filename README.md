# AWS

## Step 1 – Select an AWS Account Plan

![AWS Account Plan Selection](https://github.com/Kevinolee1/AWS/blob/6e3538355b10623600e7d9bf293906ff8da7718f/Screenshot%202026-10-05%20105542.png)

**Figure 1 – AWS Account Plan Selection:** I started the AWS Cloud DBA lab by reviewing the available AWS account plans. For this hands-on learning environment, I selected the **Free plan** to build and configure AWS resources while using the available credits and free usage for eligible services.

### Objective
The goal was to create a controlled AWS lab environment where I could gain hands-on experience deploying, securing, connecting to, and administering a PostgreSQL database using Amazon RDS.

**Skills demonstrated:** AWS Cloud, AWS Account Setup, Cloud Lab Planning, Cost Awareness

## Step 2 – Access the AWS Management Console

![AWS Management Console](https://github.com/Kevinolee1/AWS/blob/a2e6d0009eee6460a9e8bd55e076e7507bbed0de/Screenshot%202026-10-05%20111945.png)

**Figure 2 – AWS Management Console:** After setting up the AWS account, I signed in to the AWS Management Console. From the console, I can access and manage AWS services such as Amazon RDS, EC2, IAM, S3, and CloudWatch.

I verified that I was working in the **US East (Ohio) – us-east-2** AWS Region before beginning the Amazon RDS database deployment. Keeping the resources in the same AWS Region helps maintain a consistent configuration throughout the lab.

## Step 3 – Navigate to Amazon RDS

![Amazon RDS Search](https://github.com/Kevinolee1/AWS/blob/c4f516f649ad7838915710bcf98655e7e69fac57/Screenshot%202026-10-05%20112553.png)

**Figure 3 – Locating Amazon RDS:** From the AWS Management Console, I searched for **RDS** and selected **Aurora and RDS**, AWS's managed relational database service.

This opened the Amazon RDS console, where I could begin creating and configuring the PostgreSQL database instance for the lab.

## Step 4 – Open the Amazon RDS Dashboard

![Amazon RDS Dashboard](https://github.com/Kevinolee1/AWS/blob/26a8da53e46930d565b92e93f4cab67b77f309aa/Screenshot%202026-10-05%20112724.png)

**Figure 4 – Amazon RDS Dashboard:** After opening **Aurora and RDS**, I arrived at the Amazon RDS dashboard in the **US East (Ohio) – us-east-2** Region.

I selected **Create with full configuration** so I could manually configure the database engine, instance settings, storage, networking, security, monitoring, and backup options for the PostgreSQL RDS instance.

## Step 5 – Select the Database Engine

![Database Engine Selection](https://github.com/Kevinolee1/AWS/blob/a0b47edf279914a062ce0a6ac053fe6abbe09af4/Screenshot%202026-10-05%20112850.png)

**Figure 5 – Database Engine Selection:** On the **Create database** page, I reviewed the available database engine options, including Aurora, MySQL, PostgreSQL, MariaDB, Microsoft SQL Server, Oracle, and IBM Db2.

For this Cloud DBA lab, I proceeded with **PostgreSQL** as the relational database engine. PostgreSQL will be used to practice database administration tasks such as database creation, user and role management, permissions, SQL queries, backups, monitoring, and troubleshooting.

## Step 6 – Configure the RDS Instance

![RDS Instance Configuration](https://github.com/Kevinolee1/AWS/blob/620b238a4de62a1edc9fe43ddbc4545ed2700943/Screenshot%202026-10-05%20113059.png)

**Figure 6 – RDS Instance Configuration:** I selected the database creation settings and configured the PostgreSQL RDS instance for the lab environment.

I selected the **Free tier db.t4g.micro** instance class to keep the lab lightweight and cost-conscious. I also used **postgres** as the master username. The DB instance identifier would be configured as **cloud-dba-lab** to clearly identify the database resource throughout the project.

## Step 7 – Configure PostgreSQL Settings

![PostgreSQL Database Settings](https://github.com/Kevinolee1/AWS/blob/8b54ab13ad9c6e16c53ac00c51ed6647d3559c6b/Screenshot%202026-10-05%20113423.png)

**Figure 7 – PostgreSQL Database Settings:** I configured the database to use **PostgreSQL 18.3-R2** and set the DB instance identifier to **cloud-dba-lab**.

I kept **postgres** as the master username for database administration. I also left **RDS Extended Support** disabled because it was not required for this lab environment.

## Step 8 – Configure Instance Class and Storage

![RDS Instance Class and Storage](https://github.com/Kevinolee1/AWS/blob/96df1a9975e901a605e21c47ec6f7961c7370229/Screenshot%202026-10-05%20113619.png)

**Figure 8 – Instance Class and Storage:** I configured the RDS instance to use the **db.t4g.micro** burstable instance class with **2 vCPUs and 1 GiB of RAM**, which provided sufficient resources for this lab environment.

For storage, I selected **General Purpose SSD (gp2)** and allocated **20 GiB** of storage. This configuration keeps the environment lightweight while providing enough capacity to practice PostgreSQL database administration tasks.

## Step 9 – Configure Network Connectivity

![RDS Network Connectivity](https://github.com/Kevinolee1/AWS/blob/1d762cdcf61f5dafc580ff15ca5ddeab25345253/Screenshot%202026-10-05%20113810.png)

**Figure 9 – RDS Network Connectivity:** I configured the network settings for the PostgreSQL RDS instance. I chose not to connect the database directly to an EC2 compute resource and selected the **Default VPC** and **default DB subnet group**.

The screenshot shows **Public access** initially set to **No**. Because I planned to connect to the database from my local Windows computer for this lab, I later changed **Public access to Yes** and restricted PostgreSQL access through the security group rather than exposing port 5432 to all IP addresses.

## Step 10 – Configure the VPC Security Group

![RDS VPC Security Configuration](https://github.com/Kevinolee1/AWS/blob/5742174ced92a35cb8b79454406749c006cdd447/Screenshot%202026-10-05%20113951.png)

**Figure 10 – VPC Security Configuration:** I reviewed the VPC security group settings that control network access to the PostgreSQL RDS instance.

At this stage, the **default VPC security group** was selected. I left the **Availability Zone** set to **No preference**, did not enable **RDS Proxy**, and kept the default AWS RDS certificate authority for secure database connections.

Later in the configuration, I created a dedicated security group for the lab and restricted inbound PostgreSQL traffic on **TCP port 5432** to my authorized public IP address.

## Step 11 – Create a Dedicated VPC Security Group

![Create RDS Security Group](https://github.com/Kevinolee1/AWS/blob/daa82e16801042f67de7ede5eafad5adf52006d1/Screenshot%202026-10-05%20114325.png)

**Figure 11 – Creating the RDS Security Group:** I selected **Create new** under the VPC security group settings and created a dedicated security group named `cloud-dba-lab-sg`.

Using a separate security group allows me to control which network traffic can reach the PostgreSQL RDS instance instead of relying on the default security group.

I left the **Availability Zone** set to **No preference**, kept **RDS Proxy** disabled, and retained the default AWS certificate authority for secure connections.

## Step 12 – Configure Database Monitoring

![Configure RDS Monitoring](https://github.com/Kevinolee1/AWS/blob/165360a925cc1e034e151a9500a84e0be4290e79/Screenshot%202026-10-06%20053223.png)

**Figure 12 – Configuring RDS Monitoring:** I selected **Database Insights – Standard** and enabled detailed database and per-query metrics with the **7-day free retention period**.

For encryption, I kept the default AWS-managed RDS KMS key (`aws/rds`). This provides encryption support for the database while keeping the lab configuration simple and cost-conscious.

These settings provide database performance visibility that can be used later to monitor activity, troubleshoot performance issues, and analyze database behavior.

## Step 13 – Review Additional Monitoring Settings

![Additional RDS Monitoring Settings](https://github.com/Kevinolee1/AWS/blob/26b3bb0aed317e4b6fbcfe7d074b4b7cab245a30/Screenshot%202026-10-05%20114852.png)

**Figure 13 – Reviewing Additional Monitoring Settings:** I reviewed the additional monitoring options available for the PostgreSQL RDS instance, including Enhanced Monitoring, CloudWatch log exports, and Amazon DevOps Guru.

For this lab, I kept **Enhanced Monitoring**, **CloudWatch log exports**, and **DevOps Guru** disabled to maintain a simple, cost-conscious configuration.

These features can be enabled later if more detailed operating system metrics, PostgreSQL logs, or automated performance analysis are required.

## Step 14 – Configure Database Options and Encryption

![RDS Database Options and Encryption](https://github.com/Kevinolee1/AWS/blob/03134c7ec7dfb0964c09d2d1791e66788a87f725/Screenshot%202026-10-06%20053307.png)

**Figure 14 – Configuring Database Options and Encryption:** I reviewed the additional database configuration settings for the PostgreSQL RDS instance.

I kept the default PostgreSQL 18 parameter and option groups and enabled **encryption at rest** using the AWS-managed RDS KMS key (`aws/rds`).

I left the **Initial database name** blank because the database for the lab would be created manually after connecting to the RDS instance with PostgreSQL.

## Step 15 – Set the Initial Database Name

![Set Initial Database Name](https://github.com/Kevinolee1/AWS/blob/26526993ce285591a8044bd93c0110e7a504f301/Screenshot%202026-10-05%20115247.png)

**Figure 15 – Setting the Initial Database Name:** I configured the **Initial database name** as `clouddbalab`.

This allows Amazon RDS to automatically create an initial PostgreSQL database when the RDS instance is provisioned.

I kept the default PostgreSQL 18 parameter and option groups and maintained **encryption at rest** using the AWS-managed RDS KMS key (`aws/rds`).

## Step 16 – Configure Automated Backups and Maintenance

![Configure RDS Backups and Maintenance](https://github.com/Kevinolee1/AWS/blob/47d97be2226217804150b79f6a4039f6f54d6677/Screenshot%202026-10-05%20115314.png)

**Figure 16 – Configuring Automated Backups and Maintenance:** I enabled **automated backups** for the PostgreSQL RDS instance and configured a **1-day backup retention period**.

I left the backup window set to **No preference**, enabled **Copy tags to snapshots**, and left cross-Region backup replication disabled for this lab.

I also enabled **Auto minor version upgrade** so Amazon RDS can automatically apply supported PostgreSQL minor version updates during the maintenance process.

## Step 17 – Configure Backup Retention and Maintenance

![Configure RDS Backup Retention and Maintenance](https://github.com/Kevinolee1/AWS/blob/f2321ff1efd0578016b47531dcbe82f35b347e4a/Screenshot%202026-10-05%20115541.png)

**Figure 17 – Configuring Backup Retention and Maintenance:** I configured the automated backup retention period for **7 days**, providing additional recovery points for the PostgreSQL database.

I left the **Backup window** and **Maintenance window** set to **No preference**, enabled **Copy tags to snapshots**, and kept cross-Region backup replication disabled.

I also enabled **Auto minor version upgrade** so Amazon RDS can automatically apply supported PostgreSQL minor version updates. **Deletion protection** remained disabled for this lab so the RDS instance can be removed after testing to avoid unnecessary AWS charges.

## Step 18 – Final Review and Create the Database

![Create PostgreSQL RDS Database](https://github.com/Kevinolee1/AWS/blob/3d02bcc5fb29bad752a3278d0b67c16d63eb58db/Screenshot%202026-10-05%20120204.png)

**Figure 18 – Final Review and Database Creation:** I completed the final review of the PostgreSQL RDS configuration before provisioning the database.

I kept **Auto minor version upgrade** enabled, left the **Maintenance window** set to **No preference**, and kept **Deletion protection** disabled because this is a temporary lab environment.

After verifying the configuration, I selected **Create database** to begin provisioning the PostgreSQL RDS instance in AWS.

## Step 19 – Resolve the Backup Retention Configuration Error

![RDS Backup Retention Error](https://github.com/Kevinolee1/AWS/blob/aa46e7fd7ffd799dc823ed42b2b38591fbc45731/Screenshot%202026-10-05%20120454.png)

**Figure 19 – Troubleshooting Database Creation:** My first attempt to create the `cloud-dba-lab` RDS instance failed because the configured backup retention period exceeded the limit available under my AWS Free plan.

AWS returned the message: **“The specified backup retention period exceeds the maximum available to free tier customers.”**

I used the error message to identify the configuration issue and returned to the backup settings to reduce the retention period to a supported value before attempting to create the database again.

This demonstrates troubleshooting an RDS provisioning failure by reviewing the AWS error, identifying the unsupported configuration, and correcting the database settings.

## Step 20 – Adjust Backup Retention for the Free Plan

![RDS Backup Configuration](images/20-backup-retention-corrected.png)

**Figure 20 – Correcting the Backup Configuration:** After reviewing the database creation error, I returned to the RDS backup settings and changed the **backup retention period to 1 day**.

Automated backups remained enabled, allowing Amazon RDS to create point-in-time backups while keeping the configuration within the limits of the AWS Free plan.

The backup window was left at **No preference**, allowing AWS to determine when the automated backup process runs.

With the unsupported retention setting corrected, I was ready to retry provisioning the `cloud-dba-lab` PostgreSQL database.

