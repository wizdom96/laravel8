
## Laravel Docker starting app

## How to use

Step 1:

Install docker and docker-compose to your pc.

Step 2:

Clone code repository then install dependencies in src folder:
```
git clone
npm install  -  optional if you use vue
composer update
```

Edit env.example into .env and enter your database

Create db on port 8080/  login with user/secret

Build docker images
```
docker-compose build
docker-compose up -d
```

```bash
chmod -R 777 storage
```

Running php artisan:

```bash
docker-compose exec php php artisan migrate
docker-compose exec php php artisan key:generate
```

## Access the app and services
Application Homepage
```bash
http://localhost:8989
```

Adminer
```bash
http://localhost:8990
```

Username: root
Password: secret

You can edit these info in the **docker-compose.yml**

## FAQ
1. File permission problem:
Ref: [If you are running Docker on Linux, the files created are owned by root.](https://docs.docker.com/compose/django/)

```bash
sudo chown -R $USER:$USER .
```

