# Ruby on Rails

これは、次の教材で作られたサンプルアプリケーションです。
[*Ruby on Rails チュートリアル*] (https://railstutorial.jp/)
(第6版)
[Michael Hart]（https://www.michaelhart.com/）著

##ライセンス

[Ruby on Rails チュートリアル](https://railstutorial.jp/)内にある
ソースコードはMITライセンスとBeeerwareライセンスの元で公開されています。
詳細は[LISENCE.md](LICENSE.md)をご覧ください。

##使い方

このアプリケーションを動かす場合は、まずリポジトリを手元にクローンしてください。

以降は、私がDockerで環境構築しているため、Rails tutorialのReadmeの内容と異なります。

まず必要なdocker imageをbuildします
```
docker-compose build
```

次にコンテナを作成します。
```
docker-compose up
```

次にデータベースを作成します。
```
docker-compose run web rails db:create
```

次にエラー文としてWebpacker configuration file not found /myapp/config/webpacker.yml. Please run rails webpacker:installと書かれているので
webpackerをインストールします。
```
docker-compose run web rails webpacker:install
```

最後に再度コンテナを立ち上げればlocalhost:3000にrailsの画面が表示されます。
```
docker-compose up
```