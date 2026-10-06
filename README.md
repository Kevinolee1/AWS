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

![Database Engine Selection](images/05-database-engine-selection.png)

**Figure 5 – Database Engine Selection:** On the **Create database** page, I reviewed the available database engine options, including Aurora, MySQL, PostgreSQL, MariaDB, Microsoft SQL Server, Oracle, and IBM Db2.

For this Cloud DBA lab, I proceeded with **PostgreSQL** as the relational database engine. PostgreSQL will be used to practice database administration tasks such as database creation, user and role management, permissions, SQL queries, backups, monitoring, and troubleshooting.
