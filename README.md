# AWS PHP Application Migration to Graviton Machine

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Migration Steps](#migration-steps)
  - [1. PHP-based Web Application on AMD to Graviton](#1-php-based-web-application-on-amd-to-graviton)
  - [2. Take a Snapshot or Backup of the Existing Environment](#2-take-a-snapshot-or-backup-of-the-existing-environment)
  - [3. Create the Graviton Instance](#3-create-the-graviton-instance)
  - [4. Attach the Snapshot to the Graviton Instance](#4-attach-the-snapshot-to-the-graviton-instance)
  - [5. Mount the Volume to /mnt/php-app-backup](#5-mount-the-volume-to-mntphp-app-backup)
  - [6. Verify the Mount](#6-verify-the-mount)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [Created By](#created-by)

---

## Introduction
This document provides a step-by-step guide to migrating a PHP application running on an AMD instance to an AWS Graviton instance. The purpose of the migration is to improve performance and reduce costs by leveraging the ARM-based architecture of Graviton instances.

---

## Prerequisites
Before starting the migration, ensure the following:
- You have an AWS account with sufficient privileges to create and manage EC2 instances and volumes.
- Basic understanding of AWS EC2, Apache, and PHP.
- A running PHP application on an AMD-based instance that you intend to migrate.
  
---

## Installation

### 1. **Create a Graviton Instance**
   - Launch a new AWS EC2 instance using a Graviton-compatible Amazon Machine Image (AMI).
   - Select an instance type that suits your PHP application's performance requirements.

### 2. **Install PHP**
   - Install PHP on the newly created Graviton instance by running:
     ```bash
     sudo apt update
     sudo apt install php libapache2-mod-php
     ```

### 3. **Install Apache Web Server**
   - Install Apache and start the service:
     ```bash
     sudo apt install apache2
     sudo systemctl start apache2
     sudo systemctl enable apache2
     ```
---

## Migration Steps

### 1. **PHP-based Web Application on AMD to Graviton**
   - Identify the PHP application currently running on the AMD instance. Ensure compatibility with Graviton by checking software and configurations.
   - Stop the application temporarily to prepare for the migration.

### 2. **Take a Snapshot or Backup of the Existing Environment**
   - From the AWS Management Console:
     - Go to the EC2 dashboard.
     - Select your running AMD-based instance.
     - Click on "Actions" > "Image and templates" > "Create image" to create a backup of your environment.

### 3. **Create the Graviton Instance**
   - Launch a new AWS Graviton EC2 instance:
     - Select an appropriate AMI and instance type (e.g., t4g.micro).
     - Configure the instance details and security groups.

### 4. **Attach the Snapshot to the Graviton Instance**
   - After creating the snapshot, attach it as a volume to the Graviton instance:
     - Go to the EC2 dashboard > "Snapshots".
     - Select the snapshot and click on "Actions" > "Create Volume".
     - Attach the volume to the Graviton instance.

### 5. **Mount the Volume to /mnt/php-app-backup**
   - SSH into the Graviton instance and mount the volume:
     ```bash
     sudo mkdir /mnt/php-app-backup
     sudo mount /dev/nvme3n1p1 /mnt/php-app-backup
     ```

### 6. **Verify the Mount**
   - Check if the volume is mounted correctly:
     ```bash
     df -h
     ls /mnt/php-app-backup
     ```
   - Ensure that the mounted volume contains all the necessary files from the previous environment.

---

## Screenshots
Here are some key screenshots for each step:

1. **Graviton Instance Creation:**
   ![Graviton Instance](https://github.com/TKSDE/AWS-PHP-Migration-Graviton/blob/main/Screenshots/1.png)

2. **Apache Installation:**
   ![Apache Installed](https://github.com/TKSDE/AWS-PHP-Migration-Graviton/blob/main/Screenshots/2.png)

3. **Application Running on Graviton:**
   ![PHP Application Running](https://github.com/TKSDE/AWS-PHP-Migration-Graviton/blob/main/Screenshots/3.png)

---

## Contributing
Contributions are welcome! If you have suggestions for improvements, feel free to fork the repository and submit a pull request.

---

## Created By
This migration guide is created by **Tek Chand Kumar Sharma**.

