🎥 Demo Video URL: https://drive.google.com/file/d/1hf5ehgALdg1_b7oY3Xf3rbdOR6PAqmsb/view?usp=drivesdk
🔗 LinkedIn Post URL: https://www.linkedin.com/posts/venkata-ramana-80a137369_opensource-opensource-kluniversity-activity-7382319162603282433-hZ7D
👥 Team Members:
- Venkata Ramana
- Sunil

తప్పకుండా ✅ — ఇక్కడ మీకు పై **QloApps Self-Hosting Documentation** ని **తెలుగులో** స్పష్టంగా, సులభంగా అర్థమయ్యే విధంగా ఇచ్చాను.
మీరు దీన్ని Ubuntu / Linux సిస్టమ్‌లో హోటల్ మేనేజ్‌మెంట్ కోసం సెట్‌అప్ చేయవచ్చు.

---

# 🏨 **QloApps స్వీయ హోస్టింగ్ డాక్యుమెంటేషన్**

## **1. పరిచయం**

**QloApps** అనేది ఉచితమైన, ఓపెన్ సోర్స్ హోటల్ రిజర్వేషన్ మరియు ప్రాపర్టీ మేనేజ్‌మెంట్ సిస్టమ్.
ఇది PHP మరియు MySQL ఆధారంగా పనిచేస్తుంది.
దీనిని మీ సొంత సర్వర్‌లో ఇన్‌స్టాల్‌ చేసి బుకింగ్స్‌, గదుల నిర్వహణను చేయవచ్చు.

---

## **2. సిస్టమ్ అవసరాలు**

| భాగం              | సిఫార్సు చేయబడిన వెర్షన్            |
| ----------------- | ----------------------------------- |
| ఆపరేటింగ్ సిస్టమ్ | Ubuntu 20.04 / 22.04 (64-bit)       |
| వెబ్ సర్వర్       | Apache 2.4 లేదా అంతకు పైగా          |
| PHP               | 7.4 – 8.1                           |
| డేటాబేస్          | MariaDB / MySQL 5.7 లేదా అంతకు పైగా |
| RAM               | కనీసం 2 GB                          |
| స్టోరేజ్          | కనీసం 2 GB ఖాళీ స్థలం               |

---

## **3. అవసరమైన ప్యాకేజీలు ఇన్‌స్టాల్ చేయడం**

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install apache2 -y
sudo apt install mariadb-server mariadb-client -y
sudo apt install php php-cli libapache2-mod-php php-mysql php-curl php-gd php-mbstring php-xml php-zip php-intl php-bcmath unzip -y
sudo a2enmod rewrite
sudo systemctl restart apache2
```

---

## **4. MariaDB సెక్యూర్ చేయడం**

కమాండ్ ఇవ్వండి:

```bash
sudo mysql_secure_installation
```

సిఫార్సు చేయబడిన సమాధానాలు:

| ప్రశ్న                                | సమాధానం |
| ------------------------------------- | ------- |
| Switch to unix_socket authentication  | Y       |
| Remove anonymous users                | Y       |
| Disallow root login remotely          | Y       |
| Remove test database and access to it | Y       |
| Reload privilege tables now           | Y       |

---

## **5. QloApps డేటాబేస్ సృష్టించడం**

MariaDB లోకి లాగిన్ అవ్వండి:

```bash
sudo mariadb
```

తర్వాత ఇవి టైప్ చేయండి:

```sql
CREATE DATABASE qloappsdb;
CREATE USER 'qloappsuser'@'localhost' IDENTIFIED BY 'StrongPassword123!';
GRANT ALL PRIVILEGES ON qloappsdb.* TO 'qloappsuser'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

---

## **6. QloApps డౌన్‌లోడ్ చేయడం**

```bash
cd /tmp
wget https://github.com/Qloapps/QloApps/archive/refs/tags/v1.7.0.zip -O qloapps.zip
unzip qloapps.zip
sudo mv QloApps-1.7.0 /var/www/html/qloapps
```

---

## **7. ఫోల్డర్ అనుమతులు ఇవ్వడం**

```bash
sudo chown -R www-data:www-data /var/www/html/qloapps
sudo chmod -R 755 /var/www/html/qloapps
sudo chmod -R 777 /var/www/html/qloapps/upload
sudo chmod -R 777 /var/www/html/qloapps/download
sudo chmod -R 777 /var/www/html/qloapps/cache
sudo chmod -R 777 /var/www/html/qloapps/logs
```

---

## **8. Apache వర్చువల్ హోస్ట్ సెట్‌అప్ చేయడం**

```bash
sudo nano /etc/apache2/sites-available/qloapps.conf
```

ఇది పేస్ట్ చేయండి:

```apache
<VirtualHost *:80>
    ServerAdmin admin@localhost
    DocumentRoot /var/www/html/qloapps
    ServerName qloapps.local

    <Directory /var/www/html/qloapps/>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
    </Directory>

    ErrorLog ${APACHE_LOG_DIR}/qloapps_error.log
    CustomLog ${APACHE_LOG_DIR}/qloapps_access.log combined
</VirtualHost>
```

తర్వాత సైట్ యాక్టివ్ చేయండి:

```bash
sudo a2ensite qloapps.conf
sudo systemctl restart apache2
```

`/etc/hosts` ఫైల్‌లో ఈ లైన్ జోడించండి:

```bash
127.0.0.1 qloapps.local
```

---

## **9. బ్రౌజర్‌లో ఇన్‌స్టాలేషన్ ప్రారంభించండి**

బ్రౌజర్‌లో ఓపెన్ చేయండి:

```
http://localhost/qloapps
```

లేదా

```
http://qloapps.local
```

తర్వాత విండోలో:

* భాష ఎంచుకోండి
* లైసెన్స్ అంగీకరించండి
* డేటాబేస్ వివరాలు ఇవ్వండి:

  * **Database name:** qloappsdb
  * **User:** qloappsuser
  * **Password:** StrongPassword123!

ఇన్‌స్టాలేషన్ పూర్తి అవుతుంది.

---

## **10. ఇన్‌స్టాలేషన్ తర్వాత చేయవలసినవి**

1. **install ఫోల్డర్ తొలగించండి:**

   ```bash
   sudo rm -rf /var/www/html/qloapps/install
   ```

2. **అడ్మిన్ ప్యానెల్ యాక్సెస్ చేయండి:**

   ```
   http://localhost/qloapps/admin
   ```

3. **PHP సెట్టింగ్స్ మార్చాలి అనుకుంటే:**

   ```bash
   sudo nano /etc/php/8.1/apache2/php.ini
   ```

   ఇవి మార్చండి:

   ```ini
   upload_max_filesize = 16M
   post_max_size = 16M
   max_execution_time = 300
   ```

   సేవ్ చేసి రీస్టార్ట్ చేయండి:

   ```bash
   sudo systemctl restart apache2
   ```

---

## **11. బ్యాకప్ మరియు మెయింటెనెన్స్**

* **డేటాబేస్ బ్యాకప్:**

  ```bash
  mysqldump -u root -p qloappsdb > qloapps_backup.sql
  ```
* **ఫైళ్ళ బ్యాకప్:**

  ```bash
  tar -czvf qloapps_files_backup.tar.gz /var/www/html/qloapps
  ```

---

## **12. ఉపయోగకరమైన లింకులు**

* అధికారిక డాక్యుమెంటేషన్: [https://devdocs.qloapps.com](https://devdocs.qloapps.com)
* డెమో వెబ్‌సైట్: [https://demo.qloapps.com](https://demo.qloapps.com)
* ఫోరం / సపోర్ట్: [https://forums.qloapps.com](https://forums.qloapps.com)

---

