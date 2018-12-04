# Docker PHP Boilerplate

This Docker Boilerplate includes PHP 7 with necessary libraries to run most of PHP Web App, Nginx, MariaDB / MySQL, Redis, Composer, Adminer for Simple DB Management.

## Pre-requisite: 
 - Docker running on your machine

### How to use
> Clone this repo on your machine

#### To Configure
```sh
$ cd docker-php-boilerplate
$ vi docker-compose.yml
```
  - Change all necessary names org-*-project-name
  - Change the database users and password
       - "MYSQL_USER=orguser"
       - "MYSQL_PASSWORD=xxxxxxxxxxxxxxxxxxx"
       - "MYSQL_ROOT_PASSWORD=xxxxxxxxxxxxxxxxxxx"

   - Update all the mapped volume location to point to your setup
     > e.g.  ./src/public/app - source file document root
 
   - See below for the mappings

### Folder and Files
| Folder/File | Detail |
| ------ | ------ |
| ./src/public/app | Document Root |
| ./config/php/php.ini | PHP INI Config |
| ./config/nginx/default.conf | Nginx config file |
| ./db-data | MySQL Database data |
| ./redis-data | Redis data |
| ./logs/nginx/ | Nginx Logfiles |
| ./config/certs | SSL Certificates |

#### To Start
```sh
$ cd docker-php-boilerplate
$ docker-compose up -d
```

#### To Stop
```sh
$ docker-compose down
```

#### Access Your Web App
Go to your browser http://127.0.0.1/

#### Access DB Viewer adminer
Go to your browser http://127.0.0.1:8080/

> DB Host: mariadb

> DB User: set on the yml file

> DB Pass: set on the yml file

Some of the essential Docker commands:


#### Stop and remove all containers
```sh
$ docker stop $(docker ps -a -q)
$ docker rm $(docker ps -a -q)
```
#### Remove all images
```sh
$ docker rmi $(docker images -a -q)
```

#### Check and list images
```sh
$ docker images
```

#### Remove individual image
```sh
$ docker rmi <imageId>
```

#### Stop all containers
```sh
$ docker-compose stop
```

#### Start and build changes
```sh
$ docker-compose up
```

#### Shut down whole application
```sh
$ docker-compose down
```
