సెల్ఫ్-హోస్టెడ్ PairDrop సర్వర్ డాక్యుమెంటేషన్
పేరు: Mahi Venkat Pavan Korrapati
కళాశాల: KL University
ఆపరేటింగ్ సిస్టమ్: Ubuntu 22.04 LTS



1. పరిచయం

ఈ పత్రం సెల్ఫ్-హోస్టెడ్ PairDrop సర్వర్‌ను సెటప్ చేయడం మరియు నిర్వహించడం గురించి వివరమైన వివరణను అందిస్తుంది 
on Ubuntu. PairDrop is an open-source, peer-to-peer file transfer tool inspired by Snapdrop. It enables 
secure, fast, and direct file sharing between devices within the same network or via the internet without 
requiring third-party cloud storage. The purpose of this setup is to provide a private and secure environment 
for transferring files efficiently while maintaining full control over data flow.

2. సిస్టమ్ అవసరాలు

Before hosting the PairDrop server, ensure that your system meets the following requirements:
- **Operating System**: Ubuntu 20.04 or later (recommended: Ubuntu 22.04 LTS)
- **Processor**: Dual-core CPU or higher
- **Memory (RAM)**: Minimum 2 GB
- **Storage**: At least 10 GB free space
- **Network**: Stable internet connection or local LAN
- **Software Dependencies**:
  - Node.js (v16 or above)
  - npm (Node Package Manager)
  - Git
  - PM2 (for process management)

3. ఇన్‌స్టాలేషన్ మరియు సెటప్

Follow these steps to host PairDrop on Ubuntu:
1. **Update and upgrade your system:**
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```
2. **Install Node.js and npm:**
   ```bash
   sudo apt install nodejs npm -y
   ```
3. **Clone the PairDrop repository:**
   ```bash
   git clone https://github.com/schlagmichdoch/PairDrop.git
   cd PairDrop
   ```
4. **Install dependencies:**
   ```bash
   npm install
   ```
5. **Start the server:**
   ```bash
   npm start
   ```
6. **Access PairDrop:**
   Open a browser and navigate to `http://localhost:3000` or your server’s IP address.

4. సర్వర్ నిర్వహణ మరియు ఆకృతీకరణ

To keep the server running continuously, it is recommended to use a process manager like PM2.
Install PM2 globally using:
```bash
sudo npm install -g pm2
```
Start the PairDrop server with PM2:
```bash
pm2 start npm --name pairdrop -- start
```
You can also configure the server to restart automatically after system reboot:
```bash
pm2 startup
pm2 save
```
PairDrop can also be configured with HTTPS using a reverse proxy like Nginx for secure communication.

5. పరీక్ష, సమస్య పరిష్కారం మరియు ముగింపు

After the setup, ensure that PairDrop is working correctly by transferring files between devices.
If devices cannot detect each other, check the following:
- Ensure all devices are on the same network.
- Verify that no firewall or router blocks WebRTC or WebSocket connections.
- Review logs using `pm2 logs pairdrop` for debugging.

**ముగింపు:**
This document provides step-by-step guidance on deploying a self-hosted PairDrop server on Ubuntu. 
By hosting it privately, users gain complete control over their data and improve file transfer efficiency. 
This setup by Mahi Venkat Pavan from KL University demonstrates practical implementation of 
peer-to-peer technology in real-world applications.
