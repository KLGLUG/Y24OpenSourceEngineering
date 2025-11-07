# 🧅 OnionShare Self‑Hosted Documentation (Telugu)

## 🔰 OnionShare అంటే ఏమిటి?  
OnionShare ఒక **ప్రైవసీ మరియు సెక్యూరిటీ ఆధారిత Self‑Hosted టూల్**, దీని ద్వారా మనం **ఫైళ్లను share చేయడం, anonymous chat చేయడం, websites host చేయడం** వంటి పనులు **TOR network ద్వారా సురక్షితంగా** చేయవచ్చు.  
ఇది ఉపయోగించినప్పుడు మీ **IP address, Identity, Location పూర్తిగా గోప్యంగా** ఉంటుంది.

---

## 🖥️ Installation – Linux (Ubuntu ఆధారంగా)  

> క్రింద ఇచ్చిన సూచనలు Ubuntu/Debian ఆధారిత Linux కోసం.

### 1️⃣ అవసరమైన Packages Update చేయండి  
```bash
sudo apt update && sudo apt upgrade -y
```

### 2️⃣ OnionShare ఇన్స్టాల్ చేయండి  
```bash
sudo apt install onionshare -y
```

లేదా Snap ద్వారా కూడా ఇన్స్టాల్ చేయవచ్చు:

```bash
sudo snap install onionshare
```

### 3️⃣ Tor Service Enable చేయండి  
```bash
sudo systemctl enable tor
sudo systemctl start tor
```

### 4️⃣ OnionShare ప్రారంభించడం  
GUI version కోసం:  
```bash
onionshare
```

Terminal CLI version కోసం:  
```bash
onionshare --help
```

---

## ⚙️ Features (సౌకర్యాలు)

| Feature | వివరాలు (Telugu) |
|--------|--------------------|
| File Sharing | ఎలాంటి server లేదా 3rd‑party లేకుండా TOR ద్వారా సురక్షితంగా ఫైళ్లను పంపవచ్చు |
| Website Hosting | Static website ని anonymous గా host చేయవచ్చు |
| Chat Service | Anonymous encrypted chat room రూపొందించవచ్చు |
| Completely Private | Logs ఉండవు, IP leak కాదు, Identity safe |
| TOR Based | End‑to‑end secure tor service తో data transfer |

---

## 🌐 OnionShare Self‑Hosted Usage  

### 🟣 File Share చేయడం  
```bash
onionshare --share <file_name>
```
ఈ command తీసుకున్న తర్వాత మీరు share చేయడానికి ఒక `.onion` link పొందుతారు. ఆ link ఎవరికైతే ఇస్తారో వారు మాత్రమే TOR ద్వారా ఫైల్ పొందగలరు.

### 🟣 Website Host చేయడం  
```bash
onionshare --website <website_folder_path>
```

### 🟣 Anonymous Chat Room  
```bash
onionshare --chat
```

దీనివల్ల ఒక anonymous chat portal సృష్టించబడుతుంది, దాని `.onion` link anyone with tor browser use చేయవచ్చు.

---

## 🎥 వీడియో డెమో  
> **ఇక్కడ మీరు మీ Google Drive వీడియో లింక్ పేస్ట్ చేయాలి:**  
🔗 Video Link: *Pending — Add before PR*  

---

## 🔗 LinkedIn పోస్ట్  
> **మీరు LinkedIn లో పోస్ట్ చేసిన తర్వాత ఈ లింక్ ఇక్కడ ఇవ్వాలి:**  
🔗 LinkedIn Post: *Pending — Add before PR*  

---

## 👥 Team Members  
- Hasan (Hasan‑8326)  
- *మీ teammates పేర్లు ఇక్కడ జోడించండి*

---

## ✅ ముగింపు  
OnionShare ఒక శక్తివంతమైన Self‑Hosted security‑focused tool. Privacy, Security, మరియు Anonymous communication కావాలనుకునే వారికి ఇది చాలా ఉపయోగకరం.

---

> Documentation contributed as part of Issue #73 of KLGLUG/Y24OpenSourceEngineering.
