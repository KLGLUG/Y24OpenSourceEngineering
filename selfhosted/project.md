## Self-Hosted Project: Lychee

## ప్రాజెక్ట్ పేరు
Lychee – ఫోటో మేనేజ్మెంట్ సిస్టమ్

## ఇది ఏమి చేస్తుంది?
Lychee ఒక ఓపెన్ సోర్స్ ఫోటో మేనేజ్మెంట్ టూల్.  
మీ కంప్యూటర్ లేదా సర్వర్‌లో ఫోటోలను అప్లోడ్ చేసి,  
అవన్నీ ఆల్బమ్స్‌లో సింపుల్‌గా మేనేజ్ చేయడానికి ఇది ఉపయోగపడుతుంది.

Google Photos లాంటి ఫీచర్లు మీ దగ్గరే, మీ కంట్రోల్‌లో ఉంటాయి.

---

## ఫీచర్స్
- ఫోటోలను అప్లోడ్ చేయడం
- ఆల్బమ్స్ క్రియేట్ చేయడం
- ఫోటోలను షేర్ చేయడం
- ప్రైవేటు మరియు పబ్లిక్ యాక్సెస్ సపోర్ట్
- మొబైల్ మరియు వెబ్ బ్రౌజర్‌లో యాక్సెస్

---

## ఎలా ఇన్‌స్టాల్ చేయాలి (Telugu Steps)

### అవసరమైనవి
- PHP (>= 8.0)
- MySQL / MariaDB
- Apache / Nginx
- Git

### ఇన్‌స్టలేషన్ స్టెప్స్
1. GitHub నుండి Lychee ప్రాజెక్ట్‌ను క్లోన్ చేయండి:

```bash
git clone https://github.com/LycheeOrg/Lychee.git
cd Lychee

అవసరమైన ప్యాకేజీలు ఇన్స్టాల్ చేయండి:composer install

.env.example ఫైల్‌ని కాపీ చేసి .env పేరుతో మార్చండి:cp .env.example .env


మీ డేటాబేస్ సెట్టింగ్స్ .env ఫైల్‌లో ఎడిట్ చేయండి.

సర్వర్‌ రన్ చేయండి:php artisan serve

ఇప్పుడు బ్రౌజర్‌లో http://127.0.0.1:8000 ఓపెన్ చేస్తే Lychee వెబ్ యాప్ కనిపిస్తుంది.

https://drive.google.com/file/d/1T9L6zf4UqgGgcIy6Pxzwnq-2A_N7o-fu/view?usp=sharing 

https://www.linkedin.com/pulse/photo-hub-self-hosted-lychee-server-y-navya-sree-w6azc/?trackingId=v0MxNA10YhEOcvlR6%2FV7Tw%3D%3D