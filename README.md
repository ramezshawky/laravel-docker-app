# Laravel Application

in this project:
1. create a Laravel application
2. Dockerize the application
3. using a docker-compose.yaml


### Laravel application running on three separate service containers:
1. An app service running PHP7.4-FPM
2. A db service running mysql:8.0
3. An nginx:1.17-alpine service 

## How to install and run this Laravel app 

1. git clone git@github.com:ramezshawky/laravel-docker-app.git
2. docker compose build -t travellist-app .
3. docker compose up -d
4. docker-compose exec app php artisan key:generate
5. localhost:8000
