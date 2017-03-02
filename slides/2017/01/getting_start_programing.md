class: center middle
# 写経のススメ

---
class: center middle
# カキギカツユキ
# [Twitter](https://twitter.com/k2works)

---
# 構成
1. 写経とは
1. 原則
1. ツール
1. メソッド
1. 最後に
1. 参考

---
class: middle center
# 写経とは

---
class: middle
## 自分の手でソースコードを打ってみて実行してみること

---
class: middle center
# 原則

---
class: middle center
## デプロイするまでやる

---
class: middle center
## 少しづつやる

---
class: middle center
## 記録しながらやる

---
class: middle center
## いつでもどこでも再現できるようにやる

---
class: middle center
# ツール

---
## 三種の神器
+ テキストエディタ
+ バージョン管理システム
+ 仮想マシン

---
## テキストエディタ
+ 機能性
+ 拡張性
+ ポータビリティ

---
## バージョン管理システム
+ git
+ その他

---
## 仮想マシン
+ Vagrant
+ docker

---
class: middle center
# メソッド

---
## 基本コンセプト
+ 環境
+ 開発

---
### 環境
+ 主要なプラットフォームで動作する統一された開発環境
+ 開発環境のアップデートとバージョン管理

---
### 開発
+ TDD
+ CI
+ リファクタリング

---
## 基本プロセス
1. 目的を明確にして構成を決める
1. アプリケーション環境構築
1. アプリケーション開発
1. アプリケーション配置

---
### 目的を明確にして構成を決める
+ 記録しながらやる
  + テキストエディタ(Markdown表記)

---
### アプリケーション環境構築
+ いつでもどこでも再現できるようにやる
  + Vagrant
  + Docker

---
### アプリケーション開発
+ 少しづつやる
  + テキストエディタ(入力補完)
  + git(セマンティックバージョンニング)

+ 記録しながらやる  
  + テキストエディタ(Markdown表記)
  + git

---
### アプリケーション配置
+ デプロイするまでやる
  + Heroku

+ XPプラクティスの実践
  + TDD
  + CI
  + リファクタリング  

---
class: middle center
# 最後に

---
## 初心者に向けて
+ 上手い人を見つけて真似する
+ 定番部分は書籍の写経から入るのが妥当
+ 最新技術はオフィシャルサイトのチュートリアルから入るのが妥当
+ 先達の型からはいって自分の型を作っていこう

---
# 参考
+ [エクストリーム・プログラミング](https://ja.wikipedia.org/wiki/%E3%82%A8%E3%82%AF%E3%82%B9%E3%83%88%E3%83%AA%E3%83%BC%E3%83%A0%E3%83%BB%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0)
+ [セマンティック バージョニング 2.0.0](http://semver.org/lang/ja/)
+ [Markdown](https://ja.wikipedia.org/wiki/Markdown)
