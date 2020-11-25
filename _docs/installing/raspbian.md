---
title: Raspbian
category: Installing the bot
order: 4
---

<img class="doc-img" src="{{ site.baseurl }}/images/raspbian.png" alt="Raspbian" style="width: 75px; float: right;"/>

RaspbianへのMusicBotのインストールは、完了するまでに時間がかかる場合があります。  
試してみたい場合は、次のコマンドを実行してインストールできます。

```bash
# システムパッケージを更新する
sudo apt-get update -y
sudo apt-get upgrade -y

# 依存関係をインストールする
sudo apt install python3-pip
sudo apt install git
sudo apt install libopus-dev
sudo apt install ffmpeg

# MusicBotのクローンを作成する
cd ~
git clone https://github.com/Just-Some-Bots/MusicBot.git MusicBot -b master
cd MusicBot
sudo python3 -m pip install --upgrade -r requirements.txt
```

この後、ホームディレクトリ内に `MusicBot`というフォルダがあります。 [構成]({{site.baseurl}}/using/configuration)してから、 `./run.sh`を実行してボットを起動します。
