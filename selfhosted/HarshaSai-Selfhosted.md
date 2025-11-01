# Kutt URL Shortener — వివరణ & ఇన్‌స్టాలేషన్

Kutt ఒక తేలికైన, ఓపెన్‑సోర్స్ URL షార్టనర్. ఇది డొమెయిన్‌పై చిన్న URLలు సృష్టించి, క్లిక్ ట్రాకింగ్, లింక్ సెక్యూరిటీ మరియు ప్రైవేటు/పబ్లిక్ లింక్‌లను మేనేజ్ చేయడానికి వెబ్ UI/API ని అందిస్తుంది. మీరు దీన్ని స్వయంగా హొస్ట్ చేయవచ్చు (self‑host) అనగా మీ డేటా మీ నియంత్రణలోనే ఉంటుంది.

## ప్రధాన ఫీచర్లు

* షార్ట్ URL సృష్టించడం
* క్లిక్ ఎన్‌లైటిక్స్
* పాస్వర్డ్‑ప్రొటెక్టెడ్ లింకులు
* REST API కోసం ఇన్‌టిగ్రేషన్

## అవసరమైనవి (Prerequisites)

* Node.js (LTS సిఫార్సు)
* PostgreSQL డేటాబేస్
* Redis (ఐచ్ఛికంగా, క్యాషింగ్/రేట్‑లిమిటింగ్ కోసం)
* యాక్సెస్ ఉన్న సర్వర్ లేదా Docker

## ఇన్‌స్టాలేషన్ — Docker ద్వారా (సులభం)

1. పలు ఫైళ్లకు ఒక డైరెక్టరీలోకి వెళ్లండి:

```bash
git clone https://github.com/thedevs-network/kutt.git
cd kutt
```

2. `.env` ఫైలు సెట్ చేయండి (ఒక `.env.example` ఉంటే దానిని కాపీ చేయండి) మరియు PostgreSQL, Redis, సిట్‌యెల్ సెట్టింగ్స్ భర్తీ చేయండి:

```bash
cp .env.example .env
# .env లో మీ DATABASE_URL, REDIS_URL, SECRET_KEY వంటివి ఎంటర్ చేయండి
```

3. Docker Compose ఉపయోగిస్తే:

```bash
docker compose up -d
```

4. మైగ్రేషన్‌లు మరియు అడ్మిన్ యూజర్ సెటప్ అవసరమైతే README లోని కమాండ్లు అమలు చేయండి.

## ఇన్‌స్టాలేషన్ — మాన్యువల్ (Node.js)

1. కోడ్ క్లోన్ చేయండి మరియు డిపెండెన్సీలు ఇన్‌స్టాల్ చేయండి:

```bash
git clone https://github.com/thedevs-network/kutt.git
cd kutt
npm install
```

2. `.env` ఫైల్ సెట్ చేయండి (DATABASE_URL, SECRET_KEY, BASE_URL మొదలైనవి).
3. డేటాబేస్ మైగ్రేట్ చేయండి (README లోని సూచనలు పాటించండి).
4. సర్వర్ ప్రారంభించండి:

```bash
npm start
```

## కాన్‌ఫిగరేషన్ ముఖ్యాంశాలు

* `BASE_URL` — మీ షార్ట్‌డొమేన్.
* `DATABASE_URL` — PostgreSQL కనెక్షన్ స్ట్రింగ్.
* `SECRET_KEY` — JWT లేదా సెషన్ సీక్రెట్.

## Google Drive వీడియో URL

మీ ప్రాజెక్ట్ డెమో లేదా ట్యుటోరియల్ వీడియో ఇక్కడ చేర్చండి:

**Google Drive Video URL:** `https://drive.google.com/file/d/1AIqAj-f3V7yxOUzXYq6hleXYEGxbe7sI/view?usp=drive_link`
(దయచేసి `FILE_ID` ని మీ వీడియో ID తో మార్చండి.)

## LinkedIn URL

**LinkedIn Post URL (placeholder):** `https://www.linkedin.com/posts/harsha-sai-polnati-3281b6302_klu-projectexpo-selfhosted-activity-7382473197750919168-aCh2?utm_source=share&utm_medium=member_desktop&rcm=ACoAAE1FkVABBX1AOtAcDb8ud36aGOIIsMJV8OQ`
(దయచేసి మీది తో మార్చండి.)

## Team 

P Harsha Sai
M Gnana Karthik
