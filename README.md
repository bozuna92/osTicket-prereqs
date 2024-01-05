# osTicket-Prereqs and Install

 use these files to install osTicket and some of the dependencies
 https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

 Using our Azure virtual machine:
 
 -copy your public ip address and on windows search for your remote desktop connection

 ![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/f124d88a-3671-4cf5-8d42-2885cc077a6e)

 
![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/e08cf617-d3b8-4d9d-8775-2c27a7d41d9c)


-paste your ip address and hit connect

-next screen will be username and password created for your virtual machine in my case it was
labuser
Applesauce1!

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/17a2da03-b383-4c36-ae7b-6a54c96a867f)



-if credintials are correct you will see this screen next. press yes to connect to VM.

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/3089d182-f83a-444b-a7b9-eed881233e60)


-in virtual machince we install and enable IIS with CGI

open control panel, open programs (features on or off)

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/5a42750d-595e-4908-a628-f6214abdc793)


select internet information services-
expand world wide web services-
application development features-
check cgi-
go to common HTTP features make sure they are all selected and hit ok

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/56db76b2-6769-4f28-89d5-12651cbc2c5b)


-to check if settings worked go to web and search 127.0.0.1 and you should see this page

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/662a924d-fdd3-47f4-96cf-8e958746ed6c)



-next step will be download and install PHP module from the google drive file!

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/11781c4e-17bb-4b50-a7a1-d40b6dcad3c4)




-next download and install rewrite module


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/3960654c-3dde-41a3-93f6-b9ec1f913c0d)


-next create directory for PHP on local hard drive


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/7c88291c-0139-4dec-8747-eddfe0f29d5d)


-from installation files download PHP and extract all into The PHP folder we created in c-drive
  
![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/9cad387a-bc93-49cb-bf2b-46bbf4acb106)


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/2598aa67-11a3-446b-967a-15b2c69ed3aa)



-From the Installation Files, download and install VC_redist.x86.exe.

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/eedc488a-716d-460f-9bc5-af3207d8cad9)


-From the Installation Files, download and do "typical" install MySQL 5.5.62 (mysql-5.5.62-win32.msi)

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/890add88-a692-46b3-a03d-d519ea2039ff)


once finish set up credentials : 

user: root
password: Applesauce1!

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/55c4f186-e925-4048-9918-cdaff3f90ec5)



-next step will be to Open IIS as an Admin


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/21a1cdf4-9651-46f8-a2d5-a8c6da794d8f)



-Register PHP from within IIS
double click php manager, click register new php

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/a86c579d-f6e5-4208-afce-d7e01b5803a7)



-browse to c-drive, PHP folder, and php-cgi
 
 
 ![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/a2708db6-7144-44ae-a3b6-0164e620ff56)
 

 



-Reload IIS (Open IIS, Stop and Start the server)

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/7a15717c-3174-4c0d-aa16-0beefa7d5049)


-Install osTicket v1.15.8
Download osTicket from the Installation Files Folder

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/04669190-6615-4f3b-a41b-fbdf61c57d09)



Drag and drop “upload” folder to c:\inetpub\wwwroot

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/fc71b1a8-da20-4b76-903a-092224f6ecb7)



once it is done extracting Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/da25db17-a40e-4beb-aeb3-189949f05286)



-Reload IIS (Open IIS, Stop and Start the server)

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/7a15717c-3174-4c0d-aa16-0beefa7d5049)



-Go to sites -> Default -> osTicket
On the right, click “Browse *:80”

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/5097ced9-6e28-46a7-9b23-68710b54ed46)



-If osticket is working you should have seen this site after clicking “Browse *:80”

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/6a8713e1-aa6e-4ae3-84d8-c8b7db67f0fa)


-some extensions are not enabled and to fix this we will:

Go back to IIS, sites -> Default -> osTicket

Double-click PHP Manager

Click “Enable or disable an extension”

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/2ad6f74c-435f-459e-ab6f-394adc885582)



Enable: php_imap.dll

Enable: php_intl.dll

Enable: php_opcache.dll

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/159d54a5-bce6-4fc0-afa8-6253b297a8d9)



Refresh the osTicket site in your browse, observe the changes


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/9e300d53-24ea-45cb-8965-ad63ecf2f4bd)


-next Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/b372dc60-1d08-465a-a695-563a6590d83a)




-next Assign Permissions: ost-config.php (right click and go to properties)
Disable inheritance -> Remove All
New Permissions -> Everyone -> All

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/0479e4d1-629a-474e-93b7-dc65ddc12755)



-Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/b4bd6609-f0fe-4a22-ba5d-d1a4095797f3)


-For the osticket to work we need to install the data base (heidiSQL)

download and install HeidiSQL.

Create a new session, root/Password1

Connect to the session


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/9ba9963a-cb21-47da-9dfc-6684f75e3251)


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/25ad5b7f-6099-49ed-9188-a950c0fabf3d)


right click on "unnamed" Create a database called “osTicket”


![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/39e730c6-216d-498b-9a3a-2fad7933dd0d)


-Finish setting up osticket by logging in

MySQL Database: osTicket

MySQL Username: root

MySQL Password: Password1

Click “Install Now!”

![image](https://github.com/bozuna92/osTicket-prereqs/assets/155588954/51bc067b-790d-42be-a026-06b706111c72)




Congratulations, hopefully it is installed with no errors!























 

 
