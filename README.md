# dify_docker
こちらはDifyをPCのDockerで動かすためのメモです。<br>
DifyのSaaS版の無料のSandboxを使っていたのですが、v1.0にメジャーバージョンアップしてからAPI登録のやり方がわからなくなってしまい、まだAPI利用のエラーを解消できていない状態です。<br>
そこで、PCにDocker Composeでv0.15.3をデプロイする方が速かったので、こちらに手順をメモしました。<br>
Difyについては[こちら](https://github.com/langgenius/dify/blob/main/README_JA.md)をご覧ください。<br>

## [Difyのサイト「Docker Composeでデプロイする」を参照しています](https://docs.dify.ai/ja-jp/getting-started/install-self-hosted/docker-compose)
### Difyをクローンする
PC(Windows or Mac）にDocker DesktopとDocker Composeがインストールされている前提です。<br>
以下、ターミナルを利用します。<br>
Difyのソースコードをローカル環境にクローンします。<br>
3/20にv1.1.1がリリースされました。v1では不具合の報告がされているので、現状では0.15.3がおすすめです。<br>
```
git clone https://github.com/langgenius/dify.git --branch 0.15.3
```
### Difyをスタートする
```
cd dify/docker
```
```
cp .env.example .env
```
```
docker compose up -d
```
全てのコンテナが稼働していることを確認する。
```
docker compose ps
```
### Difyをアップデートする
```
cd dify/docker
docker compose down
git pull origin main
docker compose pull
docker compose up -d
```
### Difyにアクセス
Dockerでコンテナが起動したら、下記のURLでDifyを使えます。<br>
[http://localhost/install](http://localhost/install)

### 実行中のコンテナを停止する
```
docker compose stop
```
### 再起動
#### 停止後、再度起動したい場合は以下を使用します：
```
docker compose start
```
#### 停止しているか確認する
```
docker compose ps
```

