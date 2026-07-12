# Lab 3b-2 -- Additional Server Services

### System Preparation

The commands I used were:

```Bash
sudo apt clean
sudo apt update
sudo apt upgrade -y
```

Firsly I ran into a problem when upgrading it kept on showing Error 403 Forbidden.

<img width="1213" height="63" alt="image" src="https://github.com/user-attachments/assets/174b1ceb-2ee2-4c8a-9bf1-9c8f978c9db7" />

However, I found that Ubuntu was using Indonesia mirror which is out of sync when I am currently in Singapore. Therefore I ran `sudo nano /etc/apt/sources.list.d/ubuntu.sources` and change the URI to http://archive.ubuntu.com/ubuntu instead of http://id.archive.ubuntu.com/ubuntu

<img width="1207" height="733" alt="image" src="https://github.com/user-attachments/assets/187613e4-4987-4fa0-be61-55382e089fd9" />

After I changed the URI, I continued to execute the commands which were successfully executed.

<img width="410" height="199" alt="image" src="https://github.com/user-attachments/assets/f99f2de8-1b31-4983-83c8-c8c78c830ec6" />

<img width="575" height="346" alt="image" src="https://github.com/user-attachments/assets/8ff390f3-6190-4252-98ab-84547944ba0b" />

### Install MariaDB (Database Server) 

```Bash
sudo apt install -y mariadb-server mariadb-client
sudo systemctl start mariadb 
sudo systemctl enable mariadb
sudo mariadb-secure-installation

sudo mysql -u root -p
```
MariaDB Installation:

<img width="589" height="352" alt="image" src="https://github.com/user-attachments/assets/71e357cd-a866-41db-bf04-3bb9db6c4907" />

<img width="454" height="342" alt="image" src="https://github.com/user-attachments/assets/2dc6786b-069a-45ae-9bef-bb870c340b80" />

<img width="356" height="323" alt="image" src="https://github.com/user-attachments/assets/b18242bd-4350-4636-8ba8-7e7a7cb9956d" />

This picture shows the verification:

<img width="488" height="211" alt="image" src="https://github.com/user-attachments/assets/f0052be2-6659-4b92-8a51-996e5d162804" />




