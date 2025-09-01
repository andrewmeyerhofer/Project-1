<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
<img width="254" height="254" alt="image" src="https://github.com/user-attachments/assets/64682542-313e-4d29-b846-fd0c2cb95e80" />

</p>

<h1>osTicket - Installation and Prerequisites</h1>
In this project, I installed and setup the open-source ticketing system osTicket. All the files being installed are prerequisites to run the osTicket software. This project was done within an Azure Virtual Machine.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11 (24H2)</b> 

<h2>List of Prerequisites</h2>

- Created a Windows 11 Virtual Machine using Microsoft Azure
- Logged into the virtual machine using remote desktop
- Acquired osTicket Installation Files (see picture 5 for list of files)



<h2>Installation Walkthrough</h2>

<p>
<img width="1418" height="747" alt="image" src="https://github.com/user-attachments/assets/37c4505a-e6a3-4aaf-9e3b-d8fbbf43c0e0" />

</p>
<p>
I started by downloading the ostTicket-Installation-Files.zip. These files were compiled based on the requirements listed on the osTicket installation steps page (link: https://docs.osticket.com/en/latest/Getting%20Started/Installation.html).
</p>
<br />

<p>
<img width="725" height="593" alt="image" src="https://github.com/user-attachments/assets/1ed4677b-801c-47f8-8617-b12b6e18f67a" />

</p>
<p>
Next I extracted the files to my Desktop.
</p>
<br />

<p>
<img width="1397" height="732" alt="image" src="https://github.com/user-attachments/assets/bdd5ddb6-3a03-4af5-b566-006cc7a74e3e" />

</p>
<p>
I then went to Programs in the Control Panel to turn Windows features on/off. 
</p>
<br />

<p>
<img width="726" height="485" alt="image" src="https://github.com/user-attachments/assets/256d9c44-9eaa-476d-9670-2f32ec3aaf7c" />


</p>
<p>
Within the Windows features dialogue box, I enabled IIS with CGI. This is necessary to install the file in the next step. 
</p>
<br />

<p>
<img width="1381" height="685" alt="image" src="https://github.com/user-attachments/assets/229b107f-763a-4bc7-8bd5-f34719e2826e" />


</p>
<p>
With IIS enabled, I was able to install the PHP Manager for IIS file. 
</p>
<br />

<p>
<img width="1351" height="683" alt="image" src="https://github.com/user-attachments/assets/cd599f5b-ff7c-4070-aea1-6f14ba33130c" />


</p>
<p>
I also installed the IIS URL Rewrite Module 2.
</p>
<br />

<p>
<img width="1402" height="682" alt="image" src="https://github.com/user-attachments/assets/cf15fa7a-c28b-4ccc-8c52-96e206b4a1bf" />


</p>
<p>
Next I created a new folder in the Windows C drive for PHP. 
</p>
<br />

<p>
<img width="1177" height="666" alt="image" src="https://github.com/user-attachments/assets/12818c99-221a-4c6e-809f-34701f572def" />


</p>
<p>
I then extracted the PHP 7.3.8 files into the PHP folder. After this step, I also installed the VC_redist file (no picture necessary, it's redundant).
</p>
<br />

<p>
<img width="1163" height="653" alt="image" src="https://github.com/user-attachments/assets/7e1196f9-a393-45c4-b97f-d1792a8a41f3" />


</p>
<p>
Next, I downloaded MySQL and completed all the installation steps. This included the creation of a root password and setting everything to standard configuration. MySQL will allow for the creation of a database later on, which will be used by osTicket to store necessary data such as user accounts and ticketing information.
</p>
<br />

<p>
<img width="1012" height="810" alt="image" src="https://github.com/user-attachments/assets/f5bbad1d-1f8b-4bc3-92dc-782f812f3ef6" />


</p>
<p>
I then went to IIS and clicked "Run as administrator."
</p>
<br />

<p>
<img width="1416" height="717" alt="image" src="https://github.com/user-attachments/assets/06076da7-117f-463a-90e6-6bb08610773e" />


</p>
<p>
Within PHP Manager, I clicked "Register new PHP version" and pathed it to php-cgi. I also reloaded the IIS webserver by performing a stop and start.
</p>
<br />

<p><img width="1288" height="707" alt="image" src="https://github.com/user-attachments/assets/297d0d97-0eac-4759-bcd1-66a0894f0607" />



</p>
<p>
Next, I unzipped the actual osTicket installation file.
</p>
<br />

<p>
<img width="1395" height="686" alt="image" src="https://github.com/user-attachments/assets/5d6b2c35-c39e-49a7-9745-e577b4228e7b" />



</p>
<p>
I then copied the unzipped upload folder to the wwwroot folder and renamed it osTicket. I also reloaded IIS again.
</p>
<br />

<p>
<img width="1833" height="926" alt="image" src="https://github.com/user-attachments/assets/9fd0142e-85ac-4b32-8977-ca7ad535857e" />



</p>
<p>
Within the left panel of IIS, I selected the dropdown for sites, then default web site, then osTicket. On the right panel of IIS, I clicked "Browse *:80 (http)" under the Browse Folder option. I was then taken to the osTicket setup page via the default browser (Microsoft Edge in this case).
</p>
<br />

<p>
<img width="1815" height="926" alt="image" src="https://github.com/user-attachments/assets/a513fc58-9fe9-44cb-badc-74051bc63522" />



</p>
<p>
Some of the recommended prerequisites for running osTicket were not met, so I needed to enable some extensions in PHP manager. Within the osTicket file in IIS, I double-clicked "PHP Manager" then enabled php_imap.dll, php_intl.dll, and php_opcache.dll. I then refreshed the web brower with the osTicket installer and it checked the remaining necessary boxes for the installer to work properly.

</p>
<br />

<p>
<img width="1147" height="698" alt="image" src="https://github.com/user-attachments/assets/c4547066-d209-4b4a-8efd-1fae5de12a64" />



</p>
<p>
Next I went to osTicket in the wwwroot folder and went to "include." Here I changed the name of the ost-sampleconfig.php file to ost-config.php.
</p>
<br />

<p>
<img width="1552" height="787" alt="image" src="https://github.com/user-attachments/assets/c48304ac-a493-4a31-83d1-5d8e79b01955" />



</p>
<p>
Within the properties of the ost-config.php file, I went to security and clicked "disable inheritance." I then added new permissions so that any user will have access and full control (just for the sake of this project, not smart in real life).
</p>
<br />

<p>
<img width="1197" height="797" alt="image" src="https://github.com/user-attachments/assets/7de97417-558d-48a8-b18c-313d5510ca9a" />




</p>
<p>
I then went back to osTicket setup webpage and clicked continue. Here I entered some basic filler information for the help desk and Admin User.
</p>
<br />

<p>
<img width="1407" height="745" alt="image" src="https://github.com/user-attachments/assets/ca15dd1c-b623-42f0-ba41-aaaef95de0f0" />



</p>
<p>
The next step was to set up the MySQL database and link it to osTicket. I double-clicked the Heidi folder within the the osTicket Installation files, then went through the setup wizard steps. 
</p>
<br />

<p>
<img width="1163" height="732" alt="image" src="https://github.com/user-attachments/assets/57084953-8c88-4db1-ad69-330d19a07a38" />



</p>
<p>
Once HeidiSQL was open, I created a new database named it osTicket.
</p>
<br />

<p>
<img width="1086" height="471" alt="image" src="https://github.com/user-attachments/assets/cbfb9580-5e4d-4bf6-ad87-6f2581067fac" />



</p>
<p>
I then went to the database settings and set the username and password as "root" (so it's easy to remember), then clicked "install now."
</p>
<br />

<p>
<img width="1077" height="781" alt="image" src="https://github.com/user-attachments/assets/4ed22eeb-bb7a-402d-b586-7a3abb7bd837" />



</p>
<p>
Once the database was linked, the osTicket installation was complete.
</p>
<br />
