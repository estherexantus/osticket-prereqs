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

- Create VM in Azure 
- Install and enable IIS in Windows with CGI
- Download and install essential files
- Register PHP from within IIS
- Installing and configuring Heidi SQL
- Configure permissions on essential files

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/xkrg35g.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating a resource group named osTicket, create a Windows 10 Virtual Machine (VM) with 4 Virtual CPUs.
</p>
<br />

<p>
<img src="https://i.imgur.com/IrHaLll.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Steps to install and enable IIS with CGI:
<br />
IIS -> World Wide Web Services -> Application Development Features -> CGI 
</p>
<br />

<p>
Download and install essential files with this link: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
<br />
<ul>
  <li>PHP Manager for IIS</a></li>
  <li>Rewrite Module</li>
  <li>Create the directory C:\PHP</li>
    <ul>
        <li>Extract the contents of PHP 7.3.8 into C:\PHP</li>
    </ul>
  <li>VC_redist.x86.exe</li>
  <li>MySQL 5.5.62</li>
     <ul>
        <li>Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->
    Set password
       </li>
     </ul>
</ul>
</p>
<br />

<p>
<img src="https://i.imgur.com/Jqpenhh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After opening IIS as an admin, register PHP from within IIS. Be sure to restart ISS afterwards. Do so by selecting "Register new PHP version".
</p>
<br />

<p>
<img src="https://i.imgur.com/lc7MPDg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites -> Default -> osTicket -> Click “Browse *:80” on the right
</p>
<br />

<p>
<img src="https://i.imgur.com/AW0xbBq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
osTicket site should pop up
</p>
<br />

<p>
<img src="https://i.imgur.com/sj02am0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Some extensions neeed to be enabled. Follow these directions:
  <ol>
    <li>Go back to IIS, sites -> Default -> osTicket</li>
    <li>Double-click PHP Manager</li>
    <li>Enable these extensions</li>
      <ul>
        <li>php_imap.dll</li>
        <li>php_intl.dll</li>
        <li>php_opcache.dll</li>
        <li>Refresh the osTicket site in your browse</li>
      </ul>
  </ol>
</p>
<br />

<p>
Rename file to ost-config.php and assign permissions 
  <ol>
    <li>Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</li>
    <li>Change ost-sampleconfig.php to ost-config.php</li>
    <li>Disable inheritance by going to properties and select remove all</li>
    <li>Add new permissions and rovide all users full control</li>
  </ol>
</p>
<br />

<p>
Continue setting up osTicket by selecting continue, name the help desk and enter a default email. 
</p>
<br />

<p>
  <img src="https://i.imgur.com/r2rn6N1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Download and install the Heidi SQL:
  <ul>
    <li>Open Heidi SQL</li>
    <li>Create a new session, username is root and enter a password</li>
    <li>Connect to the session</li>
    <li>Create a database called “osTicket”</li>
  </ul>
 </p>
 
 <br />
 <p>
 Continue setting up osTicket in the browser:
  <ul>
    <li>MySQL Database: osTicket</li>
    <li>MySQL Username: root</li>
    <li>MySQL Password: Password1</li>
    <li>Click “Install Now!”</li>
    <li>Click “Congratulations! osTicket should be installed with no errors.”</li>
  </ul>
</p>
<br />

<p>
  Clean up files:
  <ul>
    <li>Setup file from Delete: C:\inetpub\wwwroot\osTicket\setup</li>
    <li>Set Permissions to “Read” only for ost-config.php by C:\inetpub\wwwroot\osTicket\include\ost-config.php</li>
  </ul>
</p>
<br />

<p>
<img src="https://i.imgur.com/9mAEXiw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When searching this site, it should've load this page successfully. 
</p>
<br />

<p>
<img src="https://i.imgur.com/BdoSCUs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Page after logging in with credentials 
</p>
<br />
