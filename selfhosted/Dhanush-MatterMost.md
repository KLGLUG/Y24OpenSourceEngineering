 What is Mattermost?

Mattermost is an open-source team collaboration and messaging platform (like Slack or Microsoft Teams).
It helps teams chat, share files, manage projects, and integrate DevOps tools — all while giving you full control over your data, since you can self-host it on your own server.

Main Services / Components of Mattermost

Mattermost Server

The core backend service written in Go.

Manages authentication, messaging, file storage, and API.

Mattermost Web App

The frontend (React-based) interface users interact with via browser.

Database

Uses PostgreSQL or MySQL to store all data (messages, users, channels).

File Storage

Can use local disk, Amazon S3, or other object storage for file uploads.

Push Notification Service (optional)

Handles mobile notifications (either via Mattermost Cloud or your own setup).

 How to Host Mattermost on Your System (Local Setup)
Option 1: Using Docker (recommended for quick setup)

Steps:

Install Docker
 and Docker Compose
.

Create a directory and go inside it:

mkdir mattermost && cd mattermost


Download the official docker-compose.yml:

curl -O https://raw.githubusercontent.com/mattermost/docker/master/docker-compose.yml


Start the services:

docker-compose up -d


Open your browser and go to:
 http://localhost:8065

You’ll see the Mattermost setup screen. Create your admin account and workspace.

Option 2: Manual Installation (Ubuntu example)

Install PostgreSQL

sudo apt update
sudo apt install postgresql postgresql-contrib


Create database and user

sudo -u postgres psql
CREATE DATABASE mattermost;
CREATE USER mmuser WITH PASSWORD 'yourpassword';
GRANT ALL PRIVILEGES ON DATABASE mattermost TO mmuser;
\q


Download Mattermost

wget https://releases.mattermost.com/X.Y.Z/mattermost-X.Y.Z-linux-amd64.tar.gz


(Replace X.Y.Z with the latest version, e.g. 9.0.0)

Extract and move it

tar -xvzf mattermost-*.tar.gz
sudo mv mattermost /opt
sudo mkdir /opt/mattermost/data


Edit the config file

sudo nano /opt/mattermost/config/config.json


Update:

"DriverName": "postgres",
"DataSource": "postgres://mmuser:yourpassword@localhost:5432/mattermost?sslmode=disable"


Start the server

cd /opt/mattermost
sudo ./bin/mattermost


Visit http://localhost:8065 in your browser.


Below is the video url showing the features of MatterMost :-> 
(https://drive.google.com/file/d/1vcP_4G23NcgNoC0Hzv8J_0U3fh_c3CbT/view?usp=drive_link)
