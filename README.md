# dify_docker
DifyをDockerで動かすためのメモ。<br>
PC(Windows or Mac）にDocker DesktopとDocker Composeがインストールされている前提です。<br>
以下、ターミナルを利用します。
## [Difyのサイト「Docker Composeでデプロイする」を参照しています](https://docs.dify.ai/getting-started/install-self-hosted/docker-compose)
### Difyをクローンする
Difyのソースコードをローカル環境にクローンします。<br>
現在v1.0.1が最新バージョンですが、いくつか不具合があるようなので、0.15.3がおすすめです。<br>

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
Local environment<br>
Dockerでコンテナが起動したら、下記のURLでDifyを使えます。
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

