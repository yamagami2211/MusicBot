---
title: Windows
category: Installing the bot
order: 2
---

<img class="doc-img" src="{{ site.baseurl }}/images/windows.png" alt="Windows" style="width: 75px; float: right;"/>

> Gitを使用してボットのクローンを作成せず、代わりにGitHubからZIPファイルをダウンロードして実行しようとすると、エラーが発生します。

MusicBotはWindows7、8、および10にもインストールできますが、最初にコンピューターにいくつかのプログラムをインストールする必要があります。

1. [Python3.7](https://www.python.org/ftp/python)をインストールします。(3.5～3.7)
2. セットアップ中に、「すべてのユーザーにランチャーをインストールする（推奨）」にチェックマークを付け、プロンプトが表示されたら「Python3.7をPATHに追加する」にチェックマークを付けます。
3. [Git for Windows](http://gitforwindows.org/)をインストールします.
4. セットアップ中に、「コマンドラインとサードパーティソフトウェアからGit」、「Windowsスタイルをチェックアウトし、Unixスタイルのエンディングをコミットする」、「MinTTY（デフォルトのターミナルMSYS2）を使用する」にチェックマークを付けます。
5. フォルダ（マイドキュメントなど）内の空のスペースを右クリックし、[Git Bash here]をクリックして、GitBashを開きます。
6. 開いたコマンドウィンドウで `git clone https://github.com/Just-Some-Bots/MusicBot.git MusicBot -b master`を実行します。


その後、GitBashを開いたフォルダーに `MusicBot`というフォルダーが表示されます。 ボットを[構成]({{site.baseurl}}/using/configuration)してから、 `update.bat`を実行して依存関係を更新し、次に` run.bat`を実行してMusicBotを起動します。
