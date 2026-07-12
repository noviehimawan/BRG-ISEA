# Lab 2b-1 -- Cloud Web Server Deployment with Amazon EC2 

This lab introduces cloud-based server deployment using Amazon EC2.

First, I created an AWS account.

<img width="948" height="425" alt="image" src="https://github.com/user-attachments/assets/75c9342b-86fb-4b90-bdf7-aaab7a78468a" />

<img width="944" height="437" alt="image" src="https://github.com/user-attachments/assets/686e4eac-9401-4925-8065-c10f5de76777" />

### EC2 Instance Launched

I launched EC2 Instance 

<img width="950" height="468" alt="image" src="https://github.com/user-attachments/assets/0dabc099-9d55-41ba-b2da-6447427dda01" />

Picture showing that state is running, free tier eligible, and security group configured.

### Security Group Configured 

<img width="869" height="91" alt="image" src="https://github.com/user-attachments/assets/304845f0-deec-4a8f-bc6c-d10a9072422b" />

Photo shown showing invound rules. Port 22 and Port 80.

### SSH Access Successful

<img width="550" height="380" alt="image" src="https://github.com/user-attachments/assets/04479542-5e56-4841-9804-fc3ed8ccc4e7" />

Picture showed successful SSH login using `ssh -i .\aws-lab-key.pem ubuntu@32.236.18.174`

### Apache Installed and Tested

Installed Apache using `sudo apt install apache2`

<img width="959" height="565" alt="image" src="https://github.com/user-attachments/assets/7fb44ef5-49c7-43de-91ea-4c8d7e76a8ef" />

Picture shown is the process of installing apache.

I then proceeded to check is apache working by going to my browser and inputted `http://http://32.236.18.174/`.

<img width="944" height="532" alt="image" src="https://github.com/user-attachments/assets/4e028538-05ce-480e-9652-80b60d3de25a" />

Picture shown is the welcome page of Apache which means apache installed successfully.

### Custom index.html Edited

Using these commands:

```Bash
 sudo nano /var/www/html/index.html
```
To edit the index.html

<img width="955" height="560" alt="image" src="https://github.com/user-attachments/assets/bc21ec24-ea5b-456d-85c6-d311aa4da700" />

Picture shown that index.html has been edited.

Then I check on my browser if file is succesfully edited.

<img width="959" height="515" alt="image" src="https://github.com/user-attachments/assets/71655dad-df36-4aa5-85ba-53ffa93dd7b5" />

Picture shown that content of browser output has been successfully edited.

### External File Downloaded with wget 

Next I downloaded external file with wget to be saved in /home/ubuntu file.

```Bash
cd /home/ubuntu
pwd
wget http://www2.eecs.berkeley.edu/Pubs/TechRpts/2009/EECS-2009-28.pdf
ls -lh EECS-2009-28.pdf
```

<img width="928" height="350" alt="image" src="https://github.com/user-attachments/assets/c225e93f-7614-4450-ac6b-ee69a9e261c9" />

Picture shown that file is succesfully downloaded and saved in /home/ubuntu.

### File Copied to Web Root

Next I copied file to /var/www/html.

```Bash
cd home/ubuntu
sudo cp EECS-2009-28.pdf /var/www/html
ls -l /var/www/html
```

<img width="527" height="89" alt="image" src="https://github.com/user-attachments/assets/1c0d92c4-5487-4072-a088-d109c6401c21" />

Picture showed that it is succesfully copied.

### PDF File Accessible via Browser

By inputting `http://32.236.18.174//EECS-2009-28.pdf` to my web browser, I was able to open the pdf file.

<img width="945" height="562" alt="image" src="https://github.com/user-attachments/assets/025bbdb1-0949-42ad-a861-95147447ebf8" />

### Link Inserted in HTML Page

I used `sudo nano /var/www/html/index.html` and edited the index/html file

<img width="945" height="490" alt="image" src="https://github.com/user-attachments/assets/a8118c0e-653b-485f-b24d-2377ec07c713" />

Picture shown that I added an HTML snippet `<a href="EECS-2009-28.pdf">Click here</a>`

<img width="959" height="560" alt="image" src="https://github.com/user-attachments/assets/bf977183-eb19-45cb-9731-07691cd32385" />

Picture shown that index.html has been edited with a hyperlink to the PDF file.

### Budget Monitoring Enabled

First I clicked on my account name and click `Billing and Cost Management`

<img width="937" height="445" alt="image" src="https://github.com/user-attachments/assets/3e572fd9-eab6-4bbd-8abe-11d38cc34f2f" />

<img width="951" height="473" alt="image" src="https://github.com/user-attachments/assets/0e96067c-4768-4926-88c3-661e1a49df80" />

Pictures shown are my AWS Billing Dashboard with budget alert setup.

### Instance Termination

Termination of the AWS EC2 once I was done using it to ensure there was no unecessary resources running.

<img width="940" height="256" alt="image" src="https://github.com/user-attachments/assets/9736d28e-3143-4f3e-92cf-90dea93af135" />

### Challenge 1: Network Latency Testing

I used `ping` to test servers in different countries (e.g US, Europe, and Japan)

```Bash
ping -c 4 google.com
ping -c 4 bbc.co.uk
ping -c 4 www.yahoo.co.jp
```
<img width="1853" height="899" alt="image" src="https://github.com/user-attachments/assets/4986c559-5113-4ceb-ac3d-27c5fa19a09c" />

The server located closest to my region had the lowest latency, while servers located farther away had higher latency. This was expected because network packets travel longer physical distances and pass through more network devices when communicating with overseas servers.

# Reflection Questions

- What were the benefits of cloud deployment over local virtualisation?

**Cloud deployment allows servers to be accessed from anywhere with an internet connection, making it easier to host websites and collaborate remotely**

- How does Apache serve files, and how did you verify this?

**Apache serves web content from the default web root directory, verified by editing the index.html and refreshing the web browser and confirming that is is edited succesfully**

- What did you learn about file ownership and permissions?

**Commands such as chmod, chown, and sudo cp were used to ensure that files had the appropriate permissions while preventing unauthorized access.**

- What risks are associated with leaving instances running?

**Leaving EC2 instances running can lead to unnecessary cloud charges and increase security risks if the server is not properly maintained or monitored.**

- How would you explain the difference between DNS and /etc/hosts to a client?
**Changes to /etc/hosts affect only that device, whereas DNS changes are available to users worldwide.**
























