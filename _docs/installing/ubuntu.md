---
title: Ubuntu
category: Installing the bot
order: 1
---

<img class="doc-img" src="{{ site.baseurl }}/images/ubuntu.png" alt="Ubuntu" style="width: 75px; float: right;"/>

コマンドラインからUbuntuにMusicBotをインストールすることは、**ボットをインストールするための推奨される方法**ですが、システムの依存関係は、使用しているUbuntuのバージョンによって異なります。 まず、システムに必要な依存関係をインストールしましょう。

## Ubuntu 20.04

~~~ bash

# Python 3.7をインストールし、外部リポジトリを追加します（Pythonバージョンがインストールされていない場合のみ）
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.7 -y

# ビルドツールをインストールする
sudo apt-get install build-essential unzip -y
sudo apt-get install software-properties-common -y

# システムの依存関係をインストールする
sudo apt-get update -y
sudo apt-get install git ffmpeg libopus-dev libffi-dev libsodium-dev python3-pip 
sudo apt-get upgrade -y

# MusicBotをホームディレクトリに複製します
git clone https://github.com/Just-Some-Bots/MusicBot.git ~/MusicBot -b master
cd ~/MusicBot

# Pythonの依存関係をインストールする
sudo python3 -m pip install -U pip
sudo python3 -m pip install -U -r requirements.txt
~~~


## Ubuntu 18.04

~~~ bash
# ビルドツールをインストールする
sudo apt-get install build-essential unzip -y
sudo apt-get install software-properties-common -y

# システムの依存関係をインストールする
sudo apt-get update -y
sudo apt-get install git ffmpeg libopus-dev libffi-dev libsodium-dev python3-pip 
sudo apt-get upgrade -y

# MusicBotをホームディレクトリに複製します
git clone https://github.com/Just-Some-Bots/MusicBot.git ~/MusicBot -b master
cd ~/MusicBot

# Pythonの依存関係をインストールする
sudo python3 -m pip install -U pip
sudo python3 -m pip install -U -r requirements.txt
~~~

## Ubuntu 16.04

~~~ bash
# ビルドツールをインストールする
sudo apt-get install build-essential unzip -y
sudo apt-get install software-properties-common -y

# 外部リポジトリを追加する
sudo add-apt-repository ppa:mc3man/xerus-media -y
sudo add-apt-repository ppa:deadsnakes/ppa -y

# システムの依存関係をインストールする
sudo apt-get update -y
sudo apt-get install git ffmpeg libopus-dev libffi-dev libsodium-dev python3.6 -y
sudo apt-get upgrade -y

# pipをインストールする
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.6 get-pip.py

# MusicBotをホームディレクトリに複製します
git clone https://github.com/Just-Some-Bots/MusicBot.git ~/MusicBot -b master
cd ~/MusicBot

# Pythonの依存関係をインストールする
sudo python3.6 -m pip install -U pip
sudo python3.6 -m pip install -U -r requirements.txt 
~~~

## Ubuntu 14.04

~~~ bash
# ビルドツールをインストールする
sudo apt-get install build-essential unzip -y
sudo apt-get install software-properties-common -y

# 外部リポジトリを追加する
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo add-apt-repository ppa:mc3man/trusty-media -y
sudo add-apt-repository ppa:chris-lea/libsodium -y

# システムの依存関係をインストールする
sudo apt-get update -y
sudo apt-get install git python3.6 libav-tools libopus-dev libffi-dev libsodium-dev -y
sudo apt-get upgrade -y

# pipをインストールする
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python3.6 get-pip.py

# MusicBotをホームディレクトリに複製します
git clone https://github.com/Just-Some-Bots/MusicBot.git ~/MusicBot -b master
cd ~/MusicBot

# Pythonの依存関係をインストールする
sudo python3.6 -m pip install -U pip
sudo python3.6 -m pip install -U -r requirements.txt 
~~~

これらのコマンドを実行した後、ボットを[構成]({{ site.baseurl }}/using/configuration)し、 `sudo ./run.sh`を使用して実行できます。
