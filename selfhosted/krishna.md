 Paperless-ngx Self-Hosting డాక్యుమెంటేషన్ (తెలుగు)
 Paperless-ngx అంటే ఏమిటి?
Paperless-ngx అనేది ఓపెన్ సోర్స్ డాక్యుమెంట్ మేనేజ్‌మెంట్ సిస్టమ్ (DMS).
ఇది ఈ విధంగా ఉపయోగపడుతుంది:
•	స్కాన్ చేసిన పత్రాలను డిజిటల్‌గా భద్రపరచుకోవచ్చు
•	OCR (Optical Character Recognition) ద్వారా పత్రాలలో ఉన్న టెక్స్ట్‌ని సెర్చ్ చేయవచ్చు
•	ట్యాగ్స్ మరియు కేటగిరీల ద్వారా ఫైళ్లను సులభంగా నిర్వహించవచ్చు
________________________________________
 1 అవసరమైనవి
Paperless-ngx ను హోస్ట్ చేయడానికి ముందు ఈ వాటి అవసరం ఉంటుంది:
•	Ubuntu / Linux OS
•	Docker మరియు Docker Compose
•	కనీసం 2GB RAM
•	10GB డిస్క్ స్పేస్
•	స్థిరమైన ఇంటర్నెట్ కనెక్షన్
________________________________________
 2 Docker మరియు Docker Compose ఇన్‌స్టాల్ చేయడం
టెర్మినల్‌లో ఈ కమాండ్లు ఇవ్వండి 👇
sudo apt update
sudo apt install -y docker.io docker-compose
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER
గమనిక: పై కమాండ్‌ల తరువాత సిస్టమ్‌ను reboot చేయండి లేదా log out → log in అవ్వండి.
తర్వాత చెక్ చేయండి:
docker compose version
________________________________________
 3 Paperless ఫోల్డర్ సృష్టించడం
mkdir ~/paperless
cd ~/paperless
________________________________________
 4 docker-compose.yml ఫైల్ సృష్టించడం
ఫైల్ ఓపెన్ చేయండి:
nano docker-compose.yml
ఈ కంటెంట్‌ని పేస్ట్ చేయండి 
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
________________________________________
 5 సర్వర్ స్టార్ట్ చేయడం
docker compose up -d
రన్ అవుతున్న కంటైనర్లు చూడడానికి:
docker ps
ఇవి కనపడాలి:
•	paperless-webserver-1
•	paperless-db-1
•	paperless-broker-1
________________________________________
 6 వెబ్ ఇంటర్‌ఫేస్ ఓపెన్ చేయడం
బ్రౌజర్‌లో ఈ అడ్రస్‌లోకి వెళ్లండి 👇
👉 http://localhost:8080
ఇంకో కంప్యూటర్‌ నుండి యాక్సెస్ చేయాలంటే:
👉 http://<నీ సర్వర్ IP>:8080
నీ సర్వర్ IP తెలుసుకోవాలంటే:
hostname -I
________________________________________
 7 అడ్మిన్ యూజర్ సృష్టించడం
docker exec -it paperless-webserver-1 bash
python manage.py createsuperuser
ఇప్పుడు నీకు కావాల్సిన username, email, password ఇవ్వండి.
తర్వాత exit చేయండి:
exit
________________________________________
 8 సర్వర్ చెక్ చేయడం
బ్రౌజర్‌లో మళ్లీ వెళ్లండి 👉 http://localhost:8080
నీ క్రియేట్ చేసిన యూజర్‌తో లాగిన్ అవ్వండి.
PDF ఫైల్ అప్‌లోడ్ చేసి ప్రాసెస్ అవుతుందో చూడండి. 🎉
________________________________________
 9 సర్వర్ మేనేజ్ చేయడం
చర్య	కమాండ్
సర్వర్ ఆపడం	docker compose down
సర్వర్ రీస్టార్ట్	docker compose up -d
లాగ్స్ చూడడం	docker logs -f paperless-webserver-1
రన్ అవుతున్న కంటైనర్లు	docker ps
________________________________________
 10 సమస్యలు వచ్చినప్పుడు
సమస్య	పరిష్కారం
Port 8080 already in use	"8090:8000"కి మార్చండి
“Permission denied”	sudo usermod -aG docker $USER చేసి రీబూట్ చేయండి
వెబ్ పేజ్ ఓపెన్ కావడం లేదు	కంటైనర్లు రన్ అవుతున్నాయో చూడండి, ఫైర్‌వాల్ చెక్ చేయండి
________________________________________
 11 Uninstall చేయాలంటే
docker compose down -v
rm -rf ~/paperless
________________________________________
 ముగింపు
ఇప్పుడు నువ్వు నీ సొంత Paperless-ngx సర్వర్‌ని సక్సెస్‌ఫుల్‌గా హోస్ట్ చేశావు 🎉
ఇప్పుడు నువ్వు పత్రాలు అప్‌లోడ్ చేసి, వాటిని సెర్చ్ చేసి, ట్యాగ్‌లతో మేనేజ్ చేయవచ్చు.


https://www.linkedin.com/posts/krishna-bangaru-88a616366_we-successfully-deployed-paperless-ngx-a-activity-7390447052939436033-eUQ1?utm_source=social_share_send&utm_medium=android_app&rcm=ACoAAFrcJmoBs6fJitGGPnFbVthW-Aud-ogXGmQ&utm_campaign=copy_link
