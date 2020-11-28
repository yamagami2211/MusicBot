---
title: Arch
category: Installing the bot
order: 7
---

<img class="doc-img" src="{{ site.baseurl }}/images/arch.png" alt="centos" style="width: 75px; float: right;"/>
Archへのインストールは**ほとんどテストされておらず、問題のために公式にはサポートされていません**。 サポートを求めるときは、このことに注意してください。

~~~ bash
# システムパッケージを更新する
sudo pacman -Syu

# 依存関係をインストールする
sudo pacman -S git python python-pip opus libffi libsodium ncurses gdbm glibc zlib sqlite tk openssl ffmpeg

# MusicBotをホームディレクトリに複製します
cd ~
git clone https://github.com/Just-Some-Bots/MusicBot.git MusicBot -b master
cd MusicBot

# 依存関係をインストールする
sudo pip install --upgrade pip
sudo pip install --upgrade -r requirements.txt
~~~

すべてが完了したら、ボットを[configure]({{site.baseurl}}/using/configuration)して、 `sh ./run.sh`で実行できます。
