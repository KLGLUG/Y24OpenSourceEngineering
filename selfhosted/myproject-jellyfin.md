"# My Self Hosted Project" 
# 🧩 Jellyfin Self-Hosted Media Server

## 📘 ప్రాజెక్ట్ వివరణ  
ఇది నేను స్వయంగా హోస్ట్ చేసిన ఒక మీడియా సర్వర్ (Jellyfin).  
ఈ ప్రాజెక్ట్ ద్వారా యూజర్లు తమ సినిమాలు, పాటలు, ఫోటోలు మరియు వీడియోలను తమ స్వంత కంప్యూటర్ లేదా సర్వర్‌లో నిల్వ చేసి చూడవచ్చు.  
ఇది **Netflix లాంటి ఫీచర్లు** కలిగి ఉంటుంది కానీ పూర్తిగా **free & open-source**.  
ప్రధాన ఉద్దేశ్యం — వ్యక్తులు తమ డేటాను third-party cloudలో కాకుండా స్వంత సిస్టమ్‌లో సురక్షితంగా హోస్ట్ చేసుకోవడం నేర్చుకోవడం.

---

## ⚙️ ఇన్స్టాలేషన్ స్టెప్‌లు (Ubuntu కోసం)

🧱 Step 1: సిస్టమ్ అప్‌డేట్ చేయండి
```
sudo apt update && sudo apt upgrade -y

📦 Step 2: Jellyfin Repository జోడించండి | Add the Jellyfin Repository

sudo apt install apt-transport-https gnupg -y
curl https://repo.jellyfin.org/ubuntu/jellyfin_team.gpg.key | sudo gpg --dearmor -o /usr/share/keyrings/jellyfin.gpg
echo "deb [signed-by=/usr/share/keyrings/jellyfin.gpg] https://repo.jellyfin.org/ubuntu $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/jellyfin.list



🧱 Step 3: Jellyfin Install చేయండి | Install Jellyfin

sudo apt update
sudo apt install jellyfin -y



▶ Step 4: సర్వర్‌ను స్టార్ట్ చేయండి | Start the Jellyfin Service

sudo systemctl enable jellyfin
sudo systemctl start jellyfin


🌐 Step 5: వెబ్ ఇంటర్‌ఫేస్ యాక్సెస్ చేయండి | Access the Web Interface

మీ బ్రౌజర్‌లో ఓపెన్ చేయండి:
👉 http://localhost:8096

Open your browser and visit:
👉 http://localhost:8096

మొదటి సారి ఓపెన్ చేసినప్పుడు మీరు యూజర్ అకౌంట్, మీడియా ఫోల్డర్, మరియు భాషను సెట్ చేయవచ్చు.


📺 Jellyfin ఏమి చేస్తుంది? | What Jellyfin Does

మీ కంప్యూటర్‌లో ఉన్న వీడియోలు, ఆడియోలు, ఫోటోలను ఒక centralized సర్వర్‌లో నిల్వ చేస్తుంది

వాటిని బ్రౌజర్, మొబైల్, లేదా Smart TV ద్వారా స్ట్రీమ్ చేయవచ్చు

User accounts, Playlists, మరియు Media libraries మేనేజ్ చేయడానికి అనువుగా ఉంటుంది

పూర్తిగా offline లేదా local network లో పని చేస్తుంది

No ads, No subscriptions, మరియు No tracking


Google Drive Link[https://drive.google.com/file/d/1TbymEnMB11YUhr2X1ns7s7cvJbAyP6UY/view?usp=sharing]

LinkedIn Article[https://www.linkedin.com/pulse/exploring-jellyfin-our-self-hosted-media-server-project-vasudev-pvnic]
