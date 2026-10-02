# Walkthrough 1: Install osTicket on an Azure Windows VM

[Back to project overview](README.md)

## Objective

Build the Azure environment and install a working osTicket 1.15.8 help desk on Windows 10.

## Environment and technologies

Azure, Windows 10 Enterprise 22H2, RDP, IIS, CGI, PHP 7.3.8, PHP Manager, URL Rewrite, MySQL 5.5.62, HeidiSQL 12.3, and osTicket 1.15.8.

## Demonstration

### 1. Create the Azure environment

1. In Azure, open **Resource groups > Create**.
2. Create `rg-bhc-lab3-osticket` in East US 2.
3. Inside the group, select **Create > Azure virtual machine**.
4. Name it `osticket-vm`, choose Windows 10 Enterprise 22H2 Gen2, and select `Standard_D4ls_v6` (4 vCPU, 8 GiB).
5. Choose no infrastructure redundancy, create the local administrator, and temporarily allow inbound RDP on TCP 3389.
6. Review the configuration, select **Create**, and wait for deployment to succeed.

### 2. Connect through RDP

1. Open the VM overview and select **Connect > RDP**.
2. Download and open the RDP file.
3. Sign in as `osticket-vm\bluehippo`; the password was entered privately.
4. Confirm the Windows desktop loads. The RDP bar and public IP were excluded from public evidence.

### 3. Prepare Windows and IIS

1. Download and extract the provided installation archive inside the VM.
2. Enable **Internet Information Services**, **World Wide Web Services**, **CGI**, and the IIS Management Console in Windows Features.
3. Open IIS Manager and confirm the local web server is available.

### 4. Install the dependencies

1. Install PHP Manager 1.5.0 and IIS URL Rewrite 2.
2. Create `C:\PHP` and extract PHP 7.3.8 into it.
3. Install the x86 Visual C++ Redistributable.
4. Install MySQL 5.5.62 as a Windows service and finish its configuration wizard.
5. In IIS Manager, open PHP Manager and register `C:\PHP\php-cgi.exe`.

### 5. Deploy osTicket

1. Extract osTicket 1.15.8.
2. Copy its `upload` folder to `C:\inetpub\wwwroot` and rename it `osTicket`.
3. Restart IIS and browse to `http://localhost/osTicket`.

The first installer check showed which PHP extensions were missing.

![Installer before required extensions](evidence/01_osticket_installer_before_extensions.png)

### 6. Enable the required PHP extensions

1. In PHP Manager, enable IMAP, Intl, and OPcache.
2. Correct the OPcache line in `php.ini` to `zend_extension=php_opcache.dll`.
3. Restart IIS.

![Required extensions enabled](evidence/02_php_extensions_enabled.png)

Reloading the page showed the requirements satisfied.

![Installer after extensions](evidence/03_osticket_installer_after_extensions.png)

### 7. Create the configuration file and database

1. Rename `include\ost-sampleconfig.php` to `include\ost-config.php`.
2. Temporarily grant write access to that file for installation.
3. Install HeidiSQL, connect to MySQL at `127.0.0.1`, and create database `osTicket`.

### 8. Complete and secure the installation

1. Enter the help-desk name and default email.
2. Create the administrator account; its password was never recorded.
3. Enter the local MySQL host, database, and administrator information.
4. Submit and verify the **Congratulations** page.

![Successful osTicket installation](evidence/04_osticket_install_congratulations.png)

5. Delete the `setup` directory.
6. Make `ost-config.php` read-only.
7. Verify both the end-user portal and `/osTicket/scp` staff login page.

## Result

The Azure VM was running IIS, PHP, MySQL, and a functional osTicket instance ready for administrative configuration.

