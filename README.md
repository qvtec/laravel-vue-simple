# docker-laravel

Laravel+Vue シンプルアプリケーション

## Start

DockerでLaravel+VueのシンプルなWebアプリを実行する

### 設定ファイル
```
$ cp .env.example .env
```

### build & up
```
$ docker-compose up -d
```

### コンテナ接続
```
$ docker-compose exec web bash
```

## Laravelプロジェクト

https://github.com/cretueusebiu/laravel-vue-spa

### Installation

```bash
$ cp .env.example .env
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
$ npm run hot
```

* WEB
http://192.168.99.100/

* phpMyAdmin
http://192.168.99.100:8080/

#### Production
```bash
$ npm run production
```
