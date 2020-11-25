---
title: MacOS
category: Installing the bot
order: 3
---

<img class="doc-img" src="{{ site.baseurl }}/images/mac.png" alt="Mac" style="width: 75px; float: right;"/>

MacにMusicBotをインストールするには、いくつかのライブラリとアプリケーションが必要です。 まず、Python3.5以降をシステムにインストールします。 最良の結果を得るには、[Python 3.5.4](https://www.python.org/ftp/python/3.5.4/python-3.5.4-macosx10.6.pkg)をインストールします(pkgファイルをダブルクリックします)。 次に、ターミナルを開いて次のコマンドを実行する必要があります。

```bash
# Homebrewをインストールする
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew update
xcode-select --install

# 依存関係をインストールする
brew install git
brew install ffmpeg
brew install opus
brew install libffi
brew install libsodium

# MusicBotのクローンを作成する
cd desktop
git clone https://github.com/Just-Some-Bots/MusicBot.git MusicBot -b master 

# Pythonの依存関係をインストールする
cd MusicBot
python3 -m pip install -U pip
python3 -m pip install -U -r requirements.txt
```

この後、デスクトップに「MusicBot」というフォルダがあります。 次に、ボットを開いて[configure]({{site.baseurl}}/using/configuration)し、 `run.sh`ファイルをダブルクリックしてボットを実行します。 これを実行できない場合は、ターミナルを開いてフォルダにcdし、 `chmod + xrun.sh`を使用してファイルに実行可能権限を付与する必要があります。
