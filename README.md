# Сборка докера для разработки

Включает

* php 7.4.4
* nginx latest
* mariadb 10.3
* postgres 11.2-alpine
* mailhog
* elasticsearch 7 или 8

## Installation

```bash
$ git clone https://github.com/vladbushuev/docker-dev.git
```

В .env указываем свои параметры: название проекта, версию Elasticsearch, пользователя и группу под которым работает php, свободный диапазон IP (нужно для корректной работы xdebug под PHPStorm)

В docker-compose.yml оставляем необходимые сервисы, остальное удаляем.
В папке config/nginx необходимо выбрать версию yii basic или advanced и переименовать в  site.conf

## Basic Usage

Под linux и macOS можно использовать Makefile, пример:

```bash
$ make up
$ make down
$ make bash
```

Под windows

```bash
docker-compose up --build -d
docker-compose down --remove-orphans
docker-compose exec --user=php php-fpm  bash
```
