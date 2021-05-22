# Laravel 8/Php 7.4/MariaDB/Nginx ssl/Certbot/Docker-compose

## Production
```bash
#Copy .env
cp .env.example .env

#Start Docker 
docker-compose up -d

#Enter in container
docker-compose exec app bash

#Clear cache
php artisan optimize

#Generate app key
php artisan key:generate

#Install Node dependencies
npm install && npm run prod

#Nginx ssl for https Manual from https://gist.github.com/dancheskus/8d26823d0f5633e9dde63d150afb40b2
cd nginx
curl -L https://raw.githubusercontent.com/dancheskus/nginx-docker-ssl/master/init-letsencrypt.sh > init-letsencrypt.sh
chmod +x init-letsencrypt.sh
sudo ./init-letsencrypt.sh
```
