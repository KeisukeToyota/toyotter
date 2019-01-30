# toyotter2
![](https://img.shields.io/github/stars/KeisukeToyota/toyotter2.svg)
![](https://img.shields.io/github/issues/KeisukeToyota/toyotter2.svg)
![](https://img.shields.io/github/forks/KeisukeToyota/toyotter2.svg)
![](https://img.shields.io/github/license/KeisukeToyota/toyotter2.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/KeisukeToyota/toyotter2)](https://goreportcard.com/report/github.com/KeisukeToyota/toyotter2)

Golang製のCUIベースTwitterクライアント

## インストール

```shell
$ go get github.com/KeisukeToyota/toyotter2
$ cp $GOPATH/src/github.com/KeisukeToyota/toyotter2/.env.example ~/.env.toyotter
```
macOSはHomebrewでもインストールできます
```shell
$ brew tap keisuketoyota/homebrew-toyotter2
$ brew install toyotter2
```

`~/.env.toyotter` にTwitterのキーを設定してください
```
CONSUMER_KEY=xxxxxxxxxxxxxxxxxxxxxxx
CONSUMER_SECRET=xxxxxxxxxxxxxxxxxxxxxxx
ACCESS_TOKEN=xxxxxxxxxxxxxxxxxxxxxxx
ACCESS_TOKEN_SECRET=xxxxxxxxxxxxxxxxxxxxxxx
```

## 使い方

### ツイート
```shell
$ toyotter2 tweet "Hello world" #=> Hello worldをツイート
$ toyotter2 tw "Bye" #=> World!!をツイート
$ toyotter2 tweet "Hello world" --image image.jpg #=> 画像ツイート
$ toyotter2 tw "Hello" -img=image.jpg #=> 画像ツイート
$ toyotter2 tweet delete 34820348023 #=> 34820348023のツイート削除
$ toyotter2 tw d 34820348023 #=> 34820348023のツイート削除
$ toyotter2 tweet "Hi" --reply 34820348023 #=> Hiを34820348023のツイートにリプライ
$ toyotter2 tw "Bye" --reply 34820348023 #=> Byeを34820348023のツイートにリプライ
```

### タイムライン
```shell
$ toyotter2 timeline #=> タイムライン取得(デフォルトで5件)
$ toyotter2 timeline --count 30 #=> タイムライン取得を30件取得
$ toyotter2 tl -c=20 #=> タイムライン取得を20件取得
```

### 検索
```shell
$ toyotter2 search --user twitter #=> twitterを含むユーザーを取得(デフォルトで5件)
$ toyotter2 s --tweet twitter #=> twitterを含むツイートを取得(デフォルトで5件)
$ toyotter2 s -u twitter --count 20 #=> twitterを含むユーザーを20件取得
$ toyotter2 search -tw=twitter -c=30 #=> twitterを含むツイートを30件取得
```

### リツイート
```shell
$ toyotter2 retweet 34820348023 #=> idが34820348023のツイートをリツイート
$ toyotter2 rt 34820348023 #=>idが34820348023のツイートをリツイート
$ toyotter2 retweet 34820348023 --delete #=> idが34820348023のツイートのリツイート解除
$ toyotter2 rt 34820348023 -d #=> idが34820348023のツイートのリツイート解除
```

### いいね
```shell
$ toyotter2 favorite 34820348023 #=> idが34820348023のツイートをいいね
$ toyotter2 fav 34820348023 #=> idが34820348023のツイートをいいね
$ toyotter2 favorite 34820348023 --delete #=> idが34820348023のツイートをいいね解除
$ toyotter2 fav 34820348023 -d #=> idが34820348023のツイートをいいね解除
```

### フォロー
```shell
$ toyotter2 follow TwitterJP #=> @TwitterJPをフォロー
$ toyotter2 flw TwitterJP #=> @TwitterJPをフォロー
$ toyotter2 follow TwitterJP --delete #=> @TwitterJPをフォロー解除
$ toyotter2 flw TwitterJP -d #=> @TwitterJPをフォロー解除
```

### ブロック
```shell
$ toyotter2 block TwitterJP #=> @TwitterJPをブロック
$ toyotter2 blk TwitterJP #=> @TwitterJPをブロック
$ toyotter2 block TwitterJP --delete #=> @TwitterJPをブロック解除
$ toyotter2 blk TwitterJP -d #=> @TwitterJPをブロック解除
$ toyotter2 block --list #=> ブロックユーザー一覧
```

### メンション一覧
```shell
$ toyotter2 mention #=> メンション一覧取得(デフォルトで5件)
$ toyotter2 men #=> メンション一覧取得(デフォルトで5件)
$ toyotter2 mention --count 20 #=> メンション一覧20件取得
$ toyotter2 men -c 20 #=> メンション一覧20件取得
```

### ミュート
```shell
$ toyotter2 mute TwitterJP #=> @TwitterJPをミュート
$ toyotter2 mu TwitterJP #=> @TwitterJPをミュート
$ toyotter2 mute TwitterJP --delete #=> @TwitterJPをミュート解除
$ toyotter2 mu TwitterJP -d #=> @TwitterJPをミュート解除
```

### ヘルプ
```shell
$ toyotter2 --help #=> 全体のヘルプ
$ toyotter2 -h #=> 全体のヘルプ
$ toyotter2 timeline --help #=> timelineコマンドのヘルプ
$ toyotter2 rt -h #=> retweetコマンドのヘルプ
```
