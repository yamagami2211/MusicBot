---
title: Debian
category: Installing the bot
order: 5
---

<img class="doc-img" src="{{ site.baseurl }}/images/debian.png" alt="debian" style="width: 75px; float: right;"/>

Debianへのボットのインストールは[Ubuntu](/installing/ubuntu)に似ていますが、 `apt`を介して取得したいくつかの追加のシステム依存関係が必要です。

~~~ bash
# システムリポジトリを更新する
sudo apt-get update -y
sudo apt-get upgrade -y

# 依存関係をインストールする
sudo apt-get install git libopus-dev libffi-dev libsodium-dev ffmpeg -y
sudo apt-get install build-essential libncursesw5-dev libgdbm-dev libc6-dev zlib1g-dev libsqlite3-dev tk-dev libssl-dev openssl -y

# Debian Stretch以下を使用している場合は、Pythonもインストールする必要があります...
sudo apt-get install python3.5 python3-pip -y

# MusicBotをホームディレクトリに複製します
cd ~
git clone https://github.com/Just-Some-Bots/MusicBot.git MusicBot -b master
cd MusicBot

# 依存関係をインストールする
sudo -H python3.5 -m pip install --upgrade pip
sudo -H python3.5 -m pip install --upgrade -r requirements.txt
~~~

この後、ホームディレクトリ内に `MusicBot`というフォルダがあります。 [構成]({{site.baseurl}}/using/configuration)してから、 `./run.sh`を実行してボットを起動します。
