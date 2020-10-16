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
HOSTNAME：pgsql
DBNAME：postgres
USERNAME：postgres
PASSWORD：postgres
PORT:5432
```

## Xdebug + VSCode configuration
サンプル
```json
// launch.json
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Listen for XDebug",
      "type": "php",
      "request": "launch",
      "port": 9012,
      "pathMappings": {
        "/var/www/html": "${workspaceFolder}/php"
      },
      "xdebugSettings": {
        "max_children": 128,
        "max_data": 2048,
        "max_depth": 10
      }
    }
  ]
}
```