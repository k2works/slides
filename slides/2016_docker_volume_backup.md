class: center middle
# Dockerボリュームを使ったDBのバックアップ

---
class: center middle
# カキギカツユキ
# [Twitter](https://twitter.com/k2works)

---
# 構成

1. 解決したい課題
1. Dockerでの解決/パターンの説明
1. 実装
1. 利点
1. 注意点
1. 参考

---
layout: true
.center[ Dockerボリュームを使ったDBのバックアップ ]

---
# 解決したい課題
## Developer
### Build
+ 開発・本番環境の不一致

### Run
+ データの条件により再現しない不具合
+ データの条件により再現するのに時間のかかる不具合

---
# 解決したい課題
## Operator
### Ship
+ 本番環境からステージング環境へのデータマイグレーション
+ インフラ障害発生時のデータ復旧

---
# Dockerでの解決/パターンの説明
## DockerEngine
### Data Volumes
>A data volume is a specially-designated directory within one or more containers that bypasses the Union File System. Data volumes provide several useful features for persistent or shared data:

> data volumeはUnion File Systemでパイパスされた一つまたは複数のコンテナ内で特別に指定されたディレクトリです。

---
# Dockerでの解決/パターンの説明
## DockerEngine
### データボリュームのメリット
+ データボリュームはコンテナ間で共有・再利用できる
+ 直接データボリュームの変更ができる
+ イメージを更新してもデータボリュームに影響を与えません
+ たとえコンテナが削除されてもデータボリュームはデータを保持し続けます


---
# Dockerでの解決/パターンの説明
1. コマンドラインによるコンテナ内部のデータ管理
1. DockerComposeによるコンテナ内部のデータ管理

---
# 実装
### コマンドラインによるコンテナ内部のデータ管理
```
$ docker create -v /dbdata --name pg_dbstore postgres /bin/true
・・・
```
[続き](https://github.com/k2works/docker-volume-backup/tree/master#dockercli)

---
# 実装
### DockerComposeによるコンテナ内部のデータ管理
```
$ docker volume create --name=my_dbstore
・・・
```
[続き](https://github.com/k2works/docker-volume-backup/tree/master#dockercompose)

---
# 利点
### コマンドラインによるコンテナ内部のデータ管理
+ Dockerがインストールされていればどこでもオッケー
+ コマンドラインなので自動化しやすい

---
# 利点
### DockerComposeによるコンテナ内部のデータ管理
+ コマンドラインに比べて楽
+ `docker-compose.yml`にまとめられているので管理が楽

---
# 注意点
### コマンドラインによるコンテナ内部のデータ管理
+ コマンドラインなのでとっつきにくい
+ 入力しんどい
+ Docker Composeでサポートしている'create volume'に関する解説が公式にまだ無い

---
# 注意点
### DockerComposeによるコンテナ内部のデータ管理
+ 環境によってはインストールされていない
+ 設定ファイルにVersion1と2があってネットの情報がいろいろ混在している
+ どっちにしても画面が黒い

---
# 注意点
### その他
+ コンテナをクラスタリングした場合はデータボリュームを別途管理する工夫が必要([FLOCKとか](https://clusterhq.com/flocker/introduction/))
+ とにかく画面が黒い

---
# 参考
+ [Dockerって何よ](http://k2works.github.io/slides/?what_is_docker.md#1)
+ [Docker Volumeを使ったバックアップハンズオン](https://github.com/k2works/docker-volume-backup/tree/5518371b48b04d58449e147154bd66d912569242)

