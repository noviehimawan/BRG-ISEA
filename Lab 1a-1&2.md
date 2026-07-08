# LAB 1a-1 -- Virtualisation and Linux Set Up

Creating Linux environment, which started with VirtualBox download using virtualization software. The goal is to familiarize ownself to network settings in virtualized environment.

In this lab exercise, a VirtualBox or an equivalent virtualization tool is required together with Ubuntu (as desktop ISO), Git, and Github.

Started this exercise with downloading VirtualBox, which downloaded smoothly, continued with the download of Ubuntu. Which all links are acquired through the official links. Here is the screenshot of both softwares succesfully downloaded

<img width="455" height="43" alt="image" src="https://github.com/user-attachments/assets/35110123-c543-4934-92a8-008d6a1347d1" />

However, the process of downloading Ubuntu inside the VM, didn't go smoothly, causing the page to be stuck on the loading process for more than 10 minutes which was deemed abnormal.

<img width="2048" height="1140" alt="ubuntu fail" src="https://github.com/user-attachments/assets/e00fd67e-2d84-41f9-9f87-fc1466cb2c13" />

Hence, VMware was installed instead of VirtualBox. Which worked miraculously and installation complete message was delivered through NAT configuration. 

Here is the screenshot of the VM configuration

<img width="239" height="365" alt="image" src="https://github.com/user-attachments/assets/e47cb22a-3667-4e03-8e00-e828c6974217" />

Here is the screenshot of succesfull Ubuntu installation inside the VM after inputting username which I named "Lemon Barley" and my password.

<img width="738" height="1010" alt="ubuntu success" src="https://github.com/user-attachments/assets/94ce609e-e41a-479f-a989-6945907f559a" />

"Restart Now" was clicked and Ubuntu automatically restarted and prompt to enter password for the username created.

<img width="1974" height="1155" alt="password prompt ubuntu" src="https://github.com/user-attachments/assets/96ee162b-7c16-4db9-bd81-94b185aa8e15" />

After it is fully loaded, the desktop looked like this:

<img width="1972" height="1290" alt="image" src="https://github.com/user-attachments/assets/11798dce-e0e5-48de-9f63-d787623e68a5" />


Afterwards, I installed git to the Ubuntu by prompting the following:
```bash
sudo apt update
sudo apt install git
```

However, I ran into a problem because it kept prompting error. Thus, I realized that my NAT was not fully connected to the VM. After repairing the VM, I attempted to install git again and it worked. I continued by connecting my Git to my Github.

<img width="1976" height="1155" alt="image" src="https://github.com/user-attachments/assets/a68d51d3-b201-4e1d-9334-673061dd3c6f" />

However, I noticed a typo in the name so I repaired it by updating my correct name. 

<img width="1626" height="209" alt="image" src="https://github.com/user-attachments/assets/fe34c39f-3e5f-4cad-b472-0d2e45029717" />


This is the process of allowing ssh by using the following commands:
```bash
sudo apt update
sudo apt install openssh-server -y
sudo systemctl status ssh
sudo systemctl enable --now ssh
sudo ufw allow ssh
```
<img width="1974" height="1146" alt="image" src="https://github.com/user-attachments/assets/66bd6066-bc93-40ad-b9b3-5f12625602bb" />

With the SSH key obtained, I connected the code into my GitHub account this is to securely authenticate my computer to my GitHub account.

<img width="704" height="190" alt="image" src="https://github.com/user-attachments/assets/657b0630-d359-4f3b-9a02-34c67ed2b5ba" />


## Conclusion

this lab provided valuable hands-on experience in setting up and using a virtual machine to run Ubuntu Linux. Although I encountered challenges with VirtualBox, particularly long loading times and delays during the VM setup, I learned the importance of configuring a reliable virtualisation environment and understanding the role of NAT networking. The experience also increased my confidence in using Ubuntu and demonstrated how virtualised Linux environments are widely used in industry for software development, cybersecurity, testing, and system administration without affecting the host operating system. If I were to set up another virtual machine in the future, I would choose VMware from the beginning and ensure that the NAT configuration is stable to achieve a smoother and more reliable setup process.

## Reflection

Using virtual machines provides a safe environment for testing and development because users can run different operating systems, test software, and make changes without affecting the main system. During the setup process, I faced challenges such as VirtualBox taking a long time to load and difficulties configuring the network connection. I learned that NAT allows the VM to share the host’s internet connection, while Bridged networking allows the VM to connect directly to the same network as other devices. I also learned that Linux distributions have different purposes and features, with Ubuntu being a beginner-friendly option commonly used for learning, development, and server tasks.

# LAB 1a-2 -- Ubuntu Dekstop and & CLI Familirisation

The goal of this lab is to familiarize myself with Ubuntu set up and to be more comfortable using Linux through GUI and CLI.

### Part 1 -- Ubuntu Desktop GUI Familirisation

In this part 1, I am using this lab opportunity to familiarise myself with the Ubuntu features, connectivity, and get comfortable with it. Throughout the lab session I managed to create a text document using LibreOffice and using the terminal to install the app.

To ensure internet connectivity in the Linux, I am using Firefox to download LibreOffice proving internet connectivity as shown in the picture.

<img width="1974" height="1256" alt="image" src="https://github.com/user-attachments/assets/4632f62d-49b2-44a3-870c-bf8e3c49858d" />

I continued by using Ubuntu to download LibreOffice by using the following commands:

```bash
sudo apt update
sudo apt install libreoffice
```
<img width="1974" height="1256" alt="image" src="https://github.com/user-attachments/assets/0279fa03-ac85-496d-8609-4d94c09455fa" />

To show that LibreOffice is working, I wrote a sentence as shown in the picture

<img width="1976" height="1227" alt="image" src="https://github.com/user-attachments/assets/170575ab-6ff4-4a39-b5e6-4f0db520e9a4" />

Next, I am exploring task manager and the default app centre.

<img width="1959" height="1219" alt="image" src="https://github.com/user-attachments/assets/e92ce935-5912-480c-9c32-1ff597081e5e" />

<img width="2010" height="1227" alt="image" src="https://github.com/user-attachments/assets/f43bfd4f-d528-4324-a69f-24420ad8161b" />

### Part 2 -- CLI Basics and File Operations

In this part 2, I will be using basic commands to execute file operations.

#### To monitor processes:

```Bash
ps -e
top
1
```

<img width="1982" height="1227" alt="image" src="https://github.com/user-attachments/assets/c8e3d02c-4dbf-479b-a59f-3bc12c70d425" />

Picture shown the implementation of 'ps -e' showing list of running processes

<img width="1950" height="1217" alt="image" src="https://github.com/user-attachments/assets/a9767b33-016e-4a19-bf9c-dba0e45f0998" />

Picture shown the implementation of 'top' and '1' which toggles per-CPU/core usage lines in top.


#### To explore files:

```Bash
ls
ls -la
ls -alt
ls -lah
```
<img width="1847" height="1258" alt="image" src="https://github.com/user-attachments/assets/84a779ee-41a8-43f5-9ead-992477bfc5ae" />

<img width="1864" height="1227" alt="image" src="https://github.com/user-attachments/assets/4084d2fc-8831-4524-8e92-cd88fc06b98f" />

<img width="1942" height="1174" alt="image" src="https://github.com/user-attachments/assets/ed711515-7cf5-412a-8831-479d34034f18" />

Pictures shown are the imlpementation of file exploring, describing '-l' for long listing, '-a' include hidden, '-h' human-readable sizes, '-t' to sort by time.

#### To create/edit/view:

```Bash
touch
gedit
nano
cat
less
```

'touch' is a command that allows us to create new empty file in the current directory, and for this session I will be naming my file 'testfile'.

<img width="1851" height="1269" alt="image" src="https://github.com/user-attachments/assets/72133cbf-5eb4-44bb-86a2-7878e0f88ec3" />

The picture shown the input of 'touch testfile' this is to create an empty file named 'testfile' in the directory with the timestamp.

Next, I will be using the 'gedit' command to create an empty text file.

<img width="1853" height="1238" alt="image" src="https://github.com/user-attachments/assets/b1b231a2-376f-45ca-bd96-03a91501ec5b" />

Picture shown that a file named 'testfile' has been created, which I proceed to enter a sentence. From this command I am also amble to edit the content.

Next I will be using the 'nano' command, this is to create a terminal-based file.

<img width="1875" height="1236" alt="image" src="https://github.com/user-attachments/assets/e96205df-0c7a-49a6-8cb9-22ad07051026" />

Picture shown that the sentence I input in 'testfile' is shown in a terminal-based document. 

Next I will be using 'cat' command

<img width="1873" height="1227" alt="image" src="https://github.com/user-attachments/assets/2e35b41f-cb59-4f38-9c74-8cb42cedaf93" />

Picture shown using the 'cat' command allows to print file content into the terminal.

Next I will be using 'less' command

<img width="1866" height="1201" alt="image" src="https://github.com/user-attachments/assets/ee04583a-9837-4e6d-a833-7cde9af6afe3" />

Picture shown using 'less' command is used to view contents output one screen at a time.

I have also noticed that using 'ls' and 'ls -l' allows to check if file was created with the timestamp.

<img width="1765" height="366" alt="image" src="https://github.com/user-attachments/assets/86a5a88c-d97c-4538-a8f5-35708faff79d" />

#### To copy and move files:
```Bash
cp
mv
rm (to delete)
```
<img width="1755" height="1220" alt="image" src="https://github.com/user-attachments/assets/e6350056-e07f-4d4e-914f-04d09f52e491" />

Picture shown the implementation of 'cp' to duplicate 'testfile' and name the duplicated file 'testfile2'. 'mv' command allows to rename or move file, in which I have renamed testfile2 to testfile3. 'rm' command deletes the file, which I removed testfile3. 'ls -lah' is to show file size which is 96K.

#### To view system info:
```Bash
unamme-a
lsb_release-a
hostnamectl
```
<img width="1877" height="1227" alt="image" src="https://github.com/user-attachments/assets/51ac5bb6-dc23-4263-bb73-b7cd2ddbe3a6" />

Picture shown 'uname -a' displays information about the Linux kernel and system architecture, including the kernel version, machine hardware, and operating system. 'lsb_release -a' displays information about the Linux distribution (distro), such as the distributor, version, and release. 'hostnamectl' displays detailed information about the system, including the hostname, operating system, kernel version, and hardware architecture.

### Part 3 -- Super User and Permission

In this part 3 I will understand how Linux controls user privileges and protects the operating system from unauthorized changes.

I will be using the following commands:

```Bash
whoami
sudo whoamsi
adduser
sudo adduser
```

<img width="1853" height="1048" alt="image" src="https://github.com/user-attachments/assets/0b399456-c473-475f-b854-448b695062aa" />

Picture shown the implementation of 'whoami' is to show username which is novie. 'sudo whoami' displays root, showing temporary administrator privileges. 'adduser' fails because a regular user cannot create accounts. 'sudo adduser' to succesfully create a new user. I have also added 'id' command to confirm the existence on the new user. 

From this practice, I've learned that root user is the administrator of Linux system and holds full control of the operating system and can perform any administrative task. One of which is creating new user. To maintain system security, users should perform everyday tasks with a regular account and use sudo only when elevated privileges are necessary. This reduces the risk of accidental system changes and improves overall security.

### Part 4 -- Network Configuration and DNS

In this part 4, I will learn the basic understanding for Linux networking and DNS. Throughout this activity, I will be able to identify private IP addresses, test network connectivity, perform DNS lookups, configure local hostname resolution, and distinguish between public and private IP addresses.

I will be using these following commands:

#### For Private IP & Ping

```Bash
ip a
ping -c 3 8.8.8.8
```

<img width="1810" height="1120" alt="image" src="https://github.com/user-attachments/assets/e6199d00-c583-4adb-af0d-3f22de1620cf" />

Picture shown I was able to obtain the private IP address of the Ubuntu VM, indicating that it was connected to the local network.

#### For Creating Custom Aliases

```Bash
sudo nano /etc/hosts
ping GoogleEpidDNS
```
I Started by using 'ping 8.8.8.8' to ensure connectivity to the local network.

<img width="1713" height="1051" alt="image" src="https://github.com/user-attachments/assets/538c131b-e08f-45c1-b0ca-244ce356b6bf" />

Once I made sure it is connected to the local network, I proceeded to create a terminal file using 'sudo nano /etc/hosts'

<img width="1782" height="1036" alt="image" src="https://github.com/user-attachments/assets/b1751562-0d2b-4103-97f9-8b854562e236" />

After file is created, I added '127.0.0.1 GoogleEpicDNS' to create a custom hostname 'GoogleEpicDNS' through '/etc/hosts' file

<img width="1716" height="1028" alt="image" src="https://github.com/user-attachments/assets/c939cd5f-f177-40bf-bebc-64b31b5389d8" />

This demonstrates how Linux performs local hostname resolution without querying a DNS server. The successful ping GoogleEpicDNS confirmed that the custom alias was correctly resolved to the local IP address.

#### DNS Tools

```Bash
nslookup google.com
sudo apt install whois
whois google.com | head -n 12
```
I used 'nslookup google.com' to fin the server IP address associated with a domain name.

<img width="1787" height="1054" alt="image" src="https://github.com/user-attachments/assets/4412c65f-a664-4d48-a02f-43a693f97897" />

Then i continued with installing 'whois' because it is not included in the Ubuntu installation.

<img width="1653" height="1039" alt="image" src="https://github.com/user-attachments/assets/26b283df-583c-430c-ae7c-d149e383f5ea" />

Photo shown publicly available registration information about the domain and display first 12 lines of the output.

<img width="467" height="173" alt="image" src="https://github.com/user-attachments/assets/9cc924f7-e8f6-4a9d-b8bc-c62899c32f53" />

The website whatismyipaddress.com displayed the public IP address assigned by the Internet Service Provider (ISP), which identifies the network on the Internet. 'ip a' shows host's private address on the LAN. Most home use NAT to map any private hosts to one public IP.

### Part 5 -- System and Hardware Info

In this part 5, I will inspect and understand computer's hardware using Linux command-line tools.

Using these commands:

#### To Inspect Hardware:

```Bash
lsusb
lspci
less /proc/cpuinfo
```
<img width="1662" height="1032" alt="image" src="https://github.com/user-attachments/assets/60c0ff6b-eccd-45b5-acf8-2a028ff0b247" />

<img width="1744" height="1047" alt="image" src="https://github.com/user-attachments/assets/66b1ade9-be46-4abe-9ad1-9c9cbbfda49e" />

<img width="1681" height="1021" alt="image" src="https://github.com/user-attachments/assets/37a200bf-a9a9-4c40-8aaa-a208a230240a" />

Pictures shown hardware details when commands were inputted.

The GUI provides an easy-to-read summary of system information.

The CLI provides the same information, often with more detail.

#### To Redirect Output:
```Bash
lsusb > output_of_lsusb
cat output_of_lsusb
less output_of_lsusb
rm output_of_lsusb
```

<img width="1673" height="1038" alt="image" src="https://github.com/user-attachments/assets/80547600-cff0-4cb6-9e55-42a6c86c340b" />

<img width="1657" height="1023" alt="image" src="https://github.com/user-attachments/assets/daeec783-4740-436d-af3d-54f15266bde4" />

This activity is to demonstrate how Linux can redirect command output into a file, allowing users to save, review, and manage command results.

### Part 6 -- Software Installation Methods

In this part 6 is to help me learn the different ways software can be installed on Ubuntu. By completing this activity, I will understand the advantages and disadvantages of each installation method and become familiar with Ubuntu's package management system.

For the first activity, I downloaded Google Chrome from the official website (.deb). I continued to install Google Chrome from the terminal.

<img width="1701" height="1037" alt="image" src="https://github.com/user-attachments/assets/ad8e5996-c1f3-4676-878b-13cf7214d6da" />

<img width="1647" height="1013" alt="image" src="https://github.com/user-attachments/assets/0c16fa68-d9fb-462f-83e1-544b56da4ae8" />

<img width="1703" height="1019" alt="image" src="https://github.com/user-attachments/assets/2ee1476a-300c-43ae-9db5-81b4f129419a" />

I confirmed the installation of Google Chrome by inputting 'google-chrome --version' Checking the version of the Google Chrome.

Next I will download vlc from the default Ubuntu Software Centre

<img width="1735" height="998" alt="image" src="https://github.com/user-attachments/assets/9ec0e482-c200-400c-98e0-9ac4f3b902d8" />

I will use these following commands:

```Bash
sudo apt update
sudo apt upgrade
sudo apt install vlc
vlc --version
sudo apt search[keyword]
less /etc/apt/sources.list.d/ubuntu.sources
```
<img width="1881" height="1096" alt="image" src="https://github.com/user-attachments/assets/37a5759d-9c3d-4922-b9e7-bf382d0c1500" />

To ensure vlc is installed, I used 'vlc --version'

<img width="1716" height="1045" alt="image" src="https://github.com/user-attachments/assets/a5b1a231-4f2b-4524-bba8-b26fa8844b00" />

<img width="1782" height="1086" alt="image" src="https://github.com/user-attachments/assets/877344d8-ca8c-4cc0-a8f5-9e2713158277" />

<img width="1885" height="1073" alt="image" src="https://github.com/user-attachments/assets/47b2c426-4268-4ec2-ab11-d5c814e40c92" />

Ubuntu sources list:

<img width="1758" height="1062" alt="image" src="https://github.com/user-attachments/assets/b10d5d5e-3423-4bb7-b9a6-b8868c73b49e" />

Exploring /etc/apt/sources.list helps tounderstand how Ubuntu connects to trusted software repositories to download secure and verified applications. These activities develop basic Linux administration skills, which are useful for maintaining and managing Linux systems in real-world environments.

### Part 7 -- Compiling from Source

I will be using the following commands:

```Bash
nano hello_world.c
gcc hello_world_c -o hello_world_executable
./hello_world_executable
chmod 777 hello_world_executable
```
First I created a nano file named hello_world.c

<img width="1722" height="1036" alt="image" src="https://github.com/user-attachments/assets/6ac8b328-ac7d-40f1-865f-a80b837abf12" />

After that I input Hello World

<img width="1656" height="1035" alt="image" src="https://github.com/user-attachments/assets/0f733db4-cf94-4c0d-a84e-602b0888256f" />

Then I continue to input ./hello_world_executable

<img width="1677" height="1036" alt="image" src="https://github.com/user-attachments/assets/69de4016-24a5-4bdd-a21e-5ace46b16a79" />

<img width="1657" height="1019" alt="image" src="https://github.com/user-attachments/assets/9a38a8c4-7eb5-453b-ab44-c0b55c2d343e" />

### Conclusion

Overall, this lab strengthened my understanding of the Ubuntu Linux environment by allowing me to use both the graphical interface and the command-line interface. I learned basic Linux commands, file and user management, networking, software installation methods, and how to compile a simple program using GCC. Despite some challenges during the setup process, the activities improved my confidence in using Linux and provided practical skills that are useful for software development, cybersecurity, and system administration.

### Reflection Summary

From this lab, I learned that Nano is the most suitable file editor for remote access because it works well through the command line. I also learned that SaaS applications are convenient, repository installations are secure and easy to manage, binary installations provide flexibility, and source compilation offers greater control but is more complex. Each installation method has its own advantages depending on the user's needs and technical skills. Using the Linux command-line interface also improved my understanding of file management, software installation, and basic system administration, making me more confident in using Linux.





















