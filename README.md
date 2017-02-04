説明用スライド資料
===================

# 目的 #
セミナー・勉強会等で使うスライド資料の管理

# 前提 #

# 構成 #
+ セットアップ
+ スライド

# 詳細 #
## セットアップ ##

ローカルで動かす

    # ブラウザで開く
    open slides/sample.html
    # ブラウザが Google Chrome の場合
    open -a "Google Chrome" --args --allow-file-access-from-files $(pwd)/slides/sample.html

## スライド ##
- [Dockerって何よ](http://k2works.github.io/slides/?what_is_docker.md)
    - Docker概要
- [Dockerボリュームを使ったDBのバックアップ](http://k2works.github.io/slides/?docker_volume_backup.md)
    - Dockerのデータボリューム解説
- [写経のススメ](http://k2works.github.io/slides/?getting_start_programing.md)
    - My写経スタイル
- [プログラミング練習](http://k2works.github.io/slides/?coding_for_practice.md)
    - プログラミング練習方法に関して

# 参照 #
- [remark.js ことはじめ](http://k2works.github.io/slides/?remarkjs.md)
    - remark.js における markdown の書き方を簡単に解説
- [markdown + remark.js + gh-pages でプレゼン資料を公開する](http://qiita.com/harasou/items/1fa3cca6ac1ef175c876)
