# LAB 1b-1 -- Linux Services, SSH, Firewalls & Compression 

This activity is to expand the understanding of Linux as service host. By using Apache, SSH, network settings, firewall rules, user accounts, and use compression tools for trasnffering files.

First, I installed apache using:

```Bash
sudo apt install apache2
```
<img width="1662" height="995" alt="image" src="https://github.com/user-attachments/assets/16f01a97-7ef0-4d2c-a1c8-ae81afac4b4f" />

After that, I opened Firefox and tested 'hhtp://127.0.0.1'

<img width="1739" height="995" alt="image" src="https://github.com/user-attachments/assets/bd34f855-1816-4189-ab1c-3bf05589aa82" />

Photo shown the correct apacche2 operation after installation in ubuntu.

Next, installing SSH server and Nmap using:

```Bash
sudo apt install openssh-server map
```
Since I have installed SSH in the previous activity, only nmap will be installed.

<img width="1735" height="1021" alt="image" src="https://github.com/user-attachments/assets/67b3a933-649a-4803-996f-25b5d09a032e" />

Photo shown the installation of SSH (which I had already downloaded) and nmap.

By using `ip a` I will determine my IP address.

<img width="1136" height="262" alt="image" src="https://github.com/user-attachments/assets/0a8359ce-d953-4cfc-b296-2585b1a37ccf" />

Next activity is to edit index.html using nano/gedit using

```Bash
sudo nano /var/www/html/index.html
```
<img width="1660" height="1099" alt="image" src="https://github.com/user-attachments/assets/c803415d-3a48-4412-9d9f-c0ccfdb4a6af" />

Then I continued by editing the content 

<img width="1638" height="1039" alt="image" src="https://github.com/user-attachments/assets/8d3bd8fb-0b03-4409-8ea9-f5289f5ba2a7" />

After content created, I saved the file and open firefox to check. 

<img width="1692" height="1045" alt="image" src="https://github.com/user-attachments/assets/aeece777-4c2a-4251-8c4a-540d3f1d3e8b" />

As I did not have a partner for this activity, I accessed my own web server using its IP address '192.168.237.128' to verify that the webpage was hosted correctly and that my changes to index.html were successfully displayed.

Next I will scan nmap using `nmap [IP]` , and since I dont have a partner , I performed the nmap scan on my own virtual machine to identify the open ports and running services.

<img width="1696" height="1021" alt="image" src="https://github.com/user-attachments/assets/44da3978-b990-42b3-b52a-c275abb503e2" />

Next I will remove apache using:

```Bash
sudo apt remove apache2
```
<img width="1675" height="1075" alt="image" src="https://github.com/user-attachments/assets/a8ad17ea-808a-4fa3-870e-af020c298b18" />

After apache is removed, I ran nmap.

<img width="1709" height="1045" alt="image" src="https://github.com/user-attachments/assets/00a5bd12-7969-4f61-863b-e29ff4949ddc" />

After running nmap without apache, I noticed that 80/tcp disappeared. Then I installed Apache again and ran nmap.

<img width="969" height="423" alt="image" src="https://github.com/user-attachments/assets/51bae1c3-26c0-4b6d-83b6-ce1431b33c51" />

Picture shown that 80/tcp appeared, showing that apache is running.

Next enabled UFW by using:

```Bash
sudo ufw enable
sudo ufw allow 80
sudo ufw status
```

I inputted the codes into the terminal and continued to enter my IP address into the web.

<img width="1707" height="1002" alt="image" src="https://github.com/user-attachments/assets/589c35fb-b812-43df-a1c1-edd80934f97c" />

From this activity I understand that UFW acts as the firewall before user can access the web. UFW acts as the protector of the system because it xplicitly allowing web traffic on port 80.

Next allowed UFW rule `22/tcp`. First i start by getting the status of SSH.

<img width="1651" height="1028" alt="image" src="https://github.com/user-attachments/assets/b139d908-77d9-4f51-93fa-6240de7ddd38" />

Next I allowed UFW and continued to test the connection by inputting:

```Bash
ssh 192.168.237.128
ssh novie@192.168.237.128
```

<img width="1730" height="1047" alt="image" src="https://github.com/user-attachments/assets/b45f11ba-20ee-4f3a-94c5-4d03b6b1903d" />

<img width="1632" height="1011" alt="image" src="https://github.com/user-attachments/assets/c82fb367-4fb9-43a9-89e7-15b317fb6b30" />

Pictures shown that the SSH connection was successful, indicating that the firewall was not blocking the connection. Port 22 was allowed, enabling SSH communication between the systems.

Next, I created new user using:

```Bash
sudo adduser username
ssh username@192.128.237.128
```

<img width="1812" height="1041" alt="image" src="https://github.com/user-attachments/assets/8ee0b254-04f3-4db6-ae39-ac7d24dec41d" />

Photo shown that username is successfully created. Then I confirmed by using `whoami`.

<img width="1694" height="1056" alt="image" src="https://github.com/user-attachments/assets/18542b9a-938c-4074-940f-4803f70f1127" />

From this activity I understand that SSH can authenticate different user accounts on the same Linux system and allows login remotely.

Next, I download a book titled `Pride and Prejudice`, create directory, move files, create tar, compress, decompress, and extract by using these commands:

```Bash
cd ~
wget https://www.gutenberg.org/cache/epub/1342/pg1342.txt
mkdir books
mv pg1342.txt books/
tar cf books.tar books
bzip2 books.tar
bunzip2 books.tar.bz2
tar -xvf books.tar
```

<img width="1673" height="1045" alt="image" src="https://github.com/user-attachments/assets/37855183-2ab6-49d7-bfb8-130c275b06b7" />

This activity helped me learn how to download files, organize them into directories, archive and compress files for storage or transfer, and extract them using Linux command-line tools.

# Challenge Activities

## Challenge 1: Remote File Creation via SSH

So in this challenge I attempted to create file remotely from my ubuntu. Since I dont have a partner, I used another user in my Ubuntu called "username". I used the following commands:

```Bash
ssh username@192.168.237.128
touch ~/Desktop/test.txt
```

<img width="1368" height="673" alt="image" src="https://github.com/user-attachments/assets/bdfa9e7c-bab2-4500-b658-ea8cb4cdacd9" />


However, I ran into a problem becase there is no directory file in "username" user. So I had to remotely made the directory by using `mkdir ~/Desktop`. After that, I was able to make text file.

## Challenge 2: Remote GUI Apps

For this activity I attempted to command `gedit` while I was still in SSH server. 

<img width="850" height="182" alt="image" src="https://github.com/user-attachments/assets/77799189-3a5c-4103-983e-a1a801b2320a" />

As picture shown, it showed fail message because SSH only provides a terminal session. While GUI applications require a graphical display, which is not enabled by default.

## Challenge 3: SCP File Transfer

For this activity I used the following commands:

```Bash
echo "Hello World" > file.txt
scp file.txt novie@192.168.237.128:/home/novie
scp -r books novie@192.168.237.128/home/novie
```

<img width="1426" height="188" alt="image" src="https://github.com/user-attachments/assets/dd2781a8-8c63-44d8-8f33-2668f30841c7" />

In this activity I remotely made a text file with "Hello World" written on it in "username" user. After that copied thae text file into my user. AFter that I used SCP to copy a directory files using SCP recursively.

<img width="1746" height="1066" alt="image" src="https://github.com/user-attachments/assets/9e391fe0-af5f-499d-8f5c-03ef916bc54e" />

This picture shown that text file and directoty of files are copied succesfully from another user.

## Challenge 3: Compress & Share Books

So in this activity, I downloaded 10 books using `wget` command in my own terminal. 

<img width="1814" height="1058" alt="image" src="https://github.com/user-attachments/assets/aa2da539-31a2-4766-b7fb-a5f8f0a43942" />

After downloading 10 books, I directed all books into "books" file. I made a tar archive using `books.tar`. I compressed it using `books.tar.bz2` as shown at this picture:

<img width="1894" height="1090" alt="image" src="https://github.com/user-attachments/assets/37ac92bd-a21c-4a20-b8e0-c02a67048ffb" />

Based on the picture above I also continued to copy directory of files (books) to the other user "username" using SCP.

<img width="1324" height="182" alt="image" src="https://github.com/user-attachments/assets/83436002-05c2-41ff-b58f-81527a7632df" />

The picture shown is to confirm that file of directory has been successfully copied to user "username".



















































