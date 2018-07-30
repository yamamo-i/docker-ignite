# docker-ignite

docker-composeでIgniteのall in one環境を作成する
* Apache Ingnite: 2.6.0
* Apache Zeppelin: 0.8.0

# 構築方法

## igniteのImageを生成する

* Apache IgniteはDockerHubの公式Imageをpullする
```bash
$ docker pull apacheignite/ignite
```

## zeppelinのImageを生成する

* IgniteのGUI IFを提供するApache zeppelinのdocker imageを生成する  
```bash
$ docker pull apache/zeppelin:0.8.0
```

## docker-composeでコンテナをあげる

* `.env` ファイルのバージョンをDockerImageに合わせる
```bash
$ vim .env
$ cat .env
IGNITE_VERSION=2.6.0 # IgniteのImageバージョン
ZEPPELING_IMAGE_PATH=zeppelin-local:latest # 生成したdocker Image名
```
* docker-composeであげる
```bash
$ docker-compose up -d
```

# アクセス方法

* ブラウザ
* ODBC
* JDBP
