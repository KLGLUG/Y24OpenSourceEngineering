Pastefy
ante enti? 

Pastefy oka open-source self-hosted paste-sharing platform. Ante, meeru mee own server lo install chesi, code snippets, text notes, files ni paste chesi share cheyyachu.

Idi Pastebin or GitHub Gist laanti platform ki alternative.

Main features:

Raw view, code view, syntax highlighting.

Client-side encryption (ante browser lo data encrypt avutundi), folders, pastes list, API support.

Dini use cheste mee data meeku control lo untundi, ante privacy & security better untayi.

Ela install cheyyali? (How to install)

Idi koncham technical untundi — mostly Docker use chesi setup cheyyali.

Step-by-step:

Mee server / computer lo Docker install cheyyandi. (Optional: docker-compose kuda install cheyyachu.)

Ee command use chesi Docker lo run cheyyachu:

docker run -p 8080:80 \
  --env HTTP_SERVER_PORT=80 \
  --env HTTP_SERVER_CORS="*" \
  --env DATABASE_DRIVER=mysql \
  --env DATABASE_NAME=pastefy \
  --env DATABASE_USER=pastefy \
  --env DATABASE_PASSWORD=yourpassword \
  --env DATABASE_HOST=host \
  --env DATABASE_PORT=3306 \
  --env SERVER_NAME=http://yourdomain.com \
  interaapps/pastefy


Leda, docker-compose.yml create chesi ila veyyachu:

version: "3"
services:
  db:
    image: mysql:latest
    environment:
      MYSQL_DATABASE: pastefy
      MYSQL_USER: pastefy
      MYSQL_PASSWORD: yourpassword
      MYSQL_ROOT_PASSWORD: rootpassword
  pastefy:
    image: interaapps/pastefy:latest
    ports:
      - "8080:80"
    depends_on:
      - db
    environment:
      HTTP_SERVER_PORT: 80
      DATABASE_DRIVER: mysql
      DATABASE_NAME: pastefy
      DATABASE_USER: pastefy
      DATABASE_PASSWORD: yourpassword
      DATABASE_HOST: db
      DATABASE_PORT: 3306
      SERVER_NAME: http://yourdomain.com


Ee file save chesi run cheyyandi:

docker-compose up -d


Tarvata browser lo open cheyyandi:

http://localhost:8080


#google url link:https://drive.google.com/file/d/199L5HFnSgljLwbHj8BoySxNGHtI8UQnt/view?usp=drivesdk

linked in post link:https://www.linkedin.com/posts/ashish-dohare-905758367_opensource-kluniversity-foss-activity-7382299769999654912-SeOA?utm_source=share&utm_medium=member_android&rcm=ACoAAFsO1BUB4Jl1BCoPOckIB_sDTaAwGczfNqI

teammates names:Guna shekar-2400031742
                ashish dohare-2400032517