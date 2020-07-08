# Symfony 4 docker containers

A Proof-of-concept of a running Symfony 4.4 application inside containers

```
cd symfony-4.4-docker

cd docker

docker-compose up
```

## Create symfony project

```
cd "root of project"

symfony new src --version=4.4 --full
```

## Compose

### Database (MariaDB)

...

### PHP (PHP-FPM)

Composer is included

```
docker-compose run php-fpm composer 
```

To run fixtures

```
docker-compose run php-fpm bin/console doctrine:fixtures:load
```

### Webserver (Nginx)

...

### PHPMyAdmin

...