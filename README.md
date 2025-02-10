# osTicketProject
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- 1. Web Server
     -needed to run PHP applications
- 2. PHP version 7.3 or higher
- 3. Database
     -MySQL or MariaDB
- 4. File Permissions
     -The osTicket files and directories should have the appropriate write permissions for the web server (chmod 755 for directories and chmod 644 for files).
- 5. SMTP Email Server (Optional)
     -To send emails, you'll need an SMTP server (such as Gmail or your own mail server) configured for osTicket.
- 6. SSL Certificate (Recommended for Security)
     -SSL/TLS is recommended if you're planning to handle sensitive data, You can obtain an SSL certificate from a trusted CA.
- 6. Azure Virtual Machine 
     
<h2>Installation Steps</h2>

<p>
1.Create a Virtual Machine (VM) on Azure
     -Create a new VM and select a Windows Server image.
</p>
<br />

<p>
2.Install MySQL/MariaDB and create a database ///
</p>
<br />

<p>
3.Download and extract osTicket to the web server’s root directory ///
</p>
<br />

<p>
4.Set the appropriate file permissions for the osTicket directory ///
</p>
<br />

<p>
5.Run the web-based installer via your browser (ex. http://yourdomain.com) ///
</p>
<br />

<p>
6.Configure the database and SMTP settings through the installer ///
</p>
<br />

<p>
7.Complete the setup and start using osTicket ///
</p>
<br />

