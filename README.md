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
Create a virtual machine (VM) that uses Windows 10 OS. 
<p>
<img src="https://imgur.com/ocnylGU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
Install IIS by opening Control Panel in the VM, select Program & Features. Select Windows Features and then Turn Windows Features On/Off. Check the IIS (Internet Information Services) box & expand it. Check the Web Management tools & expand it to check the IIS Management Console box. Also, enable CGI by checking and expanding World Wide Web Services>Application Development Features>CGI. Expand the Common HTTP Features and check all the boxes within. You can confirm everything was enabled correctly by visiting 127.0.0.1 & making sure it will load the Windows IIS homepage. Install PHP Manager & the Rewrite Module.
  <p>
  <img src="https://imgur.com/7Wu8CcZ.png" height="80%" width="80%"/>  
    <p>
<br />
Create a folder in C:\ called "PHP". Install the PHP zip folder (different than the PHP Manager file) and unzip contents to the PHP folder you created. Install VC redist.x86.exe.
<p>
<img src="https://imgur.com/8jK35Gy.png" height="80%" width="40%"/>
<img src="https://imgur.com/FekJ0IP.png" height="80%" width="40%"/>
</p>
<p>
Install MySqL (typical setup). Launch configuration wizard, select standard and create a root password (be sure to remember this password).
</p>
<img src="https://imgur.com/9PZfGNm.png" height="50%" width="40%"/><img src="https://imgur.com/4gEt1cn.png" height="50%" width="40%"/>
</p>
<p>
Open IIS as administrator by right clicking the program from the Start Menu. Register PHP inside of IIS by selecting PHP Manager then Register new PHP Version. Click Browse "...">PHP folder>open php-cgi, then restart the server in IIS.
<p>
<img src="https://imgur.com/m0jPKFD.png" height="80%" width="80%"/>
</p>
<p>
Install osTicket. Extract "uploads" folder to C:\inetpub\wwwroot. Rename the folder "osTicket". Reload IIS (Stop and start server). Go to: sites > default > osTicket; on the far right of the window, click on "Browse*:80". Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename "ost-sampleconfig.php" to "ost-config.php".
<p>
<img src="https://imgur.com/y6StaX6.png" height="80%" width="80%"/>
<p>
<p>
Next, you will need to enable PHP extensions before continuing with osTicket. Go back to IIS and go to "sites > default > osTicket. Double click on PHP manager and then click on "Enable or disable an extension". Enable "php_imap.dll", "php_intl.dll" and "php_opcache.dll".
</p>
<img src="https://imgur.com/jMUe9QR.png" height="80%" width="80%"/>
</p>
<p>
Assign file permissions to everyone (Disable inheritance > Remove All, New Permissions > Everyone > All). 
</p>
<img src="https://imgur.com/SY9q9k8.png" height="80%" width="80%"/>
<p>
<p>
When you refresh the browser, osTicket's PHP extension changes will be shown.
</p>
<img src="https://imgur.com/a7wRUes.png" height="80%" width="80%"/>
<p>
</p>
Start filling out the form in osTicket. Before you complete the form, you will need a database client. 
<p>
<img src="https://imgur.com/yHPp6mT.png" height="80%" width="80%"/>
</p>
<p>
Install HeidiSQL. Open HeidiSQL and create a new database using the name and password you created for MySQL. Connect to session and create a database called "osTicket". Now that you've created a database you can now finish filling out the form. Use your MySQL name and password on the form. Click Install Now.
<p>
<img src="https://imgur.com/mAsXixZ.png" height="80%" width="40%"/>
<img src="https://imgur.com/tOMABDw.png" height="80%" width="40%"/>
<p>
</p>
To confirm steps were executed correctly, browse to your help desk login page: http://localhost/osTicket/scp/login.php. 
<p>
<img src="https://imgur.com/CdsyNm7.png" height="80%" width="80%"/>
<p>
<p>
Delete the setup folder found in C:\inetpub\wwwroot\osTicket\setup. Set permissions to “Read, Read and execute" at : C:\inetpub\wwwroot\osTicket\include\ost-config.php. There will be a notification on the top of the osTicket webpage if you failed to set the correct permissions.
</p>
<img src="https://imgur.com/3vcjA66.png" height="80%" width="40%"/>
</p>
<br />
