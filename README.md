# WordPress Bedrock Docker Boilerplate

This project is faster version of this [Bedrock setup](https://github.com/trenccan777/WP-Bedrock-Docker-setup/).

Simple and fast Wordpress Bedrock setup on docker

## Supported technologies
- WordPress
- MySQL
- PhpMyAdmin
- WP-CLI - command line interface for WordPress

## Installation

- clone this repository into your PC
- `cd` into the root folder and edit `.env.bedrock` and `.env` or leave it as it is 
- download bedrock with composer:

```
composer create-project roots/bedrock
```

- copy `env.bedrock` and `.htaccess` file from root folder to bedrock folder and rename `env.bedrock` to `.env`. 

- from the root folder run:
```
docker-compose up -d
```
- WordPress is ready for installation on the `http://registered-ip-in-env-file/web`

## WP-CLI

To use wp-cli, you can easily set alias in `.bashrc` file in your user folder. 

```
alias wp="docker-compose run --rm wpcli"
```

Then you can run standard commands. For instance for database manipulation you can run:

Import database:
``` 
wp db import databasename.sql
```

Database dump:

```
wp db export
```

Database drop:

```
wp db drop
```

Search and replace:

```
wp search-replace 'old-url' 'new-url'
```

## MySQL

If you want, you can use standard MySQL commands. 

Database dump:

```
docker exec CONTAINER-NAME sh -c 'exec mysqldump DBNAME -uroot -p"$MYSQL_ROOT_PASSWORD"' > backup.sql
```

Database import:

```
docker exec -i CONTAINER-NAME sh -c 'exec mysql -uroot DBNAME -p"$MYSQL_ROOT_PASSWORD"' < backup.sql
```