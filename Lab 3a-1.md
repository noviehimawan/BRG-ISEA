# Lab 3a-1 -- Domain, DNS and TLS Certificates with Let's Encrypt

This lab activity is about setting up a complete internet-facing web presence. Which involves, cloud VM, purchase and link a domain name, set DNS records, and secure site with HTTPS using Let's Encrypt.

## Activity 1: Domain, DNS

### Domain Name Registered

To start, I registered domain name through DuckDNS

<img width="959" height="455" alt="image" src="https://github.com/user-attachments/assets/eec30e00-78e1-4827-bba4-eb0434c54578" />

The DNS I created is successfully added

<img width="884" height="323" alt="image" src="https://github.com/user-attachments/assets/3aff9261-9340-4d30-ba74-e7a5baaee0b1" />

### A Record Created

I then connected the domain with my AWS VM public IP address

<img width="862" height="152" alt="image" src="https://github.com/user-attachments/assets/df6a4deb-7ee7-45cd-b2a9-ec8e97b9644c" />

### Apache installed

The following picture showed that Apache is running and accessible on port 80

<img width="941" height="295" alt="image" src="https://github.com/user-attachments/assets/f2099cf9-eeae-41ef-8d7a-e15d4b9c82d5" />

### Public IP to Domain Mapping Verified

Tested if DNS is connected to AWS using:

```Bash
nslookup novieparamitha.duckdns.org
dig novieparamitha.duckdns.org
```

<img width="536" height="436" alt="image" src="https://github.com/user-attachments/assets/40b06af7-09fa-492e-89a2-8b3d5c838db7" />

The picture showed that Public IP to domain mapping is verfied

### Screenshot: Apache Welcome Page via Domain

Before I was able to obtain the certificate I had a problem because my HTTPS source was IPv6. and I figure it out by checking the ufw status which stated inactive. I changed the source to IPv4 and it worked. So thats how I could open the domain on website.

<img width="376" height="32" alt="image" src="https://github.com/user-attachments/assets/407d23d9-7f02-4679-b9bc-6eb9730120b1" />

<img width="951" height="532" alt="image" src="https://github.com/user-attachments/assets/211ed2e6-c083-4f57-af19-e4330679dea2" />

## Activity 2:  Let’s Encrypt TLS Certificate Setup 

### Certbot Installed

<img width="851" height="284" alt="image" src="https://github.com/user-attachments/assets/c64e16bb-7307-4e57-b245-cdc9c75ebc93" />

### HTTPS Enabled on Domain

After obtaining the certificate, the domain is now secure. This is the **screenshot** of HTTPS with lock icon.

<img width="731" height="529" alt="image" src="https://github.com/user-attachments/assets/4a6e6737-0bc9-451d-a24c-fae38b0bdbcf" />

### Valid TLS certificate 

This is the **screenshot** of certificate issuer.

<img width="406" height="477" alt="image" src="https://github.com/user-attachments/assets/72d399a7-354b-4047-8619-1bcfe6f61749" />

### Cerbot Success Message

This is the screenshot of certbot success message `sudo cerbot --apache`.

<img width="827" height="278" alt="image" src="https://github.com/user-attachments/assets/cc41fe39-b002-4678-af89-6e39d31aa129" />

### Renewal Dry-Run Output

This is the screenshot of renewal dry-run output `sudo cerbot --dry-run`.

<img width="599" height="172" alt="image" src="https://github.com/user-attachments/assets/24123c68-c520-4535-aa97-c4677e548f81" />

### Short Explanation

- What is DNS?

**Internet naming system that translate human readable domain name into IP addresses**

- What is a domain name?  

**Unique, human-readable address used to identify a website on the internet**

- What is SSL/TLS?

**TLS (Transport Layer Security) is the modern, more secure version of SSL (Secure Socket Layer) and protects sensitive information from being intercepted or modified during transmission.**

- Why use HTTPS instead of HTTP? 

**HTTPS is preferred over HTTP because it encrypts all communication between the browser HTTP sends data in plain text and is vulnerable to attackers.**

- What does Let's Encrypt provide?

**It verifies ownership of a domain and installs certificates that enable HTTPS, allowing websites to provide secure, encrypted connections without purchasing a commercial certificate**












