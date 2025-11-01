📦 नेक्स्टक्लाउड होस्टिंग सेटअप

यह रिपॉज़िटरी Nextcloud की होस्टिंग के लिए सेटअप फाइलें और कॉन्फ़िगरेशन डिटेल्स को शामिल करती है — यह एक शक्तिशाली ओपन-सोर्स प्लेटफ़ॉर्म है जो फाइल शेयरिंग और सहयोग के लिए उपयोग किया जाता है।


////////////////////////////////////////////////////////////////////////////

🧠 Nextcloud क्या है?

Nextcloud एक स्वयं-होस्टेड प्रोडक्टिविटी प्लेटफ़ॉर्म है जो आपको ये सुविधाएँ देता है:

अपनी फाइलों को सुरक्षित रूप से स्टोर, एक्सेस और शेयर करें

अपने डाटा को कई डिवाइसों में सिंक करें

कैलेंडर, कॉन्टैक्ट्स और चैट जैसे ऐप्स के साथ सहयोग करें

आधिकारिक वेबसाइट: https://nextcloud.com/

⚙️ इंस्टॉलेशन स्टेप्स (YouTube ट्यूटोरियल के आधार पर)

पूरा इंस्टॉलेशन गाइड यहाँ देख सकते हैं: 🎥 YouTube वीडियो ट्यूटोरियल

अगर आप मैन्युअली सेटअप करना चाहते हैं, तो नीचे दिए गए चरणों का पालन करें 👇

🧩 सिस्टम अपडेट और अपग्रेड करें sudo apt update && sudo apt upgrade -y

⚙️ Apache, MariaDB और PHP इंस्टॉल करें sudo apt install apache2 mariadb-server libapache2-mod-php php php-mysql php-xml php-mbstring php-curl php-gd php-zip unzip -y

🗄️ Nextcloud डेटाबेस बनाएं sudo mysql -u root -p CREATE DATABASE nextcloud; CREATE USER 'nextclouduser'@'localhost' IDENTIFIED BY 'your_password'; GRANT ALL PRIVILEGES ON nextcloud.* TO 'nextclouduser'@'localhost'; FLUSH PRIVILEGES; EXIT;

📥 Nextcloud डाउनलोड और एक्सट्रैक्ट करें wget https://download.nextcloud.com/server/releases/latest.zip unzip latest.zip sudo mv nextcloud /var/www/html/ sudo chown -R www-data:www-data /var/www/html/nextcloud

🧰 Apache कॉन्फ़िगरेशन सक्षम करें sudo nano /etc/apache2/sites-available/nextcloud.conf

निम्नलिखित को जोड़ें:

<VirtualHost *:80> DocumentRoot /var/www/html/nextcloud ServerName your-domain.com

<!-- <Directory /var/www/html/nextcloud/>
    Require all granted
    AllowOverride All
    Options FollowSymLinks MultiViews
</Directory> -->
फिर चलाएँ:

sudo a2ensite nextcloud.conf sudo a2enmod rewrite headers env dir mime sudo systemctl restart apache2

🌐 ब्राउज़र में सेटअप पूरा करें

अपने ब्राउज़र में जाएँ → http://localhost/nextcloud

एडमिन अकाउंट बनाएं, डेटाबेस की जानकारी भरें, और इंस्टॉलेशन पूरा करें।


///////////////////////////////////////////////////////////////////////////////////////



🧩 अगर कोई स्टेप काम नहीं कर रहा है, तो ऊपर दिया गया वीडियो लिंक खोलें और ध्यान से प्रक्रिया देखें। (कभी-कभी आपको PHP फाइल में "localhost" जोड़ना पड़ता है ताकि यह हर जगह काम करे।)

📘 संदर्भ (Reference)

पूरा गाइड यहाँ देखें: ▶️ https://youtu.be/Wh7Qo63EGJk?si=UcJa8uHUEm8zTTWL