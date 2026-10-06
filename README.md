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
