# DevOps Networking Assignment: Domain + EC2 + DNS

## Project Overview

This assignment demonstrates deploying a simple web application on **AWS EC2** and serving it through **NGINX** on a custom domain. It covers everything from domain purchase to DNS configuration, IP routing, and Security Group setup.  

The goal was to buy a domain, launch an EC2 instance, configure NGINX, and make the site accessible via a personal domain.


<img width="1920" height="1080" alt="Screenshot (8)" src="https://github.com/user-attachments/assets/f6e6caa4-cfc1-4f02-b72d-d444c4bae303" />

---

## ✅ Steps Completed

### 1. Domain Purchase

- Bought the domain: **`abdishakurosman.uk`** using **Cloudflare**  
- Chose a personal domain for reuse in future projects
- created an A record which pointed to my EC2 Instance
  
<img width="1920" height="1080" alt="Screenshot (10)" src="https://github.com/user-attachments/assets/ed35f5d7-d8e6-43d4-88b2-7a2b9e59927c" />

---

### 2. EC2 Instance Setup

- Launched an **Ubuntu EC2 instance**  
- Configured **Security Group** with:
  - Inbound: HTTP (80), HTTPS (443)  
  - Outbound: All traffic allowed
    
    <img width="1920" height="1080" alt="Screenshot (1)" src="https://github.com/user-attachments/assets/62f1fd04-946f-4abd-8e45-98cff9cf9745" />

- I have then installed NGINX 
Using these commands : 
- sudo apt update
- sudo apt install nginx -y
- sudo systemctl start nginx
- sudo systemctl enable nginx

 Challenges & Lessons Learned !!

Domain vs Public IP: Initially, the site worked on EC2 IP but not domain → needed correct DNS A record

Curl vs Browser issue: When I ran curl from the EC2 instance, it successfully returned the NGINX page, but when accessing the domain in a browser, it displayed a “Web server down” message.

After troubleshooting and reviewing Security Groups, I realized I had forgotten to include HTTPS (port 443) in the inbound rules.

Added the rule and verified nginx was listening on HTTPS → browser access worked.

Nginx configuration: Ensured it listened on all addresses (0.0.0.0 and [::])

Security Groups: Learned how inbound and outbound rules affect public accessibility

<img width="1920" height="1080" alt="Screenshot (4)" src="https://github.com/user-attachments/assets/ba858f0e-4163-4d5a-9084-d337b74db60c" />
<img width="1920" height="1080" alt="Screenshot (6)" src="https://github.com/user-attachments/assets/462d1ef1-cb74-4605-a0ea-fcd130dd30f3" />

Overall Outcome !!

Successfully deployed a live website on AWS EC2

Accessible via custom domain: http://abdishakurosman.uk

Gained practical experience with:

EC2 instances, Security Groups, Nginx setup

DNS configuration and propagation

HTTP vs HTTPS issues and Cloudflare integration

