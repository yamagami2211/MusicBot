---
title: OpenBSD
category: Installing the bot
order: 8
---

MusicBotはOpenBSDシステムでも実行できます。 `ffmpeg`の依存関係のため、X11セットをインストールする必要があることに注意してください。

## OpenBSD 6.6

警告：py3-PyNaClパッケージがインストールされている場合、最後の `pip install`コマンドは、おそらく新しいシステムpynaclをpynacl 1.2.1で上書きし、他のパッケージを壊す可能性があります。  
これは、virtualenv（安全）を使用するか、requirements.txtを編集して固定されたバージョンを削除することで回避できます（自己責任で）。

~~~ bash
# パッケージとして利用可能なPythonとライブラリをインストールします
doas pkg_add python # select version 3.7.4
doas pkg_add py3-aiohttp youtube-dl ffmpeg libsodium git

# pipが設定されていることを確認します
python3 -m ensurepip

# MusicBotのクローンを作成する
git clone https://github.com/Just-Some-Bots/MusicBot.git -b master
cd MusicBot

# 残りの依存関係をインストールする
doas pip3 install -U pip
doas pip3 install -U -r requirements.txt
~~~

これらのコマンドを実行した後、ボットを[構成]({{site.baseurl}}/using/configuration)し、 `./run.py`を使用して実行できます。

OpenBSDの規則に従って、ボットをシステムの他の部分から特権分離しておくために、ボット専用のユーザーを作成することをお勧めします。 詳細については、 `useradd(1)` [マニュアルページ](https://man.openbsd.org/useradd)を参照してください。 システム起動時にボットを自動的に起動する方法の詳細については、 `rc.d(8)` [マニュアルページ](https://man.openbsd.org/rc.d)を参照してください。
