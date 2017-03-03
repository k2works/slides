class: center middle
# 通常攻撃が全体攻撃で二回攻撃のプログラミング環境はお好きですか？

---
class: center middle
# カキギカツユキ
# [Twitter](https://twitter.com/k2works)

---
# 構成
1. 課題
1. 解決策
1. 通常攻撃が全体攻撃
1. 二回攻撃
1. 実践
1. 気づき
1. 最後に
1. 参考

---
class: middle center
# 課題

---
class: middle
## モダンなプログラミング環境の闇・・・

---
class: middle
## 主にフロントエンド界隈・・・

---
## すごーいフロントエンド界隈のトレンド
+ CSSコーディング
+ JavaScriptプログラミング
+ タスクランナー・ビルドツール
+ その他いろいろ

---
class: middle
## jQueryの勉強を始めたらなんかjQueryが終わりつつあるとか・・・
[You Don't Need jQuery](http://qiita.com/tatesuke/items/b9548dd484b01b139b74)

---
class: middle
## タスクランナーはGruntからGulpなのねと思ってたら・・・
[Why I Left Gulp and Grunt for npm Scripts](http://qiita.com/chuck0523/items/dafdbd19c12efd40e2de)

---
class: middle
## たのしー・・・・

---
class: middle
## くない

---
class: middle
![](http://3.bp.blogspot.com/-3IkExR-iCAo/VcMlN3R7V0I/AAAAAAAAwXg/10JXiaXCeDs/s800/figure_zasetsu.png)


---
class: middle center
# 解決策

---
class: middle
## プログラミング環境の継続的インテグレーション

---
class: middle
>Build Requires More Than One Step
>
>You should be able to check out the system with one simple command and then issue one other simple command to build it.

>Tests Require More Than One Step
>
>Being able to run all the tests is so fundamental and so important that it should be quick, easy, and obvious to do.

[Robert Cecil Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)
---
## Build Requires More Than One Step

```bash
git clone https://github.com/k2works/etude_op10_no9.git etude-op10-no9
cd /etude-op10-no9
vagrant up
vagrant ssh
yarn install
npm run build
npm run deploy
```

---
## Tests Require More Than One Step

```bash
$ npm run test

> etude-op10-no9@1.0.5 test /Users/k2works/Projects/k2works/etude_op10_no9
> mocha

  Game
    .score
      when two throws
        ✓ is scored
      when spare
        ✓ is scored
        .
        .
        .
        .
    .scoreForFrame
      when four throws
        ✓ is scored by frame
      when spare
        ✓ is scored by frame
        ✓ is scored by frame
      when strike
        ✓ is scored by frame


  13 passing (18ms)
```
---
## 通常攻撃が全体攻撃で二回攻撃のプログラミング環境
+ 再利用可能な環境
+ プラットフォームに依存しない環境

---
## 通常攻撃が全体攻撃
+ 開発
  + テストコーディング
  + プロダクトコーディング

---
class: middle
> 最良の設計というものは、テストを最初に用意し、小さなステップを繰り返すことで展開されていくものなのだ

[Robert Cecil Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)

---
## 二回攻撃
+ ビルド
+ デプロイ

---
class: middle
![](./image/coding_for_environment/build_deploy.png)

---
class: middle center
# 実践

---
class: middle center
# 気づき

---
class: middle center
# 最後に

---
class: middle center
## 通常攻撃が全体攻撃で二回攻撃のプログラミング環境はお好きですか？

---

# 参考
+ [Robert Cecil Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)
+ [アジャイルソフトウェア開発の奥義第2版オブジェクト指向開発の神髄と匠の技](https://www.amazon.co.jp/%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%96%8B%E7%99%BA%E3%81%AE%E5%A5%A5%E7%BE%A9-%E7%AC%AC2%E7%89%88-%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E9%96%8B%E7%99%BA%E3%81%AE%E7%A5%9E%E9%AB%84%E3%81%A8%E5%8C%A0%E3%81%AE%E6%8A%80-%E3%83%AD%E3%83%90%E3%83%BC%E3%83%88%E3%83%BBC%E3%83%BB%E3%83%9E%E3%83%BC%E3%83%81%E3%83%B3/dp/4797347783)
+ [Clean Code アジャイルソフトウェア達人の技](https://www.amazon.co.jp/Clean-Code-%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%81%94%E4%BA%BA%E3%81%AE%E6%8A%80-Robert-Martin/dp/4048676881/ref=pd_sbs_14_t_1?_encoding=UTF8&psc=1&refRID=3YY9KEWRQNCY9YX3DY4W)
+ [Clean Coder プロフェッショナルプログラマへの道](https://www.amazon.co.jp/Clean-Coder-%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9E%E3%81%B8%E3%81%AE%E9%81%93-Robert-Martin/dp/4048860690/ref=pd_sim_14_5?_encoding=UTF8&psc=1&refRID=P1B2W496T7HX85THK6C3)
+ [etude-op10-no9](https://github.com/k2works/etude_op10_no9)
