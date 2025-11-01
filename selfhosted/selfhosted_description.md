# 🚀 Paperless-ngx Self-Hosting | Open Source Engineering Project

## 🧩 Project Overview
We successfully self-hosted the open-source **Paperless-ngx** — a powerful **Document Management System (DMS)** — using Docker and Docker Compose on Ubuntu Linux.

---

## 📁 What is Paperless-ngx?
**Paperless-ngx** అనేది ఓపెన్ సోర్స్ డాక్యుమెంట్ మేనేజ్‌మెంట్ సిస్టమ్ (DMS).  
ఇది ఈ విధంగా ఉపయోగపడుతుంది:

- స్కాన్ చేసిన పత్రాలను డిజిటల్‌గా భద్రపరచుకోవచ్చు 🗂️  
- OCR (Optical Character Recognition) ద్వారా పత్రాలలో ఉన్న టెక్స్ట్‌ని సెర్చ్ చేయవచ్చు 🔍  
- ట్యాగ్స్ మరియు కేటగిరీల ద్వారా ఫైళ్లను సులభంగా నిర్వహించవచ్చు 🏷️  

---

## ⚙️ అవసరమైనవి (Requirements)
Paperless-ngx ను హోస్ట్ చేయడానికి ముందు ఈ వాటి అవసరం ఉంటుంది:

- Ubuntu / Linux OS  
- Docker మరియు Docker Compose  
- కనీసం **2GB RAM**  
- **10GB డిస్క్ స్పేస్**  
- స్థిరమైన ఇంటర్నెట్ కనెక్షన్ 🌐  

---

## 🧠 Installation Process (తెలుగులో)

### 1️⃣ Docker మరియు Docker Compose ఇన్‌స్టాల్ చేయడం
టెర్మినల్‌లో ఈ కమాండ్లు ఇవ్వండి 👇  
```bash
sudo apt update
sudo apt install -y docker.io docker-compose
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER

2️⃣ Paperless ఫోల్డర్ సృష్టించడం
mkdir ~/paperless
cd ~/paperless

3️⃣ docker-compose.yml ఫైల్ సృష్టించడం
nano docker-compose.yml


ఈ కంటెంట్‌ని పేస్ట్ చేయండి 👇

services:
  broker:
    image: redis:7
    restart: always

  db:
    image: postgres:15
    restart: always
    environment:
      POSTGRES_DB: paperless
      POSTGRES_USER: paperless
      POSTGRES_PASSWORD: paperless

  webserver:
    image: ghcr.io/paperless-ngx/paperless-ngx:latest
    depends_on:
      - db
      - broker
    ports:
      - "8080:8000"
    volumes:
      - ./data:/usr/src/paperless/data
      - ./media:/usr/src/paperless/media
      - ./export:/usr/src/paperless/export
      - ./consume:/usr/src/paperless/consume
    environment:
      PAPERLESS_REDIS: redis://broker:6379
      PAPERLESS_DBHOST: db
      PAPERLESS_DBNAME: paperless
      PAPERLESS_DBUSER: paperless
      PAPERLESS_DBPASS: paperless
    restart: always


సేవ్ చేయడానికి 👉
Ctrl + O → Enter → Ctrl + X

4️⃣ సర్వర్ స్టార్ట్ చేయడం
docker compose up -d


రన్ అవుతున్న కంటైనర్లు చూడడానికి:

docker ps


ఇవి కనపడాలి:

paperless-webserver-1

paperless-db-1

paperless-broker-1

5️⃣ వెబ్ ఇంటర్‌ఫేస్ ఓపెన్ చేయడం

బ్రౌజర్‌లో ఈ అడ్రస్‌లోకి వెళ్లండి 👇
👉 http://localhost:8080

ఇంకో కంప్యూటర్‌ నుండి యాక్సెస్ చేయాలంటే:
👉 http://<నీ సర్వర్ IP>:8080

నీ సర్వర్ IP తెలుసుకోవాలంటే:

hostname -I

6️⃣ అడ్మిన్ యూజర్ సృష్టించడం
docker exec -it paperless-webserver-1 bash
python manage.py createsuperuser


ఇప్పుడు నీకు కావాల్సిన username, email, password ఇవ్వండి.
తర్వాత exit చేయండి:

exit

7️⃣ సర్వర్ చెక్ చేయడం

బ్రౌజర్‌లో మళ్లీ వెళ్లండి 👉 http://localhost:8080

నీ క్రియేట్ చేసిన యూజర్‌తో లాగిన్ అవ్వండి.
PDF ఫైల్ అప్‌లోడ్ చేసి ప్రాసెస్ అవుతుందో చూడండి 🎉

8️⃣ సర్వర్ మేనేజ్ చేయడం
చర్య	కమాండ్
సర్వర్ ఆపడం	docker compose down
సర్వర్ రీస్టార్ట్	docker compose up -d
లాగ్స్ చూడడం	docker logs -f paperless-webserver-1
రన్ అవుతున్న కంటైనర్లు	docker ps
9️⃣ సమస్యలు వచ్చినప్పుడు
సమస్య	పరిష్కారం
Port 8080 already in use	"8090:8000"కి మార్చండి
Permission denied	sudo usermod -aG docker $USER చేసి రీబూట్ చేయండి
వెబ్ పేజ్ ఓపెన్ కావడం లేదు	కంటైనర్లు రన్ అవుతున్నాయో చూడండి, ఫైర్‌వాల్ చెక్ చేయండి
🔄 Uninstall చేయాలంటే
docker compose down -v
rm -rf ~/paperless

🎯 ముగింపు (Conclusion)

ఇప్పుడు నువ్వు నీ సొంత Paperless-ngx సర్వర్‌ని సక్సెస్‌ఫుల్‌గా హోస్ట్ చేశావు 🎉
ఇప్పుడు పత్రాలు అప్‌లోడ్ చేసి, వాటిని సెర్చ్ చేసి, ట్యాగ్‌లతో మేనేజ్ చేయవచ్చు.

google video url:https://drive.google.com/file/d/1obgcvZ3dNU9P94luOPAHRgqOkqZWCkWK/view?usp=drivesdk
🌐 LinkedIn Project Post:https://www.linkedin.com/posts/sathvik-undefined-a55b50337_opensource-paperlessngx-selfhosting-activity-7390424675287191552-fpZC?utm_source=share&utm_medium=member_android&rcm=ACoAAFS1juEBr6lA7PBEe4bgQVHlgrMa38PTi9I
