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

<h3>
1.Create a Virtual Machine (VM) on Azure
     -Create a new VM and select a Windows Server image.
</h3>

![image](https://github.com/user-attachments/assets/d26b4cbe-c7e1-4167-bd1a-3282753184db)

![image](https://github.com/user-attachments/assets/8e709419-a258-4d6e-ae84-1e7852c820a6)

![image](https://github.com/user-attachments/assets/6f69f5b1-202c-4de5-815a-967343eadb5a)
<p>
     Red: Name your Machine <br />
     Blue: Choose appropriate region for use <br />
     Pink: Choose a Windows based Operating system <br />
</p>
<p>Click Review=Create<p/>
<br />

<p>
2.Log into the VM with Remote Desktop using its public IP address ///
</p>
<br />

<p>
3.Install / Enable IIS in Windows WITH CGI /// <br />
     -Using the computers loop back address 127.0.0.1 to check if you have IIS enabled
</p>

![image](https://github.com/user-attachments/assets/ec3727a9-c5fd-41a3-92b6-ef5ec35504bb)

<p> GO to your start button and type in control panel and click UNISTALL PROGRAM to get you to the programs screen</p>

![image](https://github.com/user-attachments/assets/3fff91e7-7b4a-4d55-801a-932ff03ddf69)

![image](https://github.com/user-attachments/assets/56f86649-5e43-4482-812c-b61acea837cf)

<p>1. Click on Turn Windows features on or off</p> <br />
<p>2. Look for Internet Information Services and Click the box to enable</p> <br />

![image](https://github.com/user-attachments/assets/24d10983-e339-4d21-89b2-160ce048c625)

<p>3. CLick the + next to Internet Information Services (1), to ALSO intall CGI we need to access World Wide Web Services, Application Development Features (2), and THEN enable CGI (3)</p> <br />

![image](https://github.com/user-attachments/assets/82ccb434-42a9-48ab-b703-e5c7834c15ff) 

<p>THEN CLICK OK AND WAIT FOR INSTALL</p>

<p> We will need CGI for handling web requests, typically for running server-side scripts like PHP. It allows the web server to interface with the backend PHP scripts that power osTicket's functionality, such as processing form submissions and interacting with the database.</p>

<p>You can now check to see if your IP call back IIS is now enabled</p>

![image](https://github.com/user-attachments/assets/48f0e214-24d7-46e5-af60-51df7df2bbdc)

<br />

<p>
4. Install the PHP manager for ISS in our OS-Ticket install folder, without this PHP Manager, you'd have to manually configure IIS to work with PHP, which can be more complicated. ///
</p>

![image](https://github.com/user-attachments/assets/bc34f691-46a1-4a0f-8a2d-2a8694487c68)

<p>RUN THE WIZARD SETUP AND INSTALL TO Virtual Machine</p>

<p>Next we will install our Rewrite module from our folder set up it in summary ensures that osTicket's routing works smoothly on IIS, enabling clean, user-friendly, and SEO-optimized URLs.</p>

![image](https://github.com/user-attachments/assets/f349b15b-6857-40d9-a51c-5d40bf1ad1fc)

<br />

<p>
5.Creat a directory called C:\PHP ///
</p>

<p>OPEN a new File Explore</p>

![image](https://github.com/user-attachments/assets/728c3ce7-3490-46a4-8569-91308c755a3c)

<p> ONE-    CLICK THIS PC</p><br />
<p> TWO-    CLICK (Windows (C:))</p><br />
<p> THREE-  RIGHT CLICK TO OPEN OPTIONS</p><br />
<p> FOUR-   CLICK (New >)</p><br />
<p> FIVE-   CLICK ON THE FOLDER ICON </p><br />
<p> SIX-   NAME FILE (PHP) </p><br />

![image](https://github.com/user-attachments/assets/f89a8c30-50e7-4cde-b038-0e7048c8c6dd)

<p>Next we will extract our PHP folder in our Installation folder into our NEW PHP folder in our C drive</p> <br />

![image](https://github.com/user-attachments/assets/0dc496e4-f5a1-467f-b248-f9500e5a4ca2)

![image](https://github.com/user-attachments/assets/f56d51e9-4f38-46b9-b85a-900b0491cf39)

![image](https://github.com/user-attachments/assets/5927b37c-cd86-48e4-b490-2fbdcbc44882)

![image](https://github.com/user-attachments/assets/7a30febf-aee1-4423-ba56-a0cb67acfb23)

![image](https://github.com/user-attachments/assets/0b1bfb40-b6b7-4a77-8b16-c0cc1907bf1b)

<p>Creating a PHP folder on your C drive is part of properly configuring PHP on your IIS server to ensure osTicket runs without issues.</p>

<br />

<p>
6.Install Microsoft Visual C++  ///
</p>

<p>Installing the Microsoft Visual C++ Redistributable is critical for ensuring that PHP and osTicket function properly on your Windows server.</p>

![image](https://github.com/user-attachments/assets/ee2c2499-3e52-4266-b4b2-5fdb1d4b7da6)

<p>RUN INSTALLATION WIZARD AND INSTALL</p>
<br />

<p>
7.Install MySQL ///
</p>

<p>MySQL is needed for osTicket because it acts as the central repository for all the data the system needs to operate. It stores tickets, users, and other important information, ensures data integrity, enables efficient querying and searching, and provides the scalability and reliability necessary for handling growing data and users. Without MySQL, osTicket wouldn't be able to store or retrieve any data.</p>

![image](https://github.com/user-attachments/assets/ee6b6c37-fcd0-41ad-906d-0e4197a96d55)

<p>WHEN IN INSTALLATION WIZARD CLICK (TYPICAL SETUP)</p>

![image](https://github.com/user-attachments/assets/aab8f379-11fe-4a4f-aea9-33469a9d0ef5)

<p>LAUNCH THE SET UP WIZARD</p>

![image](https://github.com/user-attachments/assets/32e9755f-53fc-481a-b08b-e32ca50b4c48)

<p>CLICK THE STANDARD CONFIG</p>

![image](https://github.com/user-attachments/assets/4af3036f-7822-4dd2-8fd4-b0770df6cc6a)

![image](https://github.com/user-attachments/assets/0aa43312-30d8-457c-a169-b65a4d8e1fd3)

<p>CREATE AN ADMIN ACCOUNT FOR THIS I WILL USE</p><br />
<p>USERNAME: root</p><br />
<p>PASSWORD: root</p><br />
<p>DO NOT DO THIS IN REAL LIFE!!!</p><br />

![image](https://github.com/user-attachments/assets/d9a63577-7bbb-492f-ab0f-d85c2dfb0361)

![image](https://github.com/user-attachments/assets/e9f4eee4-f606-4dc6-b096-b0cd3e71ab0e)

<p>EXECUTE</p>

<br />

<h3>
8.OPEN IIS as an admin ///
</h3>

<p>Click your start menu, type IIS and run as admin </p>

![image](https://github.com/user-attachments/assets/79ef3957-91e7-48a9-ab2f-49f288da9f90)

<p>Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe) this makes the server aware of PHP on the computer </p>

![image](https://github.com/user-attachments/assets/52655f6f-b402-4ef8-9e9c-ce893b52e937)

![image](https://github.com/user-attachments/assets/f1453f01-f21a-438f-bbd9-aec3a0d86454)

![image](https://github.com/user-attachments/assets/99ab29cd-3eb7-46bf-919c-310b6bb60e35)

![image](https://github.com/user-attachments/assets/d32a4112-0356-48b4-ab35-0099b7647348)

![image](https://github.com/user-attachments/assets/5df03ebc-2615-4176-a048-cf613ea10bff)

![image](https://github.com/user-attachments/assets/c65638b8-e32c-43e3-95b0-7c4754e4c5d3)

![image](https://github.com/user-attachments/assets/41f2669b-600d-4f69-b4de-0308d9a9331f)

<p>STOP THE SERVER</p>

![image](https://github.com/user-attachments/assets/7b8549b6-eef2-461f-9484-5808a6c1162e)

<p>ONE- RIGHT CLICK</p><br />
<p>TWO_ CLICK</p><br />

<p>START THE SERVER WHEN STOP IS COMPLETED</p>

![image](https://github.com/user-attachments/assets/3fc09abc-3a66-4b84-876b-5c6812bb500b)

<br />

<p>
8.Install osTicket ///
</p>

<p>In our installation folder we will open the osTicket installation folder and add the “upload” folder into “c:\inetpub\wwwroot” Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
 </p>

![image](https://github.com/user-attachments/assets/87e9f426-1793-4851-a91a-8c40fe8a2762)

![image](https://github.com/user-attachments/assets/cd6717f7-9be5-4ca7-9ca1-72013b7d5d2d)

![image](https://github.com/user-attachments/assets/8f33aab3-6ec1-4690-8cae-6637e26d32ab)

![image](https://github.com/user-attachments/assets/bca1a160-118a-46c8-a89c-8335260f6121)

![image](https://github.com/user-attachments/assets/d9033727-3300-4c42-9702-7111260d626c)

<p>STOP & START THE SERVER ONE MORE TIME</p>

<p> Next we will load the osTicket site as our Default site</p>

![image](https://github.com/user-attachments/assets/c0897ae7-4da9-4108-b0dd-969e206ca816)

![image](https://github.com/user-attachments/assets/bbfe435b-80d4-4eef-8c4e-973c6f063f03)

<p>Now we will configure the X's on the osTicket Installer!!</p><br />

<p>Open IIS to our Default site page for osTicket, THEN click the PHP manager</p>

![image](https://github.com/user-attachments/assets/fcac75e0-bb92-4d3d-bcb0-cb9b8cfa8e67)

![image](https://github.com/user-attachments/assets/2d513c69-0b2b-417c-9613-edb1ba2b4072)

<p>WE WILL NOW ENABLE OUR THREE EXTENSIONS NEEDED</p><br />

<p>Enable: php_imap.dll - (The php_imap.dll extension enables IMAP support in PHP, allowing osTicket to fetch incoming emails from mail servers and convert them into tickets.)</p><br />
<p>Enable: php_intl.dll - (The php_intl.dll extension enables internationalization support in PHP. In osTicket, it's used to handle multilingual content and localization.)</p><br />
<p>Enable: Enable: php_opcache.dll - (The php_opcache.dll extension enables OPcache, a PHP caching mechanism that improves performance by caching precompiled PHP script bytecode in memory.) </p><br />

![image](https://github.com/user-attachments/assets/145762fe-1ae3-4c9a-a472-62f3e1ac4650)

![image](https://github.com/user-attachments/assets/f9e259e9-8c05-4fa9-885f-7afdfdf72b41)

![image](https://github.com/user-attachments/assets/8ec1618a-e679-441b-bf87-a2bcb6427c0d)

<p>WE WILL NOW REFRESH OUR SCREEN ON THE osTICKET PAGE</p><br />

![image](https://github.com/user-attachments/assets/19d203e0-f7e1-4df0-b7c4-42d4daa49853)

<p>WE WILL NOW RENAME: ost-config.php <br />
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php <br />
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php <br />
 </p><br />

 <p>and make sure osTicket has access to the file</p>

![image](https://github.com/user-attachments/assets/656d8bb7-ff15-45f4-ab11-50954739fc10)

![image](https://github.com/user-attachments/assets/7ffc009c-49d6-42ff-a4cf-39355c3585b5)

![image](https://github.com/user-attachments/assets/4aacd5cd-8653-46d0-a97b-9beb7270fcc6)

![image](https://github.com/user-attachments/assets/0a0bc54d-1dec-4fb2-82c5-df94bfe83e12)

![image](https://github.com/user-attachments/assets/97a10d44-280e-42f9-88f0-2cea99288fd7)

 <p>Now we eill make sure osTicket has access to this NEW file</p>

![image](https://github.com/user-attachments/assets/eaf53754-138e-4ca9-9a9e-05c43057d24b)

![image](https://github.com/user-attachments/assets/9387b2d6-4d62-4efe-ae82-a96a3382813a)

![image](https://github.com/user-attachments/assets/c009129b-cbe2-4445-8660-a3ce731d21a4)

![image](https://github.com/user-attachments/assets/fca8122a-9090-41ef-a6b3-62bded5d9b6e)

![image](https://github.com/user-attachments/assets/4734ba7f-4589-491b-8118-615f903a9958)

![image](https://github.com/user-attachments/assets/918621c8-8535-4bb8-ab1f-aeda9cc97c27)

![image](https://github.com/user-attachments/assets/b985a3d0-8823-4843-989b-0c06a2cfc08d)

![image](https://github.com/user-attachments/assets/4a036e74-ad7f-4eb8-982a-2569b901b4f3)

<p>NOT GOOD TO GIVE EVERYONE ACCESS BUT WE ARE DOING IT IN THIS PROJECT/p>

![image](https://github.com/user-attachments/assets/18fb548c-314b-4d8b-a366-9e2491208fc1)

![image](https://github.com/user-attachments/assets/c23a99a5-2705-496f-9690-11d2416c6c51)

![image](https://github.com/user-attachments/assets/41bf5d46-dc90-4804-872b-780ceab483d9)

 <p>Now we will continue our osTicket installation!</p>

![image](https://github.com/user-attachments/assets/2277e02a-0873-448e-9572-de282c7a674f)

<p>FIll out your information</p> 

![image](https://github.com/user-attachments/assets/a09407e7-22b1-4fb2-a806-0f5371ca484c)

<p>We now need to create an SQL data base for odTIcket to use. GO BACK to your installation folder to install HeidiSQL. </p> <br />
<p>Open Heidi SQL</p><br />
<p>Create a new session, root/root</p><br />
<p>Connect to the session</p><br />
<p>Create a database called “osTicket”</p><br />

![image](https://github.com/user-attachments/assets/59525a70-baf5-47fb-b738-605b5e8e9196)

![image](https://github.com/user-attachments/assets/1aaa6e1b-4731-48a8-851c-e911318e6b14)

![image](https://github.com/user-attachments/assets/fbf06e17-e085-4fbb-bf39-4b8c9cdcd09d)

![image](https://github.com/user-attachments/assets/e6c61f8f-9cb7-4a72-b622-3c1a1f3318fa)

![image](https://github.com/user-attachments/assets/9b962c8e-2c3e-4f49-8f4a-b2da002410c1)

![image](https://github.com/user-attachments/assets/75c1ab94-cced-4040-9719-f74f62cfb408)

![image](https://github.com/user-attachments/assets/48eb12f2-2f26-4c62-8c9d-c786999bfde5)

![image](https://github.com/user-attachments/assets/9730e9d6-21ec-45cd-a282-3cb1a120529b)

<p>NOW WE WILL LOG INTO OUR ROOT ACCOUNT WE MADE FOR OUR BACKEND SQL</p> <br />
<p>USERNAME: root PASSWORD: root (THIS IS MY ACCOUNT)</p>

![image](https://github.com/user-attachments/assets/32a0a577-8142-405d-8aef-cfee4fd812e2)

![image](https://github.com/user-attachments/assets/df8f6c9c-b212-4de2-9aaa-bd439943bc88)

<p>WE WILL NOW CREAT A DATABASE CALLED osTicket</p>

![image](https://github.com/user-attachments/assets/c3c91bcf-8d1a-4d03-8e36-4c8a61133518)

![image](https://github.com/user-attachments/assets/960dca2e-e7a5-4363-b3c6-cd3bca57b1f7)

![image](https://github.com/user-attachments/assets/3de03447-2620-4b93-80e9-779cba73767c)

![image](https://github.com/user-attachments/assets/5c7a4369-e189-44c8-aea1-f2d900a81fe8)

<p>We now Continue Setting up osTicket in the browser</p> <br />

![image](https://github.com/user-attachments/assets/ecd74f64-aa3d-474a-b52b-bba8b3ef7f26)

<p> INSTALL NOW!!!! </p>

![image](https://github.com/user-attachments/assets/e76bf65f-d4ab-4c5d-b5de-85a153d9fae4)

![image](https://github.com/user-attachments/assets/fe49288e-061c-4bdd-bc65-fb47282f4578)

<p>Congrats you have now installed osTicket on your VM!!! </p>
