<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system, osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
<img src="https://imgur.com/fRlEjMF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should be called “osTicket-Installation-Files”
We will use the files in this folder to install osTicket and some of the dependencies.

</p>
<br />

<p>
<img src="https://imgur.com/6b7LBHj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to Control Panel -> Programs -> Turn Windows Features on and off -> Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

</p>
<br />

<p>
<img src="https://imgur.com/1syc8Yk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<p>
<img src="https://imgur.com/oywiEb8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From the “osTicket-Installation-Files” folder, install the Rewrite Module (rewrite_amd64_en-US.msi)

</p>
<br />

<p>
<img src="https://imgur.com/dftuaIK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Create the directory C:\PHP

</p>
<br />

<p>
<img src="https://imgur.com/ak1XB0A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

</p>
<br />

<p>
<img src="https://imgur.com/izU2FEN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

</p>
<br />

<p>
<img src="https://imgur.com/EroAl5z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/fMCLiJq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/oyI0b1Y.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/rQIejth.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup->Launch Configuration Wizard->Standard Configuration->User/Pass: root

</p>
<br />

<p>
<img src="https://imgur.com/x1XcRvX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Open IIS as an Admin

</p>
<br />

<p>
<img src="https://imgur.com/P5nXWrE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Install OsTicket by unzipping "osTicket-Installation-Files", unzip "osTicket-v1.15.8zip" and copy the "upload" folder into "c:\inetpub\wwwroot", Rename "upload" to "osTicket"

</p>
<br />

<p>
<img src="https://imgur.com/ASLqfMc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Reload IIS (Open IIS, Stop, and Start the server)

</p>
<br />

<p>
<img src="https://imgur.com/QZ9tWgh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

</p>
<br />

<img src="https://imgur.com/O3nY3JG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

!Note that some extensions are not enabled!

</p>
<br />

<p>
<img src="https://imgur.com/YehJFIm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/hrB694q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/lk5X7Cc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Go back to IIS, go to sites on the left side->Default->OsTicket. After that double click PHP Manager,Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll

</p>
<br />

<p>
<img src="https://imgur.com/fzL4QHS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Refresh the OsTicket Browser to observe the changes.

</p>
<br />

<p>
<img src="https://imgur.com/P8W42Ic.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

<p>
<img src="https://imgur.com/KCRntDZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/lzx1zl6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


</p>
<p>

Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

</p>
<br />

<p>
<img src="https://imgur.com/JbOUan6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Continue Setting up osTicket in the browser (click Continue)

</p>
<br />

<p>
<img src="https://imgur.com/5im0J4G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

From the “osTicket-Installation-Files” folder, install HeidiSQL.

</p>
<br />

<p>
<img src="https://i.imgur.com/uho2DF5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/rHbMfV0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/rQIejth.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/U8GrIby.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

Open Heidi SQL and create a new session using the "root" username and password we previously created, connect to the new session and create a database called "osTicket"

</p>
<br />

<p>
<img src="https://imgur.com/NgI4AJe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

  Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

</p>
<br />

<p>
<img src="https://imgur.com/iQxXMPl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>


Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

</p>
<br />



</p>


</p>
</p>

</p>


