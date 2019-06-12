# Docker を利用した WordPress 環境

### WordPress

- version:最新

### MySQL

- version:5.7

## コンテナの操作

### コンテナの起動

```bash
$ docker-compose up -d
```

`-d`オプション：バックグランドで実行

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
