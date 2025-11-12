DOCUMENTATION BY 
Team Members:
P. Akshith(2400030388) 
K. Sai Sri Charan (2400031943)
LocalSend — Cross-Platform File Sharing Made Simple
Overview
LocalSend is a free, open-source, and cross-platform file-sharing application that allows users to securely transfer files, text, or media between devices without the need for the internet or external servers. It uses a peer-to-peer (P2P) connection over a local Wi-Fi network, ensuring privacy, speed, and full control over your data. LocalSend is available on Windows, macOS, Linux, Android, and iOS.
Key Features
•	Cross-Platform Compatibility: Works seamlessly across Android, iOS, Windows, macOS, and Linux.
•	Secure Transfers: Uses HTTPS and local encryption — no data is sent over the internet.
•	Fast File Sharing: Transfers files using your local Wi-Fi — faster than Bluetooth or cloud.
•	No Internet Required: Works offline, even without an active internet connection.
•	Open Source: 100% transparent and community-driven.
•	Simple & Lightweight: Clean interface with minimal setup — ready to use in minutes.
•	Free Forever: No ads, no subscriptions, no trackers.
Use Case Example
Imagine you need to share a 1GB project folder from your Linux laptop to your Android phone. Instead of uploading to Google Drive or sending via email:

1. Open LocalSend on both devices.
2. Ensure both are connected to the same Wi-Fi network.
3. Select the file or folder → choose the receiving device → send.
4. Done! The transfer happens instantly over the local network — secure and private.
Installation Guide (via Flatpak)
1.	Step 1: Install Flatpak
sudo apt update
sudo apt install flatpak -y
2.	Step 2: Add the Flathub Repository
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
3.	Step 3: Install LocalSend
flatpak install flathub org.localsend.localsend_app
4.	Step 4: Run LocalSend
flatpak run org.localsend.localsend_app
5.	Step 5: One-Command Setup (Optional)
sudo apt update && sudo apt install -y flatpak && \
sudo flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo && \
sudo flatpak install -y flathub org.localsend.localsend_app && \
flatpak run org.localsend.localsend_app
How LocalSend Works
LocalSend creates a local server on your device and detects other LocalSend instances connected to the same network. When you send a file:
- A secure HTTPS connection is established.
- The data is transferred directly between the two devices.
- No cloud servers or external storage are used.

This ensures 100% privacy, high speed, and low energy consumption.
Advantages
•	Privacy First: No third-party servers or data logging.
•	Device Agnostic: Works across different operating systems.
•	Speed: Uses local Wi-Fi for lightning-fast transfers.
•	Simple Interface: Minimal, modern UI for easy use.
•	Offline Functionality: Works without internet connection.
•	Open Source: Transparent and community-supported project.
Technical Summary
•	Application Type: Cross-platform P2P File Sharing App
•	Technology Stack: Flutter / Dart / Flatpak
•	Network Protocol: HTTPS (Local Network)
•	Data Transfer Method: Direct device-to-device over LAN
•	Supported OS: Windows, Linux, macOS, Android, iOS
•	Repository Source: https://github.com/localsend/localsend
•	Installation Time: ~5 minutes
Conclusion
LocalSend is an elegant solution for fast, secure, and private file sharing between devices. It eliminates the need for external services, ensures complete data control, and enhances productivity in both personal and professional settings. With just a few commands, LocalSend can be installed on any system and is ready to use instantly — making it one of the best self-contained file-sharing solutions available today.
Project Contributors
Pola Akshith (2400030388) - Lead Developer & Documentation
K. Sai Sri Charan (2400031943) - Testing & Deployment Support
Summary Table
•	Purpose: Share files instantly between devices using local Wi-Fi
•	Type: Cross-platform desktop/mobile app
•	Stack: Flutter, Dart, Flatpak
•	Access: GUI / CLI via Flatpak
•	Advantages: Privacy, speed, no internet dependency
•	Setup Time: 5–10 minutes
