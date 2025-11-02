ఈ సర్వర్‌ని మేము Ubuntu లో self-host చేశాము.
ఇది ఒక low-latency, encrypted voice chat server.
Gaming, community discussions, మరియు open-source కార్యక్రమాల కోసం ఇది చాలా ఉపయోగకరమైనది.

ఈ సర్వర్ ద్వారా మీరు మీ private voice communication system ను సెట్ చేసుకోవచ్చు.
అంటే Zoom/Discord లాంటి voice chat సిస్టమ్, కానీ మీ నియంత్రణలో ఉండే మీ స్వంత సర్వర్.

🛠 ఇన్‌స్టలేషన్ స్టెప్స్ (Ubuntu)

sudo apt update
sudo apt install mumble-server -y
sudo dpkg-reconfigure mumble-server
sudo systemctl restart mumble-server

✅ సర్వర్ స్టార్ట్ & ఎనేబుల్

sudo systemctl enable mumble-server
sudo systemctl start mumble-server

క్లయింట్ లో కనెక్ట్ చేసేటప్పుడు:
IP: <మీ సర్వర్ IP>
Port: 64738
linkdin post:
https://www.linkedin.com/posts/sharvandeep-bhardwaj-kancharana-9851a3322_opensource-mumble-selfhosted-activity-7382314958572658688-91pX?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAFGKr7UB2-S4DjlBitwyAO8WBO-FtMyJ89k
