# AWS PHP Application Migration to Graviton Machine

## Table of Contents
- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Migration Steps](#migration-steps)
  - [1. PHP-based Web Application on AMD to Graviton](#1-php-basScreenshotsed-web-application-on-amd-to-graviton)
  - [2. Take a Snapshot or Backup of the Existing Environment](#2-take-a-snapshot-or-backup-of-the-existing-environment)
  - [3. Create the Graviton Instance](#3-create-the-graviton-instance)
  - [4. Attach the Snapshot to the Graviton Instance](#4-attach-the-snapshot-to-the-graviton-instance)
  - [5. Step-by-Step Guide: Mount the Volume to /mnt/php-app-backup](#5-step-by-step-guide-mount-the-volume-to-mntphp-app-backup)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## Introduction
This project focuses on migrating a PHP application running on an AMD instance to an AWS Graviton instance to improve performance and cost efficiency.

## Prerequisites
- AWS account
- Basic understanding of AWS EC2
- PHP application that needs to be migrated

## Installation
1. **Create a Graviton Instance**
2. **Install PHP**
3. **Install Apache Web Server**

## Migration Steps
### 1. PHP-based Web Application on AMD to Graviton
- Description of how the PHP application is currently running on AMD.

### 2. Take a Snapshot or Backup of the Existing Environment
- Instructions on how to create a snapshot or backup.

### 3. Create the Graviton Instance
- Steps to create a new Graviton instance on AWS.

### 4. Attach the Snapshot to the Graviton Instance
- Instructions for attaching the existing snapshot to the new Graviton instance.

### 5. Step-by-Step Guide: Mount the Volume to /mnt/php-app-backup
- Instructions for mounting the volume to the specified directory.

## Screenshots
### 1. Graviton Instance Creation
![Graviton Instance Creation](screenshots/5.png)

### 2. Apache Installation
![Apache Installation](screenshots/10.png)

### 3. Application Running
![Application Running](screenshots/9.png)

## Contributing
If you would like to contribute, please submit a pull request.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
