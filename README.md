# docker-laravel

Laravel+Vue シンプルアプリケーション

## Start

DockerでLaravel+VueのシンプルなWebアプリを実行する

### 設定ファイル
```bash
$ cp .env.example .env
```

### build & up
```bash
$ docker-compose up -d
```

### コンテナ接続
```bash
$ docker-compose exec web bash
```

## Laravelプロジェクト作成

https://github.com/cretueusebiu/laravel-vue-spa

### Laravel設定
```bash
$ cp .env.example .env
```

```
APP_URL=http://192.168.99.100

DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=docker-database
DB_USERNAME=docker
DB_PASSWORD=docker

MAIL_DRIVER=log
```

### 準備

```
$ composer install
$ php artisan key:generate
$ php artisan jwt:secret
$ php artisan migrate
$ npm install
```

### 起動

#### Development
```bash
# build and watch
$ npm run watch
$ npm run watch-poll #Docker(Windows)

# serve with hot reloading
npm run hot
```

#### Production
```bash
$ npm run production
```

#### WEB
http://192.168.99.100/

#### phpMyAdmin
http://192.168.99.100:8080/
