class: center middle
# 俺のプログラミングが下手なのはどう考えても練習をしていないのが悪い

---
class: center middle
# カキギカツユキ
# [Twitter](https://twitter.com/k2works)

---
# 構成
1. 課題
1. 解決策
1. 実践
1. 気づき
1. 最後に
1. 参考

---
class: middle center
# 課題

---
class: middle
## プログラミングが下手すぎてヤヴァイWw

---
class: middle
```ruby
def score_for_frame(the_frame)
  score = 0
  ball = 0
  the_frame.times do
    first_throw = @its_throws[ball]
    if first_throw == 10
      # 最終フレームでスペア
      if ball != 20
        score += 10 + @its_throws[ball+1] + @its_throws[ball+2]
        ball += 1
      end
      # パーフェクトの場合は最後に30点加算する
      if ball == 10
        score += 30
      end
    else
      second_throw = @its_throws[ball+1]
      frame_score = first_throw + second_throw
      # スペアの得点計算には次のフレームの第１投が必要
      if frame_score == 10
        score += frame_score + @its_throws[ball+2]
      else
        score += frame_score
      end
      ball += 2
    end
  end
  score
end
```
---
class: middle center
# 解決策

---
## 練習
+ [Clean Coder プロフェッショナルプログラマへの道](https://www.amazon.co.jp/Clean-Coder-%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9E%E3%81%B8%E3%81%AE%E9%81%93-Robert-Martin/dp/4048860690/ref=pd_sim_14_5?_encoding=UTF8&psc=1&refRID=P1B2W496T7HX85THK6C3)

---
## 型
+ [ボウリングゲーム](http://butunclebob.com/ArticleS.UncleBob.TheBowlingGameKata)
+ [素因数分解](http://butunclebob.com/ArticleS.UncleBob.ThePrimeFactorsKata)
+ [ワードラップ](http://thecleancoder.blogspot.jp/2010/10/craftsman-62-dark-path.html)

---
## ボウリングゲーム
+ [アジャイルソフトウェア開発の奥義第2版オブジェクト指向開発の神髄と匠の技](https://www.amazon.co.jp/%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%96%8B%E7%99%BA%E3%81%AE%E5%A5%A5%E7%BE%A9-%E7%AC%AC2%E7%89%88-%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E9%96%8B%E7%99%BA%E3%81%AE%E7%A5%9E%E9%AB%84%E3%81%A8%E5%8C%A0%E3%81%AE%E6%8A%80-%E3%83%AD%E3%83%90%E3%83%BC%E3%83%88%E3%83%BBC%E3%83%BB%E3%83%9E%E3%83%BC%E3%83%81%E3%83%B3/dp/4797347783)

---
class: middle center
# 実践

---
## やったこと
+ 写経する
+ 手を動かす
+ 頭を使う
+ 思考をトレースする
+ 繰り返す

---
## 写経する
1. 目的を明確にして構成を決める
1. アプリケーション環境
1. アプリケーション開発
1. アプリケーション配置

---
## 手を動かす
+ [Javaオリジナル版](https://github.com/k2works/etude-op10-no5)

---
## 頭を使う
+ [Ruby移植版](https://github.com/k2works/etude_op10_no6)

---
## 思考をトレースする
+ Step1 - Step7 オブジェクトの振る舞いを考える
+ Step8 - Step52 Frameのリンクリストの必要性を検証する
+ Step8 - Step42 Gameの実装
+ Step43 - Step52 Gameのリファクタリング
+ Step53 Scoreの実装
+ Step54 - Step62 Scoreのリファクタリング

---
## 思考をトレースする
### Step1 - Step52
![Step1 - Step52](./image/coding_for_practice/class_diagram01.png)

---
## 思考をトレースする
### Step53 - Step62
![Step53 - Step62](./image/coding_for_practice/class_diagram02.png)

---
## 繰り返す
+ 毎日始業1時間を使う
+ 最終的には1日10分ぐらいにする

---
class: middle center
# 気づき

---
class: middle
```Ruby
def score_for_frame(the_frame)
  score = 0
  ball = 0
  the_frame.times do
    first_throw = @its_throws[ball]
    if first_throw == 10
      # 最終フレームでスペア
      if ball != 20
        score += 10 + @its_throws[ball+1] + @its_throws[ball+2]
        ball += 1
      end
      # パーフェクトの場合は最後に30点加算する
      if ball == 10
        score += 30
      end
    else
      second_throw = @its_throws[ball+1]
      frame_score = first_throw + second_throw
      # スペアの得点計算には次のフレームの第１投が必要
      if frame_score == 10
        score += frame_score + @its_throws[ball+2]
      else
        score += frame_score
      end
      ball += 2
    end
  end
  score
end
```
---
class: middle
```Ruby
def score_for_frame(the_frame)
  score = 0
  @ball = 0
  current_frame = 0
  while current_frame < the_frame
    if strike
      score += 10 + next_tow_balls_for_strike
      @ball += 1
    elsif spare
      score += 10 + next_ball_for_spare
      @ball+=2
    else
      score += two_balls_in_frame
      @ball+=2
    end
    current_frame += 1
  end
  score
end
```
---
### 気づき
+ プログラミング制御構造がわかっていない
+ 制御用変数の扱いがわかっていない
+ 対象ドメインを理解していない

---
class: middle
> 最良の設計というものは、テストを最初に用意し、小さなステップを繰り返すことで展開されていくものなのだ

[Robert Cecil Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)
---
class: middle center
# 最後に

---
## プログラミングを上達させるには
1. 上手い人を見つけて真似する(周りにいなければ書籍からでも)
1. 上手い人の思考プロセスをモデル化する
1. モデル化したプロセスを自分のプロセスに組み込む
1. あとは練習
1. うまくいかない場合はモデルを検証して改善

---
class: middle center
## 継続的インテグレーション

---
# 参考
+ [Robert Cecil Martin](https://en.wikipedia.org/wiki/Robert_Cecil_Martin)
+ [アジャイルソフトウェア開発の奥義第2版オブジェクト指向開発の神髄と匠の技](https://www.amazon.co.jp/%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%96%8B%E7%99%BA%E3%81%AE%E5%A5%A5%E7%BE%A9-%E7%AC%AC2%E7%89%88-%E3%82%AA%E3%83%96%E3%82%B8%E3%82%A7%E3%82%AF%E3%83%88%E6%8C%87%E5%90%91%E9%96%8B%E7%99%BA%E3%81%AE%E7%A5%9E%E9%AB%84%E3%81%A8%E5%8C%A0%E3%81%AE%E6%8A%80-%E3%83%AD%E3%83%90%E3%83%BC%E3%83%88%E3%83%BBC%E3%83%BB%E3%83%9E%E3%83%BC%E3%83%81%E3%83%B3/dp/4797347783)
+ [Clean Code アジャイルソフトウェア達人の技](https://www.amazon.co.jp/Clean-Code-%E3%82%A2%E3%82%B8%E3%83%A3%E3%82%A4%E3%83%AB%E3%82%BD%E3%83%95%E3%83%88%E3%82%A6%E3%82%A7%E3%82%A2%E9%81%94%E4%BA%BA%E3%81%AE%E6%8A%80-Robert-Martin/dp/4048676881/ref=pd_sbs_14_t_1?_encoding=UTF8&psc=1&refRID=3YY9KEWRQNCY9YX3DY4W)
+ [Clean Coder プロフェッショナルプログラマへの道](https://www.amazon.co.jp/Clean-Coder-%E3%83%97%E3%83%AD%E3%83%95%E3%82%A7%E3%83%83%E3%82%B7%E3%83%A7%E3%83%8A%E3%83%AB%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9E%E3%81%B8%E3%81%AE%E9%81%93-Robert-Martin/dp/4048860690/ref=pd_sim_14_5?_encoding=UTF8&psc=1&refRID=P1B2W496T7HX85THK6C3)
