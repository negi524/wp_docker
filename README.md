# Docker を利用した WordPress 環境

### WordPress

- コンテナ名:wp_docker
- version:最新

### MySQL

- コンテナ名:db_docker
- version:5.7

## ignore

- .env：環境設定ファイル
- ./db-data/mysql.dump.sql：mysql のデータ永続化のための dump ファイル

## コンテナの操作

### コンテナの起動

```bash
$ docker-compose up -d
```

|  オプション  |          説明          |
| :----------: | :--------------------: |
| --detach, -d | バックグラウンドで実行 |

### コンテナの起動確認

```bash
$ docker-compose ps
または
$ docker container ls
```

### コンテナの停止

```bash
$ docker-compose stop
```

### リソースの削除

```bash
$ docker-compose down
```

### コンテナに bash を使って入る

```bash
$ docker container exec -it wordpress_docker /bin/bash
```

|    オプション     |           説明            |
| :---------------: | :-----------------------: |
| --interactive, -i | コンテナの標準入力を開く  |
|     --tty, -t     | tty（端末デバイス）を使う |

### コンテナ内で動くプロセス（bash）のみを終了する

Ctr + p
Ctr + q

## ブラウザで確認する

`localhost:9000`にアクセスすると、WordPress の画面が表示される

## データの永続化について

データ永続化のため、mysql のデータをローカル環境に dump する
コンテナ起動後、以下のコマンドを実行すれば`docker-compose down`コマンドでリソースを削除してもデータが消えず、初期設定の手間が省ける

```
$ docker exec -it dbコンテナ名 sh -c 'mysqldump データベース名 -u データベースユーザ名 -pデータベースパスワード 2> /dev/null' > db-data/mysql.dump.sql
```

|      コマンドの値      | .env ファイルの値 |
| :--------------------: | :---------------: |
|     データベース名     |  MYSQL_DATABASE   |
|  データベースユーザ名  |    MYSQL_USER     |
| データベースパスワード |  MYSQL_PASSWORD   |
