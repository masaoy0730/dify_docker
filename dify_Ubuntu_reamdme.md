UbuntuにDokcerをインストールし、Difyを利用できるようにします。
Azureの仮想サーバーを使います。
OSはMacです。

Azureのサーバーが作られたら、
- chmod を使用して、秘密キーに読み取り専用アクセスを割り当て、セキュリティを強化。
- Macのターミナルから、SSH経由でVMに接続。

Dockerのインストール　https://docs.docker.com/engine/install/ubuntu/#install-using-the-repository

`gnome-terminal`をインストールします。
```sudo apt install gnome-terminal```

Docker Desktopのインストール
`lsb_release -a`でUbuntuのCodenameを調べます。Ubuntu 22.04.5 LTSはjammyでした。

https://download.docker.com/linux/ubuntu/dists/

インストール後、Dockerの起動の確認
sudo systemctl status docker
（systemctl status は、出力が長いと自動的に ページャ (less) を使って結果を表示します。qを入力すれば抜けられます。）

Hello Worldのイメージの動作確認
sudo docker run hello-world

