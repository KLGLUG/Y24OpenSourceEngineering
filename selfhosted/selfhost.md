# 🚀 Self-Hosted Server Project Overview

## 🖥️ Project Description
This project demonstrates how I built my **self-hosted server** using **Ubuntu Linux**.  
It creates a **secure and reliable environment** for other devices to safely access hosted services such as websites or APIs.  
The main goal was to make a **protected mini server setup** with firewalls, SSH security, and local network access.

---

## 🌐 Features
- UFW firewall protection  
- Fail2Ban security against brute-force attacks  
- Static IP setup with Netplan  
- Nginx web server hosting  
- SSH access for remote management  
- Optional HTTPS encryption using Let’s Encrypt  

---

## ⚙️ Installation Steps (English Example)
1. Update the system:
   
   sudo apt update && sudo apt upgrade -y
Install Nginx web server:

sudo apt install nginx -y
Enable and configure the firewall:



sudo ufw enable
sudo ufw allow 22
sudo ufw allow 80
sudo ufw allow 443
Start Nginx:



sudo systemctl enable nginx
sudo systemctl start nginx
Access the default page:




Hasan
Open Source Contributor & Linux Enthusiast
GitHub: @Hasan-8326

✅ Summary
This project shows how to set up a self-hosted Ubuntu server from scratch — with proper security, network configuration, and service hosting — making it an ideal starting point for open-source and local hosting projects.




---

