# 🎵 Navidrome Self-Hosted Music Server

## 📌 Project Overview
Navidrome is a lightweight, self-hosted music streaming server that allows you to access your personal music collection from anywhere. It works similar to Spotify but runs on your own server, ensuring privacy, control, and flexibility.

---

## ⚙️ Features
- Stream your personal music library from any device.
- Clean and responsive web interface.
- Multi-user support with individual libraries and playlists.
- Compatible with Subsonic API-based mobile apps.
- Lightweight and easy to install on low-resource systems.

---

## 💻 Installation Steps

### 🧩 Using Docker (Recommended)
1. **Install Docker** on your system.
2. Pull the Navidrome Docker image:
   ```bash
   docker pull deluan/navidrome:latest
3. Create directories for data and music:
    mkdir -p ~/navidrome/music ~/navidrome/data
4. Run the Navidrome container:
  docker run -d \
  --name navidrome \
  -v ~/navidrome/music:/music \
  -v ~/navidrome/data:/data \
  -p 4533:4533 \
  deluan/navidrome:latest
5. Open your browser and visit:
  http://localhost:4533
6. Create an admin account and start adding your music collection.

## 💼 LinkedIn Post URL
   https://www.linkedin.com/posts/himabindu-sunkari-3665b535a_opensource-kluniversity-foss-activity-7382296992141582336-GGbk?utm_source=share&utm_medium=member_android&rcm=ACoAAFlu-r4BzxlTHbNw29Dt8vJWQpxTRcElZkk
   
## 👥 Team Members

Himabindu Sunkari

Sathvika Undala

## 🌎 Local Language Description (Telugu)

నావీడ్రోమ్ అనేది మనం స్వంతంగా హోస్ట్ చేసుకునే మ్యూజిక్ సర్వర్. దీని ద్వారా మన పాటలను ఎక్కడినుంచైనా వినవచ్చు. ఇది తేలికగా పనిచేసే సాఫ్ట్‌వేర్ మరియు మన డేటా పూర్తిగా మన దగ్గరే ఉంటుంది. ఇది స్పాటిఫై లాంటి అనుభూతి ఇస్తుంది కానీ మన సొంత సర్వర్‌ మీద నడుస్తుంది.



## 💬 నా అనుభవం (My Experience)

నావీడ్రోమ్‌ సర్వర్‌ను హోస్ట్‌ చేసే సమయంలో నాకు చాలా కొత్త విషయాలు నేర్చుకున్నాను. మొదటిసారి డాకర్‌ వాడటం, కంటైనర్‌ క్రియేట్‌ చేయడం, పోర్ట్‌లను మ్యాప్‌ చేయడం వంటి వాటిని ప్రాక్టికల్‌గా అర్థం చేసుకున్నాను. 
ఇన్‌స్టాలేషన్‌ పూర్తయ్యిన తర్వాత నా సొంత పాటలను వెబ్‌ ఇంటర్‌ఫేస్‌లో వినడం చాలా ఆసక్తికరంగా అనిపించింది. 
ఇది స్పాటిఫై లాంటి అనుభూతిని ఇచ్చింది కానీ నా సొంత సర్వర్‌ మీద నడుస్తుందనే విషయం నాకు ఒక సంతృప్తి కలిగించింది. 

ఈ ప్రాజెక్ట్‌ ద్వారా సర్వర్‌ హోస్టింగ్‌, నెట్‌వర్కింగ్‌ మరియు ఓపెన్‌ సోర్స్‌ ప్రాజెక్ట్‌లలో కాంట్రిబ్యూట్‌ చేయడం ఎలా అనేది నేర్చుకున్నాను. 
ఇది నాకు ఒక మంచి ప్రాక్టికల్‌ లెర్నింగ్‌ అనుభవంగా నిలిచింది.

---

