# php-nginx-docker

php development environment using docker

## 概要

- nginx: 1.15.7
- php: 7.3.6
- xdebug
- composer
- postgres:11-alpine

## 起動・停止
起動
```
$ docker-compose build --no-cache # Dockerfileを更新した場合
$ docker-compose up -d
```

停止
```
$ docker-compose down
```

```
docker-compose exec php /bin/ash
docker-compose exec pgsql /bin/ash
```

## URL
index.php  
http://localhost:8080

pgadmin  
http://localhost:5050


## pgadminへの接続
デフォルトのログインアカウントは以下の通り
```
USER：pgadmin
PASS：pgadmin
```

データベースの追加は以下の通り
```
サーバー名：自由に決めて
HOSTNAME：pgsql
DBNAME：postgres
USERNAME：postgres
PASSWORD：postgres
PORT:5432
```