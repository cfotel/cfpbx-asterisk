## RUN

### Docker Run:
Start MySQL:  
`docker run --rm -ti -p 3306:3306 -v ${PWD}/data/db:/var/lib/mysql -e MYSQL_DATABASE=asterisk -e MYSQL_USER=asterisk -e MYSQL_ROOT_PASSWORD=CHANG3M3 -e MYSQL_PASSWORD=CHANG3M3 --name cfpbx-db mariadb:10.6`

Start cfpbx:  
`docker run --rm -ti --network=host --privileged --cap-add=NET_ADMIN -v ${PWD}/data:/data -e MYSQL_SERVER=127.0.0.1 -e MYSQL_DATABASE=asterisk -e MYSQL_USER=asterisk -e MYSQL_ROOT_PASSWORD=CHANG3M3 -e MYSQL_PASSWORD=CHANG3M3 -e APP_DATA=/data --name cfpbx cfpbx-asterisk:dev-20.16.0`

### docker compose:

Asterisk 20 + FreePBX 16:
`docker compose down ; docker compose up -d`