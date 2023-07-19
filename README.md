Forkar e clonar o repositório

`git clone --recurse-submodules --remote-submodules git@github.com:rmsaitam/app-laravel-docker.git`

Acessar o diretório app-laravel-docker

`cd app-laravel-docker`

Renomear o arquivo .env.example para .env

`cp .env.example .env`

.env

```
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=app-laravel
DB_USERNAME=root
DB_PASSWORD=secret

MAIL_MAILER=smtp
MAIL_HOST=mailhog
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="no-reply@applaravel.com"
MAIL_FROM_NAME="${APP_NAME}"

```

Acessar o diretório laradock

Renomar o arquivo .env.example para .env

`cp .env.example .env`

.env

```
PHP_VERSION=8.2
MYSQL_VERSION=latest
MYSQL_DATABASE=app-laravel
MYSQL_USER=user
MYSQL_PASSWORD=secret
MYSQL_PORT=3306
MYSQL_ROOT_PASSWORD=secret

```

No diretório laradock, execute:

`docker-compose up -d nginx mysql adminer mailhog workspace`

Aguarde e depois verifique com o comando seguinte

`docker ps`

Estando OK, acesse o container

`docker exec -it <container-id-workspace-laradock> bash`

`composer install`

`php artisan key:generate`

No browser acesse http://localhost irá exibir a página default do Laravel
Para acessar o Adminer http://localhost:8081
Para acessar o MailHog (webmail) http://localhost:8025 

Feito!



