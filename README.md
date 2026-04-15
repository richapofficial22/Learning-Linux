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
-














 







