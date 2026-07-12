# Lab 3b-1 Bash Backup Scripting, Cron Jobs & Cloud Export 

This activity introduces Bash scripting for creating file backups, scheduling them using cron jobs, and exporting them to the cloud. 

### Practice Bash Commands Executed

For echo, variables:

```Bash
name="Novie"
age=25
echo "Hello, $name! You are $age years old."
echo "Next year you will be $((age + 1))."
```
The variables are assigned (name="Novie")

<img width="522" height="83" alt="image" src="https://github.com/user-attachments/assets/2fc7dca3-b4e3-4e7d-9a2b-2fa48156bce8" />

Arithmetic with (()):

```Bash
a=8
b=5

echo "Sum: $((a + b))"
echo "Difference: $((a - b))"
echo "Product: $((a * b))"
echo "Quotient: $((a / b))"
echo "Remainder: $((a % b))"

((a++))
echo "a after increment: $a"
```

<img width="517" height="295" alt="image" src="https://github.com/user-attachments/assets/dbfaf147-38f9-4709-a86b-02ef5e00297a" />

Basic for loop summation:

```Bash
nano sum.sh
chmod +x sum.sh // To make it executable
./sum.sh
```

<img width="932" height="203" alt="image" src="https://github.com/user-attachments/assets/58eb6896-9860-486f-a3e6-fc162394fa42" />

<img width="393" height="56" alt="image" src="https://github.com/user-attachments/assets/b4ba1715-8071-4cbb-8c58-cb22e9dc6b7f" />

### Test Files & Directories Created

First I created a directory then made nano files and put in the respected directories. I used there following commands:

```Bash
mkdir -p /home/ubuntu/Documents/folder
mkdir -p /home/ubuntu/Documents/books

nano /home/ubuntu/Documents/folder/student.txt
nano /home/ubuntu/Documents/folder/class.txt
nano /home/ubuntu/Documents/books/romeoandjuliet.txt
nano /home/ubuntu/Documents/books/richdadpoordad.txt

ls -R /home.ubuntu/Documents
```

<img width="509" height="29" alt="image" src="https://github.com/user-attachments/assets/11b178d1-d1ac-4deb-885c-746ee990bb6f" />
<img width="597" height="202" alt="image" src="https://github.com/user-attachments/assets/dcffbbf6-fe3b-4094-8f4f-fe050127a075" />

Pictures above shows that -R recursively lists the contents of the directory, including all subfolders and their contents

### Basic Script Working

First I created 'testscript' file then I did the terminal coding. Afterwards,  executed permission

```Bash
nano /home/ubuntu/testscript
chmod 777 /home/ubuntu/testscript
ls -l /home/ubuntu/testscript

/home/ubuntu/testscript
ls -R /home/ubuntu/backup
```
This is the picture of commands execution:

<img width="512" height="260" alt="image" src="https://github.com/user-attachments/assets/a1067e88-b7e7-40f2-96fb-30bc9789e8b5" />

This is the Bash code inside 'testscript':

<img width="614" height="211" alt="image" src="https://github.com/user-attachments/assets/2fcc223d-1223-4609-a879-d310183924a4" />

### Script Moved to /usr/bin and Tested

The commands I used:

```Bash

sudo mv /home/ubuntu/testscript /usr/bin/testscript
ls -l /usr/bin/testscript 

sudo chown root:root /usr/bin/testscript
ls -l /usr/bin/testscript

cd ~
cd /tmp
cd /var/log
testscript

which testscript // To confirm its in the path
```

<img width="575" height="281" alt="image" src="https://github.com/user-attachments/assets/970898ac-7071-4fc6-83db-32dadde09d0f" />

Picture shown commands input since /usr/bin is part of the system, testscript should be able to run by it's name alone from anywhere.

### ZIP Archive with Date Filename 

These are the commands I used:
```Bash
sudo nano /usr/bin/testscript
sudo apt install zip

ls -l /usr/bin/testscript
testscript
ls -l /home/ubuntu/
```

I edited testscript file to:

<img width="754" height="324" alt="image" src="https://github.com/user-attachments/assets/0d7e7818-1d75-4882-8ecd-bf427cea325e" />

Then these are the commands execution:

<img width="850" height="516" alt="image" src="https://github.com/user-attachments/assets/784e1518-95ff-4354-b843-fc508d5f614a" />
<img width="560" height="323" alt="image" src="https://github.com/user-attachments/assets/f21ccd72-719b-4ba5-ba3b-317cc811ea52" />

### Cronjob Set Up for Hourly Backup

```Bash
sudo nano /etc/crontab
cat /etc/crontab

sudo systemctl restart cron
sudo systemctl status cron # Check if it's running
```
I added `9 **** ubuntu /usr/bin/testscript` to crontab

<img width="815" height="353" alt="image" src="https://github.com/user-attachments/assets/865ffb75-93f0-459f-ae0f-5fd828ffe773" />

Then this is the commands execution
<img width="764" height="365" alt="image" src="https://github.com/user-attachments/assets/1a4aaa0e-2329-453c-ac9a-58eeede12969" />

<img width="954" height="269" alt="image" src="https://github.com/user-attachments/assets/abe7d89d-34f3-4455-b9ba-996ff53f4a4d" />

### Successful Cron Execution Verified 

Using `ls -lh /home/ubuntu/*.zip` can prove that the file is being backup every :09.

<img width="554" height="60" alt="image" src="https://github.com/user-attachments/assets/5eb64b05-eaeb-4b57-9c32-c58624879d4b" />

### SCP to Cloud Working

I have a zip file named 'books.zip' so I did the SCP to EC2 

Commands I used:
```Bash
cd $env:USERPROFILE\Downloads
scp -i .\aws-lab-key.pem .\books.zip ubuntu@3.104.106.153:~
ssh -i .\aws-lab-key.pem ubuntu@3.104.106.153

ls ~/
```
<img width="930" height="495" alt="image" src="https://github.com/user-attachments/assets/9ff93e14-9b70-410a-8071-5993b1f6477a" />

`ls ~/` is to verify file arrival.

### SSH Certificate Accepted by Root

Commands I used: 

```Bash
cd $env:USERPROFILE\Downloads
dir *.pem

ssh -i .\aws-lab-key.pem ubuntu@3.104.106.153
```

Picture below is the commands execution showing manual acceptance of SSH key fingerprint:

<img width="601" height="426" alt="image" src="https://github.com/user-attachments/assets/74454f88-b788-4735-8678-b1a8c8ef8fb4" />

### Final Script Submitted

<img width="623" height="391" alt="image" src="https://github.com/user-attachments/assets/3bf68dc6-7c85-4ab7-869a-a269acd20787" />

<img width="617" height="383" alt="image" src="https://github.com/user-attachments/assets/7f23038d-2cb3-41b3-8b5a-da026700235f" />

<img width="766" height="159" alt="image" src="https://github.com/user-attachments/assets/31f7e196-9999-4e31-a897-20367d438a43" />

# Reflection Question

- Why is using absolute paths important in scripts run by cron? 

**Cron runs with a minimal environment and may not use the same working directory or PATH as a normal user session.**

- What are the benefits of cloud exporting for backups? 

**Cloud exporting stores backups on a remote server, protecting them from local hardware failure, accidental deletion, or data loss.**

- How does cron differ from manual execution?

**Cron executes scripts automatically according to a predefined schedule without user intervention, while manual execution requires a user to run the script each time.**

- What happens if SSH keys are not accepted ahead of time?

**Connection cannot continue**

- How can login messages help improve user/system engagement?

**Keeps user informed by displaying useful information such as system status, maintenance notices, security reminders, or welcome messages.**































