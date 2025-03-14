# dify_docker
DifyをDockerで動かすためのメモ。<br>
PC(Windows or Mac）にDocker DesktopとDocker Composeがインストールされている前提。<br>
以下、ターミナルを利用。
## [Deploy with Docker Compose](https://docs.dify.ai/getting-started/install-self-hosted/docker-compose)
### Clone Dify
Clone the Dify source code to your local machine:
Assuming current latest version is 0.15.3<br>
（現在v1.0.1が最新バージョンですが、0.15.3がおすすめ）
```
git clone https://github.com/langgenius/dify.git --branch 0.15.3
```
### Starting Dify
```
cd dify/docker
```
```
cp .env.example .env
```
```
docker compose up -d
```
Finally, check if all containers are running successfully:
```
docker compose ps
```
### Upgrade Dify
```
cd dify/docker
docker compose down
git pull origin main
docker compose pull
docker compose up -d
```
### Access Dify
Local environment
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

