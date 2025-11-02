## ప్రాజెక్ట్ వివరణ  
ఇది నేను స్వయంగా హోస్ట్ చేసిన ఒక వెబ్ అప్లికేషన్.  
ఈ ప్రాజెక్ట్ ద్వారా యూజర్లు తమ స్వంత కంప్యూటర్ లేదా సర్వర్‌లో సాఫ్ట్‌వేర్‌ను ఎలా హోస్ట్ చేయాలో నేర్చుకోగలరు.  
ఇది డేటా నిల్వ (Data Storage), యూజర్ ఇంటర్‌ఫేస్ (User Interface), మరియు ఫీచర్ మేనేజ్‌మెంట్ (Feature Management) వంటి ప్రధాన అంశాలను చూపిస్తుంది.  
ప్రాజెక్ట్ యొక్క ముఖ్య ఉద్దేశ్యం — విద్యార్థులు మరియు డెవలపర్లు self-hosting ప్రక్రియను సులభంగా అర్థం చేసుకుని ప్రాక్టికల్ అనుభవం పొందేలా చేయడం.

## ఇన్స్టాలేషన్ స్టెప్

Rocket.Chat Deployment using Docker & Docker Compose (సంక్షిప్త ఆధునిక తెలుగు మార్గదర్శిని)
 Step 1: Install Docker, Docker Compose & Git

మీ లినక్స్ సిస్టమ్‌లో Docker, Docker Compose (v2) మరియు Git ఉండాలి.
క్రింది కమాండ్‌తో సులభంగా ఇన్స్టాల్ చేయవచ్చు:

curl -L https://get.docker.com | sh
sudo apt install git


Docker commands ను sudo లేకుండా రన్ చేయాలంటే:

whoami
sudo usermod -aG docker $USER
sudo reboot


సిస్టమ్ రీస్టార్ట్ అయిన తర్వాత మీరు Docker‌ని సాధారణ యూజర్‌గా రన్ చేయగలరు.

 Step 2: Fetch Rocket.Chat Compose Files

Rocket.Chat అధికారిక repository ని clone చేయండి:

git clone --depth 1 https://github.com/RocketChat/rocketchat-compose.git
cd rocketchat-compose


ఇందులో compose.yml, .env.example మరియు ఇతర సహాయక కాన్ఫిగరేషన్ ఫైళ్లుంటాయి.
మీ సొంత .env ఫైల్ సృష్టించండి:

cp .env.example .env

 Step 3: Configure Rocket.Chat

.env ఫైల్‌ను ఓపెన్ చేసి అవసరమైన వేరియబుల్స్ సెట్ చేయండి:

nano .env


ఉదాహరణకు:

RELEASE=7.5.0
DOMAIN=localhost
ROOT_URL=http://localhost


Grafana Monitoring యాక్టివేట్ చేయాలంటే:

GRAFANA_PATH=/grafana
GRAFANA_ADMIN_PASSWORD=your_secure_password

 Step 4: Optional Configurations

External MongoDB ఉపయోగించాలంటే .env లో ఈ లైన్ జోడించండి:

MONGO_URL=mongodb://<user>:<pass>@host:27017/<dbName>?replicaSet=<rs>&ssl=true&authSource=admin


Registration Token ఉన్నట్లయితే:

REG_TOKEN=your_token_here

▶ Step 5: Launch Rocket.Chat

అన్ని సర్వీసులు ప్రారంభించడానికి:

docker compose -f compose.database.yml -f compose.monitoring.yml -f compose.traefik.yml -f compose.yml up -d


సర్వీసులు రన్ అవుతున్నాయో చూడండి:

docker ps

 Step 6: Access Workspace

Local Testing: http://localhost:3000

Production: మీ ROOT_URL (e.g., https://your-domain.com
)
మొదటి admin user సృష్టించి సెట్టప్ పూర్తి చేయండి.

Grafana Dashboard కు యాక్సెస్:

https://your-domain.com/grafana
User: admin  
Password: మీరు .env లో సెట్ చేసిన GRAFANA_ADMIN_PASSWORD

 Step 7: Update File Storage

డిఫాల్ట్‌గా Rocket.Chat GridFS ఉపయోగిస్తుంది.
Production లో performance మరియు scalability కోసం Amazon S3, Google Cloud Storage, లేదా MinIO వంటి object storage సర్వీసులు ఉపయోగించడం సిఫార్సు.

 Update Rocket.Chat Version

.env లో version మార్చండి:

RELEASE=7.6.0


తర్వాత క్రింది కమాండ్‌తో ఇమేజ్ అప్‌డేట్ చేయండి:

docker compose -f compose.yml up -d

 Securing with Nginx + Let’s Encrypt

Traefik స్థానంలో Nginx ఉపయోగించాలంటే:

.env లో ఈ విలువలు సెట్ చేయండి:

DOMAIN=localhost
ROOT_URL=http://localhost
LETSENCRYPT_ENABLED=false


Rocket.Chat‌ను Traefik లేకుండా రన్ చేయండి:

docker compose -f compose.database.yml -f compose.monitoring.yml -f compose.yml up -d


Nginx install చేసి HTTPS సెట్టప్:

sudo apt update
sudo apt install nginx certbot
sudo certbot certonly --standalone --email your@email.com -d your-domain.com


/etc/nginx/sites-available/default లో Rocket.Chat reverse proxy config జోడించండి.

Test చేసి restart చేయండి:

sudo nginx -t
sudo systemctl restart nginx


ఇప్పుడే మీ Rocket.Chat workspace సురక్షిత HTTPS లో రన్ అవుతుంది.

 Backup & Restore MongoDB

Backup:

docker ps -a
docker exec <mongo_container> sh -c 'mongodump --archive' > db.dump


Restore:

docker exec -i <mongo_container> sh -c 'mongorestore --archive' < db.dump

 Monitoring & Logs

Rocket.Chat logs చూడటానికి:

docker compose logs -f rocketchat


MongoDB logs:

docker logs -f <MongoDB_Container_Name>


Traefik/Nginx logs:

sudo tail -f /var/log/nginx/access.log
sudo tail -f /var/log/nginx/error.log

 ముగింపు

మీరు ఇప్పుడు Docker మరియు Docker Compose ద్వారా Rocket.Chat ను సఫలంగా సెట్ చేశారు.
తర్వాతి స్టెప్స్:

User Guides చూడండి.

Workspace Administration కన్ఫిగర్ చేయండి.

Marketplace apps ద్వారా ఫీచర్స్ విస్తరించండి.






##  డెమో వీడియో  
[ఇక్కడ క్లిక్ చేసి వీడియో చూడండి](https://drive.google.com/file/d/1UvvA2VqnwtF1BKYnKR-5Yc25Y6BPZeCM/view?usp=sharing)



##  లింక్‌డిన్ పోస్ట్  

[ఇక్కడ క్లిక్ చేసి వీడియో చూడండి]	https://www.linkedin.com/pulse/our-self-hosted-rocketchat-project-hemanth-gvs-j6ote



##  టీమ్ సభ్యులు
- జి.వి.ఎస్. హేమంత్  
- రమేష్ కుమార్ కందులా






