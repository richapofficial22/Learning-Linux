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
















