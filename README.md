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

- IIS and Management Console
- PHP and Rewrite Module
- MySQL
- HeidiSQL
- osTicket

<h2>Installation Steps</h2>

<p>
<img src="https://imgur.com/ocnylGU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a virtual machine (VM) that uses Windows 10 OS. 
  <p>
  <img src="https://imgur.com/7Wu8CcZ.png" height="80%" width="80%"/>  
    <p>
  Install IIS by right-clicking on the start button, click on "run" and type in "control panel". Select program and features. Select "windows features". Install and enable IIS management console in web management tools. Also, enable CGI and all of Common HTTP Features boxes (located in: world wide web services > application development features.) You can confirm everything was enabled correctly by visiting 127.0.0.1 & making sure it will load the Windows IIS homepage. Install PHP manager. Install rewrite module.
</p>
<br />

<p>
<img src="https://imgur.com/8jK35Gy.png" height="80%" width="40%"/>
<img src="https://imgur.com/FekJ0IP.png" height="80%" width="40%"/>
</p>
<p>
Create a folder in C:\ called "PHP". Install PHP and unzip contents to PHP folder you created. Install VC redist.x86.exe.
</p>  
<img src="https://imgur.com/9PZfGNm.png" height="50%" width="40%"/><img src="https://imgur.com/4gEt1cn.png" height="50%" width="40%"/>

Install MySqL (typical setup). Launch configuration wizard, select standard and create a name plus password. FYI- You will need to remember them.
</p>
<p>
<img src="https://imgur.com/m0jPKFD.png" height="80%" width="80%"/>
</p>
<p>
Open IIS as administrator. Register PHP inside of IIS. Stop and start server. 
<p>
<img src="https://imgur.com/y6StaX6.png" height="80%" width="80%"/>
<p>
Install osTicket. Extract "uploads" folder to C:\inetpub\wwwroot. Rename the folder "osTicket". Reload IIS (Stop and start server). Go to: sites > default > osTicket; on the far right of the window, click on "Browse*:80". Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename "ost-sampleconfig.php" to "ost-config.php".
<p>
<img src="https://imgur.com/SY9q9k8.png" height="80%" width="80%"/>

Next, you will need to enable PHP extensions before continuing with osTicket. Go back to IIS and go to "sites > default > osTicket. Double click on PHP manager and then click on "Enable or disable an extension". Assign file permissions to everyone (Disable inheritance > Remove All, New Permissions > Everyone > All).
<p>
<img src="https://imgur.com/jMUe9QR.png" height="80%" width="80%"/>
<p>
Enable "php_imap.dll", "php_intl.dll" and "php_opcache.dll". 
<p>
<img src="https://imgur.com/a7wRUes.png" height="80%" width="80%"/>
<p>
If you refresh the browser, osTicket's PHP extension changes will be shown.
</p>
<br />

<p>
<img src="https://imgur.com/yHPp6mT.png" height="80%" width="80%"/>
</p>
<p>
Start filling out the form in osTicket. Before you complete the form, you'll need a database client. 
<p>

Install HeidiSQL. Open HeidiSQL and create a new database using the name and password you created for MySQL. Connect to session and create a database called "osTicket". Now that you've created a database you can now finish filling out the form. Use your MySQL name and password on the form. Click install now. Browse to your help desk login page: http://localhost/osTicket/scp/login.php. There's a little bit of cleanup necessary before you proceed. Delete: C:\inetpub\wwwroot\osTicket\setup. Set permissions to “Read, Read and execute" at : C:\inetpub\wwwroot\osTicket\include\ost-config.php. Confirm you executed the steps correctly by going to http://localhost/osTicket/scp/login.php and sign in using the Admin account info.
</p>
<br />
