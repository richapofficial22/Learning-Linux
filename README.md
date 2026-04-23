# Learning-Linux
# Learning-Linux-using-Docker-container
### Started with Complete Linux Course with Networking and Shell Scripting by Abhishek Veeramalla
- Source : https://www.youtube.com/watch?v=29eDuMjsEF8
- Github repo for instructor notes : Ultimate Linux Guide - https://github.com/iam-veeramalla/ultimate-linux-guide
#
### Installed Docker desktop
### Created a folder in tmp 
- <img width="1425" height="135" alt="Screenshot 2026-04-14 at 11 55 31 AM" src="https://github.com/user-attachments/assets/af4b0962-4429-44f5-a095-166f1fd08a5c" />

- //Folder created to provide storage from my own laptop in case the linux container runs out of storage. If this folder also runs out of storage then the container also runs out of storage. 
### Used the following command on MacOS terminal to create Linux Container
  ```bash
docker run -dit \
  --name ubuntu-LinuxLearnings \
  --hostname ubuntu-dev \
  --restart unless-stopped \
  --cpus="2" \
  --memory="4g" \
  --mount type=bind,source=/tmp/data-folder,target=/data \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -p 2222:22 \
  -p 8080:80 \
  --env TZ=Asia/Kolkata \
  --env LANG=en_US.UTF-8 \
  ubuntu:latest /bin/bash
                 
```
### 
- <img width="577" height="243" alt="Screenshot 2026-04-14 at 11 56 42 AM" src="https://github.com/user-attachments/assets/1fb1f9c6-989c-408a-8f88-8b321bb318b3" />
### Linux container created using commands
- <img width="1440" height="900" alt="Screenshot 2026-04-14 at 11 57 58 AM" src="https://github.com/user-attachments/assets/706f8334-f282-46c3-90c4-c88ac0822dcc" />
### Checking the containers created
- <img width="1424" height="86" alt="Screenshot 2026-04-14 at 12 00 08 PM" src="https://github.com/user-attachments/assets/be3b67cd-0bf5-4d6c-8a3b-c79933a0391a" />
### Getting into the Linux container using the container id retrieved above
- <img width="1425" height="77" alt="Screenshot 2026-04-14 at 12 02 44 PM" src="https://github.com/user-attachments/assets/7d3074f6-d1bc-44fe-934e-8cd5ad82f0ad" />
### Running and updating the package in ubuntu: apt
- <img width="572" height="464" alt="Screenshot 2026-04-14 at 12 04 16 PM" src="https://github.com/user-attachments/assets/3114a0c8-79db-48e8-b89c-3e95292ab61b" />
### Updating the package installer
- <img width="726" height="430" alt="Screenshot 2026-04-14 at 12 06 52 PM" src="https://github.com/user-attachments/assets/449c1d70-4130-4eb0-8b2d-bdeb31b86a6d" />
### Upgrading the apt package
- <img width="812" height="531" alt="Screenshot 2026-04-14 at 12 07 17 PM" src="https://github.com/user-attachments/assets/6cabc23f-d0a4-430c-98cb-dd5a24cfdd7c" />
## 
### Here root is the user, ubuntu is the hostname, : is seperator and / is the path or current working directory
```bash 
  root@ubuntu-dev:/# 
```
### All the files and folders in the root directory 
```bash 
  root@ubuntu-dev:/# ls -ltr
```
- <img width="444" height="339" alt="Screenshot 2026-04-14 at 12 29 43 PM" src="https://github.com/user-attachments/assets/170cfa39-77c2-48e8-b76c-de18b4f5b0bd" />
##
### Creating user named 'user1'
- <img width="522" height="346" alt="Screenshot 2026-04-14 at 1 40 08 PM" src="https://github.com/user-attachments/assets/fa6d0302-8c8a-47bc-8c97-f97e7ece7842" />
### Setting password for user1-
- <img width="306" height="94" alt="Screenshot 2026-04-14 at 1 42 23 PM" src="https://github.com/user-attachments/assets/d9a5a73c-8c03-442c-83e5-802dcbec8a1c" />
### Checking if the password was actually created or not. It shows encrypted version of the password. This encrypted password is one way encryption and can not be decrypted. 
- <img width="741" height="334" alt="Screenshot 2026-04-14 at 1 43 50 PM" src="https://github.com/user-attachments/assets/988e971e-853f-4cd4-b0c2-4aedb3a1a51d" />
### Deleting user1 and checking if it has been deleted or not 
- <img width="515" height="352" alt="Screenshot 2026-04-14 at 1 49 20 PM" src="https://github.com/user-attachments/assets/1524596a-1da2-4707-b9d5-8f7db32d7d43" />
### There is a difference between useradd & adduser. useradd does not create a home directory for that user. Whereas adduser on getting created asks details to add that user into the home directory. useradd is mostly used while scripting so that unnecessary things can be skipped while adding user. 
- Here, Richa1 is not added in home directory
- <img width="297" height="92" alt="Screenshot 2026-04-14 at 1 53 56 PM" src="https://github.com/user-attachments/assets/c99358f9-6183-4edb-88ec-d8f026648fb9" />
- ********Glitch** : adduser command not found
- <img width="1428" height="467" alt="Screenshot 2026-04-14 at 1 58 24 PM" src="https://github.com/user-attachments/assets/f0961a76-5853-4a57-a61d-f9a50356ec7d" />
- installing adduser through apt
- <img width="717" height="399" alt="Screenshot 2026-04-14 at 1 59 11 PM" src="https://github.com/user-attachments/assets/e587fb06-72a1-42a8-891f-9e22cdc852ff" />
- Finally adduser is working. Created user named 'richie'
- <img width="591" height="423" alt="Screenshot 2026-04-14 at 2 09 06 PM" src="https://github.com/user-attachments/assets/64263479-00bc-4bac-abfd-f853a873d302" />
- User richie is showing in home directory
- <img width="259" height="66" alt="Screenshot 2026-04-14 at 2 13 22 PM" src="https://github.com/user-attachments/assets/ca727f93-103e-4fed-ade9-05f1264e5950" />
- *****Note:
  - 1.while using adduser the username cannot start with capital letter unlike useradd
  - 2.su - switching user
  - 3.userdel will not delete the user created using adduser command from home directory. can use rm -rf /home/username
  - 4.also passwd -l username prevents user from accessing account using password.
  - 5.chage -M 90 : change password in 90 days
##
### Created 2 groups
- <img width="395" height="726" alt="Screenshot 2026-04-14 at 7 56 38 PM" src="https://github.com/user-attachments/assets/cd37c7ad-8bbd-44a0-9b29-a356a65d0e26" />
### Successfully added R1,R2,R3 users to rgroup
- <img width="319" height="740" alt="Screenshot 2026-04-14 at 8 00 52 PM" src="https://github.com/user-attachments/assets/e9662edc-10f9-445b-ba90-e317a676ff12" />
### Creating folder, files in tmp directory
- <img width="330" height="177" alt="Screenshot 2026-04-15 at 8 16 12 AM" src="https://github.com/user-attachments/assets/1f3ecd3e-0ae2-482d-87ca-d7b095004f55" />
### Deleting the created file and folder
- ******Note: file can also be created using vim command
- <img width="363" height="130" alt="Screenshot 2026-04-15 at 8 24 47 AM" src="https://github.com/user-attachments/assets/93f5e3cd-0c33-4288-8110-22085df33b9b" />
### Writing to a file and viewing it 
- <img width="719" height="249" alt="Screenshot 2026-04-15 at 8 40 59 AM" src="https://github.com/user-attachments/assets/d13e9933-1a26-497f-b5ba-7ca37244777b" />
### Used few other commands with the file (head, tail, echo)
- <img width="750" height="273" alt="Screenshot 2026-04-15 at 8 43 41 AM" src="https://github.com/user-attachments/assets/e434a132-37ae-4162-ab59-3f2dfde7dd72" />
##
### 
Created 2 users userread & userwrite. Userwrite has a script file that userread can view and read. 
But on saving this file after editing the userread is not allowed to do the changes to it. Userread is not even allowed to delete the file. 
Hence, it shows that Linux comes with default file permissions. 
- <img width="721" height="221" alt="Screenshot 2026-04-15 at 9 09 06 AM" src="https://github.com/user-attachments/assets/da20a0be-7165-4289-b6d5-1373b9e61f41" />
- <img width="528" height="210" alt="Screenshot 2026-04-15 at 9 14 26 AM" src="https://github.com/user-attachments/assets/d751b1bd-bfc1-493b-89b8-4ce18fd19077" />
- <img width="393" height="861" alt="Screenshot 2026-04-15 at 9 17 05 AM" src="https://github.com/user-attachments/assets/f0a7d705-3d84-4d5d-bfa4-b244564437fb" />
- <img width="504" height="139" alt="Screenshot 2026-04-15 at 9 21 51 AM" src="https://github.com/user-attachments/assets/df4fdd8e-9be0-4415-93aa-46e507e29f59" />
### Doing modifications in the file permissions and understanding the concept behind it.
- <img width="851" height="340" alt="Screenshot 2026-04-15 at 9 34 39 AM" src="https://github.com/user-attachments/assets/2ab73371-6f96-4f0e-a61f-0270d1554d14" />
- <img width="469" height="172" alt="Screenshot 2026-04-15 at 9 30 16 AM" src="https://github.com/user-attachments/assets/12f7f74a-52d7-465e-9acb-53ead02d39c6" />
- <img width="480" height="119" alt="Screenshot 2026-04-15 at 9 30 38 AM" src="https://github.com/user-attachments/assets/31e702bd-00b8-4ecb-9ce5-955d6ae31c84" />
- <img width="1337" height="332" alt="Screenshot 2026-04-15 at 9 43 08 AM" src="https://github.com/user-attachments/assets/7344baa8-b834-4be7-9049-fe063542d734" />
### Checking if a user who created a folder and file within it is allowed to use the file if the root user changes the folder permissions
- <img width="429" height="204" alt="Screenshot 2026-04-15 at 11 32 29 AM" src="https://github.com/user-attachments/assets/5dbb774d-4887-4d66-b7fc-79ee84ccd745" />
- <img width="399" height="161" alt="Screenshot 2026-04-15 at 11 35 37 AM" src="https://github.com/user-attachments/assets/871387e6-0361-4fac-ab5e-f43a3a8215fb" />
- <img width="431" height="243" alt="Screenshot 2026-04-15 at 11 37 12 AM" src="https://github.com/user-attachments/assets/31a215c6-76c6-4117-a53c-8683dff13d59" />
### Changing the owner of folder from one user to another
- <img width="535" height="113" alt="Screenshot 2026-04-15 at 11 40 09 AM" src="https://github.com/user-attachments/assets/f666d08d-fe57-434c-84a2-4814829f31ff" />
### Checking the process running in my linux docker container. Killing the process using the PID. Using renice to change the priority of the process. top to monitor the system processes. Installed htop package using apt and then ran it. 
- <img width="580" height="232" alt="Screenshot 2026-04-16 at 9 10 18 AM" src="https://github.com/user-attachments/assets/2e906e8d-2065-485e-8742-e69cbeca658a" />
- <img width="559" height="155" alt="Screenshot 2026-04-16 at 9 14 17 AM" src="https://github.com/user-attachments/assets/b907af3d-ab0c-4606-9a01-4fda0e8d769a" />
- <img width="676" height="151" alt="Screenshot 2026-04-16 at 9 32 13 AM" src="https://github.com/user-attachments/assets/4970fd19-0456-4227-af5e-7c69d68cec95" />
- <img width="558" height="284" alt="Screenshot 2026-04-16 at 9 43 04 AM" src="https://github.com/user-attachments/assets/db16eb56-33bb-4766-8bea-47d48d752635" />
- <img width="707" height="176" alt="Screenshot 2026-04-16 at 9 45 01 AM" src="https://github.com/user-attachments/assets/26d25987-1877-4f40-a9cd-7aef66f7da9a" />
- <img width="886" height="666" alt="Screenshot 2026-04-16 at 9 49 15 AM" src="https://github.com/user-attachments/assets/85283e75-9b8a-41fc-87e7-9f64e6966d50" />
- <img width="1440" height="900" alt="Screenshot 2026-04-16 at 9 48 59 AM" src="https://github.com/user-attachments/assets/23be0974-0673-42b3-8b13-0e7a8f09a4f7" />
### Using vmstat to see system performance statistics. Using free -m & free -h to see memory usage . nproc to check how mant cpu's are running in my docker linux container. and finally seeing the disk usage using commands du -h & du -sh * 
- <img width="656" height="329" alt="Screenshot 2026-04-16 at 9 51 11 AM" src="https://github.com/user-attachments/assets/2166c0af-f2d2-4122-8a04-9eea17c7fa2b" />
- <img width="648" height="501" alt="Screenshot 2026-04-16 at 9 55 43 AM" src="https://github.com/user-attachments/assets/3edfc2f5-e929-4ead-b832-a38016c70cf8" />
- <img width="544" height="369" alt="Screenshot 2026-04-16 at 9 57 17 AM" src="https://github.com/user-attachments/assets/8fdd58e2-2a02-447e-8664-80d0125ec9c0" />

## 
### I also used EC2 instance to create linux server and run the process and systems commands on it. 
- <img width="1422" height="787" alt="Screenshot 2026-04-16 at 10 04 48 AM" src="https://github.com/user-attachments/assets/4c4e00d0-82ca-42ea-bd34-1f182310ef9a" />
- <img width="1440" height="900" alt="Screenshot 2026-04-15 at 12 50 50 PM" src="https://github.com/user-attachments/assets/8f66d6fa-e0d7-4cc4-92bc-467750cf6e8b" />
- <img width="1440" height="900" alt="Screenshot 2026-04-15 at 12 48 52 PM" src="https://github.com/user-attachments/assets/a202dbf1-55c1-4fcc-9d9e-1805a1b3481b" />
- <img width="1440" height="900" alt="Screenshot 2026-04-15 at 1 14 18 PM" src="https://github.com/user-attachments/assets/af151116-fbc3-4b68-b725-f355c65fd0a4" />
- <img width="1440" height="900" alt="Screenshot 2026-04-15 at 1 32 48 PM" src="https://github.com/user-attachments/assets/5bddff0a-a34b-4b71-b983-3fcce8896be7" />
##
### Checking disk storage on Linux instance using lbslk and fdisk -l
- <img width="1440" height="798" alt="Screenshot 2026-04-16 at 10 41 33 AM" src="https://github.com/user-attachments/assets/bad86390-d83d-4443-8635-a05be398d45f" />
- <img width="1440" height="778" alt="Screenshot 2026-04-16 at 10 42 49 AM" src="https://github.com/user-attachments/assets/4d029582-07be-4aa9-86ad-3423dd3d11a4" />
### Created 10gb block storage using EBS Volumes and attached to the current Linux instance. (**block only attaches if it is in same availability zone as the instance). This block storage needs to be mounted first and formated so that applications can run on it. 
- <img width="1434" height="786" alt="Screenshot 2026-04-16 at 10 48 54 AM" src="https://github.com/user-attachments/assets/f13ffb11-eda8-4fe9-a952-ffd596478f85" />
- <img width="629" height="271" alt="Screenshot 2026-04-16 at 10 53 37 AM" src="https://github.com/user-attachments/assets/c2a4a8fe-9350-41dd-8c57-240898e66603" />
- <img width="505" height="102" alt="Screenshot 2026-04-16 at 11 01 08 AM" src="https://github.com/user-attachments/assets/e80cf11c-9f81-4ce1-8822-5cb046ee090c" />
- <img width="647" height="252" alt="Screenshot 2026-04-16 at 11 03 58 AM" src="https://github.com/user-attachments/assets/0a24ccf4-3d03-4f33-8a40-593a4c16f7f4" />
- <img width="632" height="276" alt="Screenshot 2026-04-16 at 11 02 54 AM" src="https://github.com/user-attachments/assets/2177c61b-face-406e-ac6f-9d59159f01f8" />
- <img width="675" height="530" alt="Screenshot 2026-04-16 at 11 06 13 AM" src="https://github.com/user-attachments/assets/c210c33b-4a86-492e-8491-55b599f049ff" />
- <img width="607" height="389" alt="Screenshot 2026-04-16 at 11 11 51 AM" src="https://github.com/user-attachments/assets/76b05f06-a319-460c-9ecf-08c7756bb092" />
- unmount
- <img width="628" height="525" alt="Screenshot 2026-04-16 at 11 23 12 AM" src="https://github.com/user-attachments/assets/45cb7656-fe6d-454a-9489-50c681fe77d3" />
- detaching the volume
- <img width="1440" height="776" alt="Screenshot 2026-04-16 at 11 26 27 AM" src="https://github.com/user-attachments/assets/8907cada-f3d5-42b3-b00f-6b3609948b6c" />
- now my linux server is not showing the detached volume
- <img width="631" height="252" alt="Screenshot 2026-04-16 at 11 27 39 AM" src="https://github.com/user-attachments/assets/7e42c0ec-2986-4e7b-a9eb-b3e4f216c087" />








































##
- *******Notes:
   - ps -ef and ps aux : Aux gives cpu and memory utilisation
   - diff btw kill & kill -9 : -9 forcefully kills processesand doesn't show again 
   - kill -3 is to get threat dumps
   - kill -STOP to stop the process
   - kill -CONT to continue the stopped processes
   - renice check
   - service starts when server starta & they are different from the processes running
   - processes can be changed to services
   - top, htop to check the processes running
   - vmstat – Report system performance statistics (top is visual representation can't be used in scripts)
   - free -m & free -h : Show memory usage
   -  n-proc : Tells no. of cpu running in the machine
   -  disc space : du -h, du -sh * : gives disc utilisation of folder/directory
   -  On adding disks the apps don't start to run on them. First these added storage disks need to be mounted to the linux instance and then applications can run on them smoothly
   -  Also the volume that we create is of block storage. so it needs to be formatted to xfs or ext4.
   -  192, 172,10 are generally used for private subnets.. 8.8.8.8 is public IP address and is google's dns which is impossible to change.
   -  ports
   -  dns resolution > tcp handshake : usually called 3 ways handshake.
   -  3 way handshake: sync, sync-ack, ack. there is also 2 way and 4 way handshake. but to communicate a server 3-way handshake is enough.
   -  After dns and tcp handshake data request initiation happens
##

  ### OSI Model
 -  L7,L6, L5 are taken care by the browser itself. sender basically. 
 -  layer 7 : Application layer // Initiates communication
 -  layer 6 : Presentation layer // encryption  depending upon the certificates and https 
 -  layer 5 : Session layer // stored in cookies and cache
 -  layer 4 : Transport layer // segmentation of data and defining of protocol tcp or udp. if using http then tcp protocol if using dns then udp protocol
 -  layer 3 : Networking layer // Data is received by router that finds the shortest path and for this the source and destination IP addresses are both added..forming packets. 
 -  layer 2 : Data link layer //Routers are connected to switches. if you are using switches the data is converted into frames. For frames,mac information is also added.
 -  layer 1 : Physical layer //eod switches are connected to optical cables which understand electronic signals and help in fast transmission of data through cables.

 And after Layer 1 data traverses through multiple hops and finally reaches the server.

<img width="1088" height="655" alt="Screenshot 2026-04-16 at 3 25 00 PM" src="https://github.com/user-attachments/assets/0a135218-1572-43ed-b21a-4694b1317618" />

- TCP-IP Model: Layers 7,6,5 are combined as one unit. OSI model is the og standard model.
##
##

# Shell Scripting 
- Basically reducing manual activity we choose to automate anything. Doing automation on linux hosted machine is called shell scripting.
- Process of automating day to day activities on linux.
- <img width="979" height="325" alt="Screenshot 2026-04-16 at 3 56 29 PM" src="https://github.com/user-attachments/assets/577fdbf2-7473-4708-a711-9b9971b9bfc4" />
- vi vim work same . vim is better though.
- Even if the file is not created using touch command. we can directly create it using vim command. and the command directly opens the new file to modify it.
- Commom question why not use vim then? Bcox Touch command is used in automation. vim command opens the file to modify it which is why during automation process it cannot be used to create multiple files.
- Shebang #!/Bin/Bash : bash, dash,sh,ksh are different executables used to inform my linux OS that I am going to use it.
- sh vs bash : In sh the request is taken by sh but it is forwarded to bash using linking concept. used to happen earlier. we dont do it now. 
- ubuntu has started linking sh to dash. so it is very important to use bash while scripting. sh would not link to bash now.
- to execute a shell script we can use sh or ./
-  sh  reads the script line‑by‑line and executes it regardless of what  #!/bin/bash  (or a broken version of it) says
-  Linux is very strict regarding security. Before executing any script it wants to know that who all have permission to execute the script.
-  chmod : root user or admin or you / group / for others
- history command to see what commands have been used previously
- man command shows the details of the any other command
- pwd: to check the current working directory
- mkdir to make a directory , cd to change directory,

### 
Devops use Shell scripting for 3 things- Infrastructure maintenance, code management using git, configuration management
- pipe |  it sends output of the first command to the second command. eg. ps -ef | grep amazon
- if the first command is sending input to stdin then pipe won't be able to read the output
- set -x : gives which command was given
- Always write metadata info & write set -x
- set -e : exits the script when there is an error but it does not show error when there is a pipe hence we use set -o pipefail
- // set -e set -x set -o pipefail can also be written as set -exo pipefail
- when an application is failing you need to go on a logfile
- curl : retrieves information from internet
- wget downloads the file of which url was given
- curl vs wget
- find command :
- if , ifelse, for loop commands
- trap command : fo rtrapping signals.

##













































 





 







