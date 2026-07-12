# Lab 1b-2 -- Linux File Permissions and Group Access Control 

In this lab is to acquire foundational skill to manage multi-user system securely.

### Three Users Created

First, I created 3 users named Alice, Bob, and Mallory.

The commands I used:

```Bash
sudo adduser alice
sudo adduser bob
sudo adduser mallory
```
<img width="2048" height="1156" alt="image" src="https://github.com/user-attachments/assets/cc2747d6-264b-4ded-a55b-b7b1f2e4673f" />

After creating the users, I verified the user creation using `less /etc/passwd`

<img width="2048" height="160" alt="image" src="https://github.com/user-attachments/assets/4b8edc25-8d7d-43ca-bf17-24c7797ab5af" />

### Group Created and Configured

Created a group named `sharedgroup` using the command `sudo groupadd sharedgroup` Then continued by adding user Alice and Bob. By using `sudo adduser user sharedgroup` and gave both owner and group full access `sudo chmod -R 770 /home/shared`

<img width="1771" height="166" alt="image" src="https://github.com/user-attachments/assets/aa01f433-cf99-4a81-b181-053b51716621" />

Then I continued to verify using `less /etc/group`

<img width="2048" height="1100" alt="image" src="https://github.com/user-attachments/assets/6c37bc3c-96ef-444e-85db-cbd073bdd885" />

### 'shared' Directory Created in /home/

I started by creating a directory of file named 'shared' in /home/ I also changed the ownership and group of the file by using these commands:

```Bash
sudo mkdir /home/shared
sudo chown novie/home/shared
sudo chgrp sharedgroup/home/shared
ls -ld /home/shared
```

<img width="1747" height="1006" alt="image" src="https://github.com/user-attachments/assets/971325bb-86be-4d57-a45c-bbfac0a9f107" />

Pictures shown that I have changed the ownership of the file and also allowed the member of `sharedgroup` to have access to the file. All of these are verified using `ls -ld /home/shared/`

### Ten Files Created in 'shared' Folder

I created 10 files using `sudo touch /home/shared/file` and continuosly entering 10 files. 

<img width="1843" height="1111" alt="image" src="https://github.com/user-attachments/assets/6e689a8e-3faa-4936-9e98-28b143521d05" />

Picture shown than I have made 10 files and using `ls -l /home/shared` to verify that the 10 files exist in the 'shared' folder.

### Permission Assigned Properly

Here are the commands I used:

```Bash
sudo chown -R alice:sharedgroup /home/shared
sudo chgrp -R sharedgroup /home/shared
sudo chmod -R 750 /home/shared
su - alice
ls -l /home/shared
```
First I changed the owner of the group to Alice then I continued to swtich user to Alice so I could get the data of the folder.

<img width="1799" height="1090" alt="image" src="https://github.com/user-attachments/assets/656dc9fb-be23-4432-bd4a-b07e35582114" />

Picture shown that Alice is the owner `rwx`.

### Access Verified as Each User

First I logged in as Alice using these commands:

```Bash
su - alice
whoami
ls /home/shared
echo "Hello!" > /home/shared/file1
cat /home/shared/file1
```

<img width="1698" height="783" alt="image" src="https://github.com/user-attachments/assets/6e7e5bc6-25b2-4c91-8efb-55c679403e70" />

Then I logged in as bob using these commands: 

```Bash
su - bob
whoami
ls /home/shared
echo "Hello!" > /home/shared/file1
cat /home/shared/file1
```

<img width="1421" height="656" alt="image" src="https://github.com/user-attachments/assets/8eb91fcb-0a2d-43e5-96bb-d9333f4dab19" />

Then I logged in as Mallory using these commands: 

```Bash
su - mallory
whoami
ls /home/shared
```

<img width="1697" height="783" alt="image" src="https://github.com/user-attachments/assets/acafd829-72e5-4ddd-a9cf-74094b9fc6d2" />

From accessing each user it shows that Alice as the owner, is allowed to view and edit, while Bob could only view the file, and Mallory is not allowed to access the file at all.

### Use of chmod/chown/chgrp -R 

Here are the commands I used:

```Bash
sudo chown -R alice:sharedgroup /home/shared
sudo chgrp -R sharedgroup /home/shared
sudo chmod -R 750 /home/shared
```

<img width="1799" height="238" alt="image" src="https://github.com/user-attachments/assets/0efbe199-83a6-4131-88b6-245e8392469a" />

Picture shown is confirming use of recursive flag.

### Mallory Added to Sudoers (Challenge) 

<img width="1954" height="1290" alt="image" src="https://github.com/user-attachments/assets/1e7bbc0a-76ad-47e3-adce-44ef52ee51c4" />

Picture shown is the proof Mallory had been added to sudoers.

### Effect of Sudo Access for Mallory Tested 

<img width="1600" height="946" alt="image" src="https://github.com/user-attachments/assets/42d90f26-4e2c-477d-b433-9740ca32283b" />

Picture shown that Mallory can do things that only sudo can do.

### Folder Clean-Up Performed

<img width="1600" height="256" alt="image" src="https://github.com/user-attachments/assets/8479b717-e7a2-4f35-87e5-dffd05009e5e" />

Picture shown confirmed deletion of shared directory and its content.

# Conclusion

This activity demonstrated how Linux file ownership, groups, and permissions control user access to files and directories. By using Alice, Bob, and Mallory, I learned how commands such as chmod, chown, and chgrp can assign different access levels, while su and whoami help verify user permissions. Overall, the exercise highlighted the importance of proper permission management in protecting files and maintaining system security.

# Reflection

This activity showed that Linux uses a simple owner, group, and others permission model, while Windows ACL provides more detailed and flexible access control. I learned that chmod 770 allows both the owner and group to read, write, and execute, whereas chmod 750 removes write permission from the group and denies all access to others. Adding users to the sudo group should be done carefully because it grants administrative privileges that could affect system security. Using su and whoami is important to confirm the active user and verify that permissions are working as intended.
















