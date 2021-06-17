---
title: Troubleshooting
category: Using the bot
order: 6
---

これは、ボットの一般的な問題と解決策の表です。 GitHubに問題を残す前、または[サポートサーバー](https://discord.gg/bots)でヘルプを求める前に、ここを確認してください。

Issue | Solution
--- | ---
`Bot was not installed using Git` | ボットを正しくインストールしませんでした。 ZIPをダウンロードするのではなく、Gitを使用してインストールする必要があります。 YouTubeビデオではなく、公式のインストールガイドを使用してください。
音楽を再生しながら遅れる| CPUとディスクの使用状況を確認してください。 十分な帯域幅があることを確認してください。 音声チャネルのビットレートを確認してください。 [Discordの問題](https://status.discordapp.com)がないことを確認してください。
`Bot can't login, bad credentials` | [ボットアプリケーションページ](https://discordapp.com/developers/applications/me)から構成ファイルに正しいトークンをコピーしたことを確認してください。 これは、クライアントシークレットではなく、**トークン**と呼ばれます。
`WebSocket connection is closed` | ボットはWebSocketの切断を処理しようとしますが、Discordの音声サーバーがダウンした場合などに問題が発生する場合があります。 このエラーが続く場合は、ボットを再起動するか、サーバーリージョンを切り替えてみてください。
`./run.sh: command not found` | Gitはファイルのパーミッションを保持する必要がありますが、 `chmod a + x run.sh`を実行して、` run.sh`を実行可能に設定する必要がある場合があります。
`Your config file is missing some options.` | これは通常、ボットを更新した場合に発生します。 問題を回避するために、ボットの更新では構成ファイルを新しいオプションで更新しませんが、 `example_options.ini`を更新します。 したがって、可能であれば、そのファイルを確認し、新しいオプションを構成ファイルにコピーする必要があります（または、構成ファイルを削除して完全に再構成します）。 ボットは、構成するまで不足しているオプションのデフォルト設定を使用するため、メッセージは単なる警告であり、ボットのパフォーマンスに影響を与えることはありません。
`git: unable to access 'https://github.com/Just-Some-Bots/MusicBot.git' SSL certificate problem: self signed certificate in certificate chain` | ウイルス対策を無効にしてみてください。 一部のウイルス対策ソフトウェアは、gitに干渉することが知られています。
`ValueError: Invalid format '.' for '%' style` | ボットのマスターブランチでPython3.8を使用している可能性があります。 これを解決するには、[Python 3.7](https://www.python.org/ftp/python/3.7.0/python-3.7.0.exe)をインストールするか、実行してレビュー用に更新するだけです。 `git checkout review`
`TypeError: __new__() got an unexpected keyword argument 'deny_new'` | これは、古いバージョンの `discord.py`が原因で発生します。 これを解決するには、次のコマンドで `discord.py`を更新します。`python -m pip install -U discord.py[voice]`
