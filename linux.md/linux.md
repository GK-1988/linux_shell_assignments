# Assignments — Linux and DevOps Basics

## Assignment — Linux and SSH Setup

1. Launch an Amazon Linux 2023 EC2 instance in HYD region. Generate an SSH key pair. What is the difference between the two files created?
---
1a> Launch an Amazon Linux 2023 EC2 instance in HYD region.
Ans:

Before Launching EC2 instance, needs to do two things. 
One is to create security group and second one is to generate SSH keypai and Import Into AWS Console.

--security Group  'linuxpractice' created successfully and below is the details/evidence.
![ṣ](image-3.png)
![ṣ](image-4.png)

1b> Generate an SSH key pair.
---
Ans:
---Command (ssh-keygen -f <filename>)

$ ssh-keygen -f gkrishna

 -->>successfully created SSH Keypair and below is the evidence.
![ṣ](image-2.png)
----------------------------------------------------------------------
lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$ pwd
/d/DEVOPS/DAWS-92s/repos/linux_shell_assignments

lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$ ll
total 0
drwxr-xr-x 1 lovel 197609 0 Nov  1 07:34 linux.md/
lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)

$ ssh-keygen -f gkrishna
Generating public/private ed25519 key pair.
Enter passphrase for "gkrishna" (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in gkrishna
Your public key has been saved in gkrishna.pub
The key fingerprint is:
SHA256:kJnYBrA7campXG1KhUMHd0sMyDPvH9i5e0R6yXD5qzE lovel@VENISHAMUMMY
The key's randomart image is:
+--[ED25519 256]--+
|  o+++oo         |
|  .*+=o=.        |
|  ooB.B.  .      |
|   *+o o +       |
|  =o.oo S o      |
|..o.oo = = .     |
|.. .  . =E  .    |
|       o .o.     |
|       .o..      |
+----[SHA256]-----+
lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$ ll
total 2
-rw-r--r-- 1 lovel 197609 411 Nov  1 07:42 gkrishna
-rw-r--r-- 1 lovel 197609 100 Nov  1 07:42 gkrishna.pub
drwxr-xr-x 1 lovel 197609   0 Nov  1 07:34 linux.md/
lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$
---------------------------------------------------
successfully launched the EC2 instance in HYD region and below is the evidence.
![ṣ](image-1.png)
---------------------------------------------------
c> What is the difference between the two files created?
---
Ans:
Generated SSH keypair successfully.
krishna      --> private key
krishna.pub  --> public key
Private key is like a password and should not be shared with anyone.
Public key can be copied into Linux servers for authentication.
-------------------------------------------------------------------------------------------------
2. Connect to your EC2 instance using SSH. Confirm you are connected by checking the hostname, current directory, and logged-in username.
---
![ṣ](image-5.png) 
![ṣ](image-6.png)

2a> Connect to your EC2 instance using SSH.
---
Ans:
--->> ssh -i gkrishna ec2-user@18.61.86.43 
-->> executed this command from relative path(current directory of keypairs)
---------------------------------------------------------------------------------
lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$ pwd
/d/DEVOPS/DAWS-92s/repos/linux_shell_assignments

lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$ ssh -i gkrishna ec2-user@18.61.86.43
The authenticity of host '18.61.86.43 (18.61.86.43)' can't be established.
ED25519 key fingerprint is: SHA256:t45/CvqUTegItfbMcdhCsWWVps7ABxn1Q/GmJcr6L4c
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '18.61.86.43' (ED25519) to the list of known hosts.
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
   ,     #_
   ~\_  ####_        Amazon Linux 2023
  ~~  \_#####\
  ~~     \###|
  ~~       \#/ ___   https://aws.amazon.com/linux/amazon-linux-2023
   ~~       V~' '->
    ~~~         /
      ~~._.   _/
         _/ _/
       _/m/'
[ec2-user@ip-172-31-45-137 ~]$
-----------------------------------------------------------------------------------
--command:
ssh -i /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments/gkrishna ec2-user@18.61.86.43
>>Executed from my homepath. Because i used absolutepath(means the location of the Keypars)
--------------------------------------------------------------------------------------
lovel@VENISHAMUMMY UCRT64 /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments (main)
$ cd
lovel@VENISHAMUMMY UCRT64 ~
$ pwd
/c/Users/lovel
lovel@VENISHAMUMMY UCRT64 ~
$ ssh -i /d/DEVOPS/DAWS-92s/repos/linux_shell_assignments/gkrishna ec2-user@18.61.86.43
** WARNING: connection is not using a post-quantum key exchange algorithm.
** This session may be vulnerable to "store now, decrypt later" attacks.
** The server may need to be upgraded. See https://openssh.com/pq.html
   ,     #_
   ~\_  ####_        Amazon Linux 2023
  ~~  \_#####\
  ~~     \###|
  ~~       \#/ ___   https://aws.amazon.com/linux/amazon-linux-2023
   ~~       V~' '->
    ~~~         /
      ~~._.   _/
         _/ _/
       _/m/'
Last login: Sun Nov  1 02:51:47 2026 from 58.84.61.145
[ec2-user@ip-172-31-45-137 ~]$
--------------------------------------------------------------------------------------------
2b> Confirm you are connected by checking the hostname, current directory, and logged-in username
Ans:
![ṣ](image-7.png)
----------------------
Last login: Sun Nov  1 02:51:47 2026 from 58.84.61.145
[ec2-user@ip-172-31-45-137 ~]$ hostname
ip-172-31-45-137.ap-south-2.compute.internal

[ec2-user@ip-172-31-45-137 ~]$ pwd
/home/ec2-user

[ec2-user@ip-172-31-45-137 ~]$ whoami
ec2-user

[ec2-user@ip-172-31-45-137 ~]$ id
uid=1000(ec2-user) gid=1000(ec2-user) groups=1000(ec2-user),4(adm),10(wheel),190(systemd-journal) context=unconfined_u:unconfined_r:unconfined_t:s0-s0:c0.c1023
[ec2-user@ip-172-31-45-137 ~]$
-----------------------
Successfully connected to AWS Linux server using SSH private key.
hostname displayed server name.
pwd displayed current location.
whoami displayed logged in username.
id displayed complete user and group details.
---------------------------------------------------------------------------------------------
3. Your Security Group currently allows SSH from anywhere. Restrict it to your own IP only.
---
Ans:
3a> Your Security Group currently allows SSH from anywhere.
yes, becuase the inbound rule is configured with '0.0.0.0/0' and it's allow all to connect this EC2 Instance.
![ṣ](image-8.png)
3b> Restrict it to your own IP only.
Ans:
Yes, we can restriced the connectivity of others. So for this can make changes in security group Inbound rule of 'ssh' protocal with '22' port to allow connections only from my machine(winsows/Mac). For security reasons i have striked out my IP.
![ṣ](image-9.png)
-----------------------------
Initially SSH port was accessible from anywhere on internet.
Updated Security Group to allow SSH only from my public IP.
This improves security and reduces unauthorized access attempts.
-----------------------------------------------------------------------------------------------------
4. Find out which Linux distribution and version is running on the instance.
---
Ans:
See below are the Linux distribution and Version details.
![ṣ](image-10.png)
---Commands:
cat /etc/os-release
cat /etc/os-release |grep VERSION
uname -a
---------------------------
[ec2-user@ip-172-31-45-137 ~]$ cat /etc/os-release
NAME="Amazon Linux"
VERSION="2023"
ID="amzn"
ID_LIKE="fedora"
VERSION_ID="2023"
PLATFORM_ID="platform:al2023"
PRETTY_NAME="Amazon Linux 2023.12.20261102"
ANSI_COLOR="0;33"
CPE_NAME="cpe:2.3:o:amazon:amazon_linux:2023"
HOME_URL="https://aws.amazon.com/linux/amazon-linux-2023/"
DOCUMENTATION_URL="https://docs.aws.amazon.com/linux/"
SUPPORT_URL="https://aws.amazon.com/premiumsupport/"
BUG_REPORT_URL="https://github.com/amazonlinux/amazon-linux-2023"
VENDOR_NAME="AWS"
VENDOR_URL="https://aws.amazon.com/"
SUPPORT_END="2029-06-30"

[ec2-user@ip-172-31-45-137 ~]$ cat /etc/os-release |grep VERSION
VERSION="2023"
VERSION_ID="2023"

[ec2-user@ip-172-31-45-137 ~]$ uname -a
Linux ip-172-31-45-137.ap-south-2.compute.internal 6.18.56-125.164.amzn2023.x86_64 #2 SMP PREEMPT_DYNAMIC Mon Oct 19 19:39:29 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux
[ec2-user@ip-172-31-45-137 ~]$
---------------
The command displayed operating system details.
The instance is running Amazon Linux 2023.
Knowing OS details helps while installing software and troubleshooting issues.
-------------------------------------------------------------------------------------------
5. Delete the instance, Security Group, and key pair.
---
Ans:
Deleted EC2 instance, Security Group and Key Pair successfully.
Unused resources should be removed to avoid unnecessary AWS cost and improve security.
Below is the evidence.

===============================================================================================
## Assignment — Linux File Operations
1. Create the following directory structure using a single command:
   ```
   devops/
   └── projects/
       └── batch-90s/
---
Ans:
-------------------------------On windows machine
Created directory structure using a single command.
Option -p automatically creates parent directories if they do not exist.
![ṣ](image-11.png)

--Command i used here is,
mkdir -p devops/projects/batch-90s/
find devops -type d
cmd //c "tree devops"
-----------------------------------
lovel@VENISHAMUMMY UCRT64 ~
$ mkdir -p devops/projects/batch-90s/

lovel@VENISHAMUMMY UCRT64 ~
$ find devops -type d
devops
devops/projects
devops/projects/batch-90s

lovel@VENISHAMUMMY UCRT64 ~
$ cmd //c "tree devops"
Folder PATH listing for volume Windows-SSD
Volume serial number is 9A64-3365
C:\USERS\LOVEL\DEVOPS
└───projects
    └───batch-90s

lovel@VENISHAMUMMY UCRT64 ~
$ date
Sun Nov  1 09:19:41 IST 2026
lovel@VENISHAMUMMY UCRT64 ~
$
-----------------------------On EC2 Linux Instance or Server
[ec2-user@ip-172-31-45-137 ~]$ pwd
/home/ec2-user
[ec2-user@ip-172-31-45-137 ~]$ mkdir -p devops/projects/batch-90s

[ec2-user@ip-172-31-45-137 ~]$ find devops -type d
devops
devops/projects
devops/projects/batch-90s

[ec2-user@ip-172-31-45-137 ~]$ ls -R devops
devops:
projects
devops/projects:
batch-90s
devops/projects/batch-90s:
[ec2-user@ip-172-31-45-137 ~]$
=======================================================================================
2. Inside `batch-90s/`, create a file called `notes.txt`. Write three lines into it, then append two more. Read it to verify.
---
Ans:
-Commands
cat > notes.txt << EOF
cat >> notes.txt << EOF
cat notes.txt
----------------------------------
[ec2-user@ip-172-31-45-137 batch-90s]$ cat > notes.txt << EOF
> Hi, I am Gopi Krishna and i am learning DevOps Course.
Now, I am trying to complete the Linux assignments.
It will increase my confidence levels.
> EOF

[ec2-user@ip-172-31-45-137 batch-90s]$ cat notes.txt
Hi, I am Gopi Krishna and i am learning DevOps Course.
Now, I am trying to complete the Linux assignments.
It will increase my confidence levels.
[ec2-user@ip-172-31-45-137 batch-90s]$
---
[ec2-user@ip-172-31-45-137 batch-90s]$ cat >> notes.txt << EOF
> I am very greatful to learn this course from one of the top most experienced tutor.
> I want to switch into devops domain from administrator domain.
> EOF
---
[ec2-user@ip-172-31-45-137 batch-90s]$ cat notes.txt
Hi, I am Gopi Krishna and i am learning DevOps Course.
Now, I am trying to complete the Linux assignments.
It will increase my confidence levels.
I am very greatful to learn this course from one of the top most experienced tutor.
I want to switch into devops domain from administrator domain.
[ec2-user@ip-172-31-45-137 batch-90s]$ date
Sun Nov  1 04:21:01 UTC 2026
[ec2-user@ip-172-31-45-137 batch-90s]$
---------------------------
Created notes.txt file and inserted data successfully.
Using (cat > notes.txt << EOF) >>>>> creates the content.
Using (cat >> notes.txt << EOF) >>>> appends data without deleting existing information.
using (cat notes.txt) >>>>> to see the content inside the file.
-------------------------------------------------------------------------------------------------
3. Copy `notes.txt` to `projects/` and rename the copy to `backup.txt`. Verify both exist.
---
Ans:
--Commands:
cp notes.txt /home/ec2-user/devops/projects/ ---copying/moving the file into 'projects' folder.
ls /home/ec2-user/devops/projects ---to check the contenets/verify the file moved or not.
cp notes.txt backup.txt ---Make a copy of the file(like backup)
mv notes.txt backup.txt ---renaming the file.
------------
[ec2-user@ip-172-31-45-137 batch-90s]$ pwd
/home/ec2-user/devops/projects/batch-90s

[ec2-user@ip-172-31-45-137 batch-90s]$ ll
total 4
-rw-r--r--. 1 ec2-user ec2-user 293 Nov  1 04:20 notes.txt

[ec2-user@ip-172-31-45-137 batch-90s]$ cp notes.txt /home/ec2-user/devops/projects/

[ec2-user@ip-172-31-45-137 projects]$ ls /home/ec2-user/devops/projects
backup.txt  batch-90s
[ec2-user@ip-172-31-45-137 batch-90s]$ cd /home/ec2-user/devops/projects

[ec2-user@ip-172-31-45-137 projects]$ ll
total 4
drwxr-xr-x. 2 ec2-user ec2-user  23 Nov  1 04:48 batch-90s
-rw-r--r--. 1 ec2-user ec2-user 293 Nov  1 04:49 notes.txt

[ec2-user@ip-172-31-45-137 projects]$ cp notes.txt backup.txt

[ec2-user@ip-172-31-45-137 projects]$ ll
total 8
-rw-r--r--. 1 ec2-user ec2-user 293 Nov  1 04:50 backup.txt
drwxr-xr-x. 2 ec2-user ec2-user  23 Nov  1 04:48 batch-90s
-rw-r--r--. 1 ec2-user ec2-user 293 Nov  1 04:49 notes.txt
[ec2-user@ip-172-31-45-137 projects]$ mv notes.txt backup.txt

[ec2-user@ip-172-31-45-137 projects]$ ll
total 4
-rw-r--r--. 1 ec2-user ec2-user 293 Nov  1 04:49 backup.txt
drwxr-xr-x. 2 ec2-user ec2-user  23 Nov  1 04:48 batch-90s
[ec2-user@ip-172-31-45-137 projects]$
---------------------------------------------------------------------------------------------------
4. Move `backup.txt` to `/tmp/`. What happens to files there when the server restarts?
---
Ans: backup.txt file was successfully moved to /tmp directory.
------------------------
[ec2-user@ip-172-31-45-137 projects]$ mv backup.txt /tmp

[ec2-user@ip-172-31-45-137 projects]$ cd /tmp
[ec2-user@ip-172-31-45-137 tmp]$ ll
total 4
-rw-r--r--. 1 ec2-user ec2-user 293 Nov  1 04:49 backup.txt
--------------------------
What happens to files there when the server restarts?
Ans: 
The /tmp directory is used for temporary storage and files may be removed automatically during reboot or cleanup operations.
--------------------------------------------------------------------------------------------------
5. Delete the `devops/` directory and everything inside it.
---
Ans:
--command:
rm -rf devops
ls devops
ll
----------------------------------
[ec2-user@ip-172-31-45-137 ~]$ pwd
/home/ec2-user

[ec2-user@ip-172-31-45-137 ~]$ ls devops
projects

[ec2-user@ip-172-31-45-137 ~]$ ls devops/projects
batch-90s

[ec2-user@ip-172-31-45-137 ~]$ ls devops/projects/batch-90s
notes.txt

[ec2-user@ip-172-31-45-137 ~]$ rm -rf devops

[ec2-user@ip-172-31-45-137 ~]$ ls devops
ls: cannot access 'devops': No such file or directory

[ec2-user@ip-172-31-45-137 ~]$ ll
total 0

[ec2-user@ip-172-31-45-137 ~]$ date
Sun Nov  1 05:03:10 UTC 2026
[ec2-user@ip-172-31-45-137 ~]$
---------------------------------------
Deleted complete directory structure and all files inside it.
Option -r removes directories recursively and -f forces deletion without confirmation.
-----------------------------------------------------------------------------------------------
6. List the contents of `/var/log/` sorted by time. What do you notice? Why would a DevOps engineer check this directory?
---
Ans:
-Command
ls -ltr /var/log or ls -ltr `/var/log/`
----------------------------------
[ec2-user@ip-172-31-45-137 ~]$ ls -ltr /var/log/
total 180
drwxr-x---. 2 root   root                 6 Jul 14 17:05 sssd
-rw-------. 1 root   root                 0 Oct 30 02:01 tallylog
lrwxrwxrwx. 1 root   root                39 Oct 30 02:01 README -> ../../usr/share/doc/systemd/README.logs
drwx------. 2 root   root                 6 Oct 30 02:01 private
-rw-rw----. 1 root   utmp                 0 Oct 30 02:01 btmp
drwxr-sr-x+ 3 root   systemd-journal     46 Nov  1 02:45 journal
drwx------. 2 root   root                23 Nov  1 02:45 audit
drwxr-xr-x. 2 root   root                18 Nov  1 02:45 sa
drwxr-xr-x. 3 root   root                17 Nov  1 02:45 amazon
-rw-r-----. 1 root   adm               3686 Nov  1 02:45 cloud-init-output.log
-rw-r-----. 1 root   adm             149861 Nov  1 02:45 cloud-init.log
-rw-r--r--. 1 root   root                58 Nov  1 02:45 dnf.rpm.log
-rw-r--r--. 1 root   root                60 Nov  1 02:45 hawkey.log
-rw-r--r--. 1 root   root              1181 Nov  1 02:45 dnf.log
-rw-r--r--. 1 root   root              1698 Nov  1 02:45 dnf.librepo.log
drwxr-x---. 2 chrony chrony              72 Nov  1 02:45 chrony
-rw-rw-r--. 1 root   utmp              4224 Nov  1 03:59 wtmp
-rw-rw-r--. 1 root   utmp            292292 Nov  1 03:59 lastlog

[ec2-user@ip-172-31-45-137 ~]$ ls -ltr '/var/log/'
total 180
drwxr-x---. 2 root   root                 6 Jul 14 17:05 sssd
-rw-------. 1 root   root                 0 Oct 30 02:01 tallylog
lrwxrwxrwx. 1 root   root                39 Oct 30 02:01 README -> ../../usr/share/doc/systemd/README.logs
drwx------. 2 root   root                 6 Oct 30 02:01 private
-rw-rw----. 1 root   utmp                 0 Oct 30 02:01 btmp
drwxr-sr-x+ 3 root   systemd-journal     46 Nov  1 02:45 journal
drwx------. 2 root   root                23 Nov  1 02:45 audit
drwxr-xr-x. 2 root   root                18 Nov  1 02:45 sa
drwxr-xr-x. 3 root   root                17 Nov  1 02:45 amazon
-rw-r-----. 1 root   adm               3686 Nov  1 02:45 cloud-init-output.log
-rw-r-----. 1 root   adm             149861 Nov  1 02:45 cloud-init.log
-rw-r--r--. 1 root   root                58 Nov  1 02:45 dnf.rpm.log
-rw-r--r--. 1 root   root                60 Nov  1 02:45 hawkey.log
-rw-r--r--. 1 root   root              1181 Nov  1 02:45 dnf.log
-rw-r--r--. 1 root   root              1698 Nov  1 02:45 dnf.librepo.log
drwxr-x---. 2 chrony chrony              72 Nov  1 02:45 chrony
-rw-rw-r--. 1 root   utmp              4224 Nov  1 03:59 wtmp
-rw-rw-r--. 1 root   utmp            292292 Nov  1 03:59 lastlog
[ec2-user@ip-172-31-45-137 ~]$
----------------------------------
-What do you notice?
Ans: 
Log files are continuously updated by Linux services and applications.
-Why would a DevOps engineer check this directory?
Ans:
DevOps engineers check this location for troubleshooting, service failures and system activity investigations.
================================================================================================
---
## Assignment — Linux Text Processing
Create a file with this content:
```
web-server-01 192.168.1.10 running
web-server-02 192.168.1.11 stopped
db-server-01  192.168.1.20 running
db-server-02  192.168.1.21 running
cache-server  192.168.1.30 stopped
```
Write a command for each:
------------------------------
[ec2-user@ip-172-31-45-137 ~]$ awk "{print $2}" servers.txt
web-server-01 192.168.1.10 running
web-server-02 192.168.1.11 stopped
db-server-01  192.168.1.20 running
db-server-02  192.168.1.21 running
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$ awk "{print $1}" servers.txt
web-server-01 192.168.1.10 running
web-server-02 192.168.1.11 stopped
db-server-01  192.168.1.20 running
db-server-02  192.168.1.21 running
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$
-------------------------------Explanation---------------------
Issue:
I used double quotes instead of single quotes in awk command.
Wrong:
awk "{print $2}" servers.txt
Correct:
awk '{print $2}' servers.txt
Reason:
Inside double quotes, shell tries to interpret $1, $2 as shell variables before passing them to awk.
Using single quotes passes the awk program exactly as written to awk.
--------------------------------

1. Show only lines where the server is `running`.
---
Ans:
-commands
grep running servers.txt
cat servers.txt |grep running
---------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ grep running servers.txt
web-server-01 192.168.1.10 running
db-server-01  192.168.1.20 running
db-server-02  192.168.1.21 running
[ec2-user@ip-172-31-45-137 ~]$ cat servers.txt |grep running
web-server-01 192.168.1.10 running
db-server-01  192.168.1.20 running
db-server-02  192.168.1.21 running
[ec2-user@ip-172-31-45-137 ~]$
----------------------------------------------
2. Show only lines where the server is NOT `running`.
---
Ans:
-command:
grep -v running servers.txt
cat servers.txt |grep -v running
-----------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ grep -v running servers.txt
web-server-02 192.168.1.11 stopped
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$ cat servers.txt |grep -v running
web-server-02 192.168.1.11 stopped
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$
-----------------------------------------------
3. Count how many servers are `running`.
---
Ans:
-command:
grep running servers.txt |wc -l
cat servers.txt |grep running |wc -l
----------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ grep running servers.txt |wc -l
3
[ec2-user@ip-172-31-45-137 ~]$ cat servers.txt |grep running |wc -l
3
[ec2-user@ip-172-31-45-137 ~]$
----------------------------------------------
4. Show the first 3 lines. Then show the last 2.
---
Ans:
-Commands:
cat servers.txt |head -3
head -3 servers.txt
-
cat servers.txt |tail -2
tail -2 servers.txt
---------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ cat servers.txt |head -3
web-server-01 192.168.1.10 running
web-server-02 192.168.1.11 stopped
db-server-01  192.168.1.20 running
[ec2-user@ip-172-31-45-137 ~]$ head -3 servers.txt
web-server-01 192.168.1.10 running
web-server-02 192.168.1.11 stopped
db-server-01  192.168.1.20 running
[ec2-user@ip-172-31-45-137 ~]$
----------
[ec2-user@ip-172-31-45-137 ~]$ cat servers.txt |tail -2
db-server-02  192.168.1.21 running
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$ tail -2 servers.txt
db-server-02  192.168.1.21 running
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$
----------------------------------------------
5. Extract only the IP addresses.
---
Ans:
-command:
awk '{print}' servers.txt
awk '{print $2}' servers.txt
------
awk command extracted the second column from every line.
This is useful when creating server inventories or checking network information
----------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ awk '{print}' servers.txt
web-server-01 192.168.1.10 running
web-server-02 192.168.1.11 stopped
db-server-01  192.168.1.20 running
db-server-02  192.168.1.21 running
cache-server  192.168.1.30 stopped
[ec2-user@ip-172-31-45-137 ~]$ awk '{print $2}' servers.txt
192.168.1.10
192.168.1.11
192.168.1.20
192.168.1.21
192.168.1.30
--------------------------------------------------
6. Extract only the server names.
---
Ans:
-command:
awk '{print $1}' servers.txt
-------
awk extracted the first column from each record.
This helps when preparing reports or filtering specific servers for administration activities.
-------------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ awk '{print $1}' servers.txt
web-server-01
web-server-02
db-server-01
db-server-02
cache-server
[ec2-user@ip-172-31-45-137 ~]$ 
----------------------------------------------------
7. Show only the names of `stopped` servers — in one command.
---
Ans:
-command:
awk '$3=="stopped" {print $1}' servers.txt
awk '$3=="stopped" {print $1,$3}' servers.txt
----
awk can filter and extract information in a single command.
Filtered stopped servers and displayed only their names and thier status too.
---------------------------------------------------
[ec2-user@ip-172-31-45-137 ~]$ awk '$3=="stopped" {print $1}' servers.txt
web-server-02
cache-server
[ec2-user@ip-172-31-45-137 ~]$ awk '$3=="stopped" {print $1,$3}' servers.txt
web-server-02 stopped
cache-server stopped
[ec2-user@ip-172-31-45-137 ~]$
==============================================================================================
---
## Assignment — wget, curl, and Pipes

1. Download the following file to your EC2 instance and save it as `session-notes.txt`:
   ```
   https://raw.githubusercontent.com/daws-90s/notes/refs/heads/main/session-02.txt
   ```

2. Fetch the same file using `curl` and count its lines — without saving it to disk.

3. Fetch the file and print only lines containing `Linux` — in one command.

4. Run this and explain what `$NF` means:
   ```bash
   echo "https://raw.githubusercontent.com/daws-90s/notes/refs/heads/main/session-02.txt" | awk -F "/" '{print $NF}'
   ```

5. Fetch the file, filter lines containing `ssh`, then count how many matched — using two pipes.

---

## Assignment — /etc/passwd Deep Dive

1. How many user accounts exist on the system?


2. Extract only the usernames.

3. Show only users with UID greater than 999.

4. Find the entry for `ec2-user`. What is their home directory?

5. List all unique login shells assigned to users on the system.

---

## Assignment — Vim Editor

1. Create `practice.txt` using vim. Add 10 lines of content, save and exit.

2. Open the file. Turn on line numbers, jump to line 7, delete line 3, save and exit.

3. Open the file. Search for a word, move through its occurrences, then clear the highlight.

4. Replace every occurrence of one word in the file with another — in one command.

5. Go to the bottom of the file, add 3 lines, then undo the last one. Save.

6. Copy one line and paste it 5 times in a single step. What is the command?

---

## Assignment — Linux User Management

1. Create a user `alice`. What primary group was automatically created for her?

2. Set a password for `alice`. Configure the server to allow password-based SSH and connect as `alice`.

3. Create a group `devops-team`. Add `alice` as a secondary member. Verify.

4. Create a user `bob`. Add both `alice` and `bob` to `devops-team`.

5. Give `alice` sudo access. Verify she can run commands as root.

6. Remove `alice`'s sudo access. Confirm she can no longer run sudo commands.

7. Add a rule to `/etc/sudoers` that allows only `devops-team` to run `useradd` and `usermod` — nothing else.

---

## Assignment — File Permissions and Ownership

1. Create `secret.txt` with some content. Who can read it by default?

2. Restrict it so only the owner can read and write. Switch to another user and try to read it — what happens?

3. Create `deploy.sh` with one line of content. Make it executable by the owner only. What numeric value represents owner read+write+execute?

4. Create `shared/`. Owner has full access, group can read and execute, others have none — set this in numeric form.

5. Change the owner of `secret.txt` to `alice` and the group to `devops-team`.

6. Create `project/` with 3 files inside. Change ownership of everything in it to `alice:devops-team` in one command.

7. Check the permissions on `/etc/shadow`. Why is it set that way?

---

## Assignment — Key-Based SSH for a New User

1. Create a user `deploy` with no password.

2. Generate a new SSH key pair for this user on your local machine.

3. Set up `.ssh/` and `authorized_keys` on the server for `deploy` with the correct permissions and ownership.

4. Connect to the server as `deploy` using the private key.

5. Try connecting without specifying the key. What happens and why?

6. Disable password authentication on the server. Verify that a password login is rejected. Why does this matter for production?

---

> If a command fails, read the error carefully — it usually tells you what is wrong. Search if needed. Bring questions to the Q&A session.
