# Self Hosted Project - BOOKSTACK

## Description
**BookStack** is an open-source, self-hosted platform for storing and organizing information like documentation, wikis, or notes.  
It’s built with PHP and Laravel and offers a clean, user-friendly interface for creating pages, organizing them into chapters and books, and managing access for teams.  
BookStack is ideal for knowledge bases, internal documentation, or collaborative writing.


## Installation 
ఈ స్క్రిప్ట్ కొత్త Ubuntu 22.04 సిస్టమ్‌లో మాత్రమే ఉపయోగించాలి. ఇప్పటికే వెబ్‌సైట్‌లు లేదా డేటాబేస్‌లు ఉన్న కంప్యూటర్‌లో ఇది అమలు చేస్తే అవి దెబ్బతినే అవకాశం ఉంటుంది.

స్క్రిప్ట్‌ని డౌన్‌లోడ్ చేయండి:
wget https://codeberg.org/bookstack/devops/raw/branch/main/scripts/installation-ubuntu-22.04.sh -O installation-ubuntu-22.04.sh

స్క్రిప్ట్‌లో ఏముంది చూడండి:
less installation-ubuntu-22.04.sh
(ఇది ఏ ఫైళ్ళను ఇన్‌స్టాల్ చేస్తుందో, ఏ సెట్టింగ్స్ మార్చుతుందో ముందుగా చూసుకోవాలి.)

స్క్రిప్ట్‌ను అమలు చేయగలిగేలా మార్చండి:
chmod a+x installation-ubuntu-22.04.sh

స్క్రిప్ట్‌ను అడ్మిన్ హక్కులతో నడపండి:
sudo ./installation-ubuntu-22.04.sh
(ఇది Apache, MySQL, PHP, BookStack లను ఆటోమేటిక్‌గా ఇన్‌స్టాల్ చేస్తుంది.)

ప్రాసెస్ పూర్తయిన తర్వాత, ఎర్రర్లు ఉన్నాయా లేదో చెక్ చేయండి.
ఫైల్ లాగ్‌ను చూడటానికి: tail -f installation-log.txt

Apache మరియు MySQL సర్వీసులు సరిగ్గా నడుస్తున్నాయా చూడండి:
sudo systemctl status apache2
sudo systemctl status mysql

BookStack ఫోల్డర్ /var/www/bookstack లో సరిగ్గా ఉందో చూసి, అవసరమైతే ఫైల్ యజమానిని మార్చండి:
sudo chown -R www-data:www-data /var/www/bookstack

BookStack సైట్ ఓపెన్ చేసి లాగిన్ అవ్వండి — మొదటిసారి ఓపెన్ చేసినప్పుడు సర్వర్ యూర్ఎల్ సరిగ్గా ఉందో .env ఫైల్లో చెక్ చేయండి.

అన్ని సరిగ్గా పని చేస్తే, చివరగా బ్యాకప్ తీసుకోవడం మరియు సెక్యూరిటీ సెట్టింగ్స్ పెట్టడం మర్చిపోవద్దు 

## Video Demonstration
https://drive.google.com/file/d/1ZxbmRDJZV0aHPVGaGZYpJ4FW2azUL2IV/view?usp=drive_link

## LinkedIn Post
https://www.linkedin.com/posts/koushitha-tadiboina-787427350_opensource-kluniversity-foss-activity-7383768629764403200-HqWH?utm_source=share&utm_medium=member_android&rcm=ACoAAFegxZcBK-GKkoglpRkpLOIES3YBmnAqI50

## Team Members
2400030734 - Koushitha Tadiboina
2400030727 - Snehitha Kurapati
