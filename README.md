# osTicket Help Desk System Installation

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

## Overview

Deployed and configured osTicket, an open-source help desk ticketing system, on a Windows 10 VM in Azure using IIS, PHP, and MySQL.

<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute][(https://www.youtube.com/watch?v=VRnegKfQFxc)]

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines)
- Remote Desktop
- Internet Information Services (IIS)
- PHP Manager & MySQL

## Operating System

- Windows 10 (21H2)

---

## Installation Steps

### 1. Create Azure Virtual Machine

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/create-azure-machine.png)

Created Windows 10 VM in Azure with 4 vCPUs

- VM Name: osticket-vm
- Connected via Remote Desktop

### 2. Install IIS with CGI

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/install-iis.png)

Enabled IIS in Windows Features with CGI support

- Control Panel → Programs → Turn Windows features on/off
- World Wide Web Services → Application Development Features → ✅ CGI

### 3. Install PHP Manager & Dependencies

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/install-php.png)
![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/register-php.png)

Installed required components:

- PHP Manager for IIS
- URL Rewrite Module
- PHP 7.3.8 (extracted to C:\PHP)
- VC++ Redistributable
- Registered PHP in IIS

### 4. Install MySQL Database

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/install-iis.png)
Installed MySQL 5.5.62

- Standard Configuration
- Credentials: root/root

### 5. Install osTicket

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/install-sql.png)
![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/rename-osticket.png)

Deployed osTicket application:

- Extracted osTicket files to C:\inetpub\wwwroot
- Renamed "upload" folder to "osTicket"
- Reloaded IIS

### 6. Enable PHP Extensions

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/enable-extensions.png)

Enabled required extensions via PHP Manager:

- php_imap.dll
- php_intl.dll
- php_opcache.dll

### 7. Configure osTicket

![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/osticket-installed.png)
![image](https://raw.githubusercontent.com/LasalleFrazier/assets/main/heidi-sql.png)

Completed setup:

- Renamed ost-sampleconfig.php to ost-config.php
- Set permissions for Everyone
- Created database in HeidiSQL
- Configured osTicket via browser

---

## Access URLs

**Admin/Agent Login:**  
http://localhost/osTicket/scp/login.php

**End User Portal:**  
http://localhost/osTicket/

---

## Key Skills Demonstrated

- Azure VM deployment and management
- IIS web server configuration
- PHP and MySQL database integration
- Application deployment and troubleshooting
- Security hardening and permissions management

---

## Conclusion

Successfully deployed a fully functional help desk ticketing system, demonstrating proficiency in cloud infrastructure, web server administration, and enterprise application deployment.
