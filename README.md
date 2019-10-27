# docker-laravel

Docker環境のベース

## Start

Dockerでapache,php7.3,mysql5.7の環境をつくる

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

Laravelインストールまでを実行

### Laravelプロジェクト作成
```bash
$ laravel new myapp
```

### Laravelサーバ起動
```bash
$ php artisan serve
```

http://192.168.99.100/

http://192.168.99.100:8080/

### laravelの.env修正
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

### ログイン実装
```bash
$ composer require laravel/ui
$ php artisan ui vue --auth
$ php artisan migrate
```

### 必要なパッケージをインストールして実行
```
$ npm install
$ npm run dev
```