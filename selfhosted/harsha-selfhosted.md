# 🌐 4gaBoards — Self Hosted Project Documentation

## 🎥 Google Drive Video Link
[🎬 Watch the Demo Video](https://drive.google.com/file/d/1YeVoNYBnQE6tYIJjhwSvtlxeHmnrEq4I/view?usp=sharing)

## 🔗 LinkedIn Post
[🔗 LinkedIn Project Post](https://www.linkedin.com/posts/siva-harsha-vardhan-reddy_excited-to-share-my-project-4ga-boards-activity-7389595413214867456-0VeA?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAFPMJPYBnnZF8UDad8wmhnEC8o442dqERz0)

## 👨‍💻 Team Members
- Siva Harsha Vardhan Reddy  
- Lokesh

---


📘 ప్రాజెక్ట్ శీర్షిక: 4gaBoards — ఓపెన్ సోర్స్ ప్రాజెక్ట్ మేనేజ్‌మెంట్ సిస్టమ్
🔹 1. ప్రాజెక్ట్ అవలోకనం (Project Overview)

4gaBoards అనేది ఓపెన్ సోర్స్ ప్రాజెక్ట్ మేనేజ్‌మెంట్ టూల్.
ఇది టీమ్స్, విద్యార్థులు మరియు ప్రొఫెషనల్స్ తమ పనిని సులభంగా ట్రాక్ చేయడానికి, టాస్కులను విభజించడానికి మరియు రియల్ టైమ్‌లో సహకరించడానికి ఉపయోగపడుతుంది.

ఈ ప్రాజెక్ట్ Kanban Board మోడల్ ఆధారంగా పనిచేస్తుంది.
ఇది పూర్తిగా Docker Compose ఉపయోగించి డిప్లాయ్ చేయబడింది మరియు PostgreSQL డేటాబేస్ మరియు Node.js (Strapi CMS) బ్యాక్‌ఎండ్‌పై ఆధారపడి ఉంటుంది.

🎯 2. లక్ష్యాలు (Objectives)

రియల్ టైమ్ ప్రాజెక్ట్ మేనేజ్‌మెంట్ సిస్టమ్ రూపొందించడం.

టాస్క్‌లను వర్గీకరించి (categorize) ప్రాజెక్ట్‌లను సులభంగా మానిటర్ చేయడం.

యూజర్‌ ఫ్రెండ్లీ ఇంటర్‌ఫేస్ కలిగిన సిస్టమ్‌ను అభివృద్ధి చేయడం.

Docker ద్వారా డిప్లాయ్ చేయగలిగే స్కేలబుల్ అప్లికేషన్‌ను రూపొందించడం.

⚙️ 3. ముఖ్య ఫీచర్లు (Key Features)

యూజర్ ఆథెంటికేషన్ (Admin, Teacher, Student).

టాస్క్ సృష్టి, అసైన్‌మెంట్ మరియు ప్రోగ్రెస్ ట్రాకింగ్.

ప్రాజెక్ట్ ఆధారిత బోర్డ్స్ ద్వారా విజువల్ మేనేజ్‌మెంట్.

Docker వాల్యూమ్స్ ద్వారా డేటా శాశ్వతంగా నిల్వ చేయడం.

ఫైల్ మరియు అటాచ్మెంట్ సపోర్ట్ (avatars, documents, images).

PostgreSQL డేటాబేస్‌కి సురక్షిత కనెక్షన్.

సులభమైన వెబ్ UI మరియు స్మూత్ UX.

🏗️ 4. సిస్టమ్ ఆర్కిటెక్చర్ (System Architecture)
⚡ Architecture Flow:

User → React Frontend → Node.js Backend → PostgreSQL Database → Docker Containers

🔧 కాంపోనెంట్స్ (Components):

Frontend: React.js

Backend: Node.js (Strapi Framework)

Database: PostgreSQL

Containerization: Docker Compose

Hosting Environment: Localhost / VPS

💻 5. ఉపయోగించిన టెక్నాలజీలు (Technologies Used)
లేయర్ (Layer)	టెక్నాలజీ (Technology)
Frontend	React.js
Backend	Node.js (Strapi CMS)
Database	PostgreSQL
Containerization	Docker, Docker Compose
Version Control	Git & GitHub
Hosting	Localhost / Remote Server
🧩 6. ఇన్‌స్టాలేషన్ మరియు సెటప్ (Installation and Setup)
🪜 Step 1: రిపోజిటరీని క్లోన్ చేయండి
git clone https://github.com/harsha08-2k6/4gaBoards.git
cd 4gaBoards

🪜 Step 2: Environment Variables సెట్ చేయండి

.env అనే ఫైల్ సృష్టించి ఈ వివరాలను జోడించండి:

POSTGRES_DB=4gaBoards
POSTGRES_PASSWORD=superstrongpass123
DATABASE_URL=postgresql://postgres:superstrongpass123@db:5432/4gaBoards
SECRET_KEY=notsecretkey
BASE_URL=http://localhost:3000
NODE_ENV=production

🪜 Step 3: Docker Compose రన్ చేయండి
sudo docker compose up -d

🪜 Step 4: అప్లికేషన్‌ యాక్సెస్ చేయండి

Web App URL: http://localhost:3000

PostgreSQL Port: 5432

📁 7. ప్రాజెక్ట్ నిర్మాణం (Project Structure)
4gaBoards/
├── docker-compose.yml
├── backend/                # Node.js (Strapi) backend
├── frontend/               # React frontend
├── .env                    # Environment variables
├── volumes/                # Docker volumes
└── README.md

🎓 8. నేర్చుకున్న విషయాలు (Learning Outcomes)

ఈ ప్రాజెక్ట్‌ ద్వారా నేర్చుకున్నవి:

Docker ద్వారా మల్టీ కంటైనర్ అప్లికేషన్లు ఎలా డిప్లాయ్ చేయాలో.

Node.js మరియు PostgreSQL డేటాబేస్‌ల మధ్య కనెక్షన్ ఎలా ఏర్పాటు చేయాలో.

సెక్యూర్ ఎన్విరాన్‌మెంట్ కాన్ఫిగరేషన్ మరియు డేటా పర్సిస్టెన్స్ కాన్సెప్ట్‌లు.

రియల్ టైమ్ వెబ్ అప్లికేషన్ల డిజైన్ మరియు డిప్లాయ్‌మెంట్ విధానం.

🚀 9. భవిష్యత్తు అభివృద్ధులు (Future Enhancements)

ఇమెయిల్ వెరిఫికేషన్ మరియు నోటిఫికేషన్ సిస్టమ్.

WebSocket ఆధారిత లైవ్ అప్‌డేట్స్.

క్లౌడ్ ప్లాట్‌ఫార్మ్‌ (AWS / Render / Railway) లో డిప్లాయ్‌మెంట్.

Analytics Dashboard చేర్చడం.

🪪 10. లైసెన్స్ (License)

ఈ ప్రాజెక్ట్ MIT License కింద విడుదల చేయబడింది.
దీనిని ఎవరైనా ఉచితంగా ఉపయోగించవచ్చు, మార్చవచ్చు మరియు పంపిణీ చేయవచ్చు.

🔗 11. రిపోజిటరీ లింక్ (Repository Link)

https://github.com/harsha08-2k6/4gaBoards

🏁 12. ముగింపు (Conclusion)

4gaBoards ప్రాజెక్ట్‌ ద్వారా ప్రాజెక్ట్ మేనేజ్‌మెంట్, టీం కలబరేషన్ మరియు రియల్ టైమ్ డిప్లాయ్‌మెంట్‌పై లోతైన అవగాహన ఏర్పడింది.
ఇది ఒక పూర్తి స్థాయి ఫుల్‌స్టాక్ డెవలప్‌మెంట్ ప్రాజెక్ట్, భవిష్యత్తులో ప్రొడక్షన్ స్థాయికి తీసుకెళ్లగలిగే సామర్థ్యం కలిగి ఉంది.
