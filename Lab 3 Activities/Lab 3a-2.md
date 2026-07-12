# Lab 3a-2 -- Enabling HTTPS with Let's Encrypt & Certbot

This lab activity is about obtaining and enabling HTTPS using a free TLS certificate from Let's Encrypt via Cerbot. To secure Apache web server, verify certificate installation, and understanding the principles of secure communications online.

### Pre-Condition Verified: Domain Points to Server

<img width="862" height="152" alt="image" src="https://github.com/user-attachments/assets/df6a4deb-7ee7-45cd-b2a9-ec8e97b9644c" />

<img width="953" height="530" alt="image" src="https://github.com/user-attachments/assets/e10d08eb-9840-495d-ab05-de97d221b282" />

### Certbot Installed via Snap

This is the screenshot of installation confirmation of Certbot using the Snap Package

<img width="527" height="356" alt="image" src="https://github.com/user-attachments/assets/b9329da1-7621-446d-a19d-77f8eca8c374" />

### Certificate Successfully Issued

This is the screenshot showing certificate issuance from Let's Encrypt `Output of sudo certbot --apache` 

<img width="941" height="352" alt="image" src="https://github.com/user-attachments/assets/a11cf34c-1880-4e5b-9c0d-61f6ded9591c" />

### HTTPS Enabled on Apache 

This is the screenshot that Apache has ben reconfigured to support HTTPS through Certbot's automation

<img width="695" height="211" alt="image" src="https://github.com/user-attachments/assets/4b62112f-017e-403e-b0d5-be04ff7599c5" />

<img width="945" height="509" alt="image" src="https://github.com/user-attachments/assets/297462bd-01cd-4628-948b-827a56aeebf5" />

### Browser Lock Icon (Secure Connection)

The screenshot of my site loaded via `https://novieparamitha.duckdns.org

<img width="945" height="509" alt="image" src="https://github.com/user-attachments/assets/297462bd-01cd-4628-948b-827a56aeebf5" />

### View Certificate Issuer

This is the screenshot of browser certificate showing that teh issuer is Let's Encrypt

<img width="406" height="477" alt="Screenshot 2026-07-11 205808" src="https://github.com/user-attachments/assets/37afd288-e09f-448e-adbd-c13cc252e6d9" />

### Certbot Auto-Renewal Dry Run Successful

The output screenshot  `sudo certbot renew --dry-run`

<img width="518" height="128" alt="image" src="https://github.com/user-attachments/assets/345b2f54-ceef-497a-bc36-005e03afa99c" />

### HTTPS Redirect Enabled

This is the screenshot of me inputting http.

<img width="601" height="58" alt="image" src="https://github.com/user-attachments/assets/ea9cfb3c-8b37-4496-aec4-bd414641e862" />

When I entered, it is automaticallt changed to HTTPS

<img width="592" height="64" alt="image" src="https://github.com/user-attachments/assets/953a8076-14e4-4a64-b4be-225d7d9fa474" />

# Reflection Questions

- Why is HTTPS important for modern web applications?

  **Protects sensitive information such as passwords and personal data from being intercepted or modified.**

- What entity issued your site’s TLS certificate?

  **Let's Encrypt**

- How long is your certificate valid for, and how can it be renewed?

  **90 days, renew automatically using certbort `sudo certbot renew --dry-run`**

- What happens if a certificate expires and is not renewed?

  **web browsers will display security warnings indicating that the website is not secure.**

- Why does Let’s Encrypt require port 80 or 443 to be open for verification?

  **It connects to the server using HTTP (port 80) or HTTPS (port 443) to confirm that the domain points to the correct server.**















