# Docker を利用した WordPress 環境

### WordPress

- コンテナ名:wp_docker
- version:最新

### MySQL

- コンテナ名:db_docker
- version:5.7

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
