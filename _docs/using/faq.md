---
title: FAQ
category: Using the bot
order: 7
---

#### IDを取得するにはどうすればいいですか？

<img class="doc-img" src="{{ site.baseurl }}/images/ids.gif" alt="IDs" style="width: 350px; float: right;"/>

ボットには、IDを取得するために使用できる `!listids`コマンドがあります。または、Discordクライアントで[ユーザー設定]-> [外観]に移動して開発者モードをオンにすることもできます。 その後、任意のユーザー、チャネル、ロールなどを右クリックすると、コンテキストメニューに[IDのコピー]オプションが表示されます。 GIFはこれを示しています。

#### ボットは何をプレイできますか？

このボットは、YouTubeとSoundCloudのURLをサポートするために開発されましたが、理論的にはyoutube-dl [サポート](https://rg3.github.io/youtube-dl/supportedsites.html)のほとんどをサポートできます。 ボットでサポートされていないがyoutube-dlでサポートされているサイトがある場合は、[issue](https://github.com/Just-Some-Bots/MusicBot/issues/new)を作成してお知らせください サポートを追加したい。 ボットは、Twitchやインターネットラジオ（直接URLを指定した場合）などのストリームもサポートしますが、これは実験的な機能です。 これを行うには、 `!play`の代わりに`!stream`コマンドを使用します。

現在、ボットはコンピュータに保存されている音楽をローカルで再生できませんが、[予定されている機能](https://github.com/Just-Some-Bots/MusicBot/issues/168)です。.

#### ボットを変更できますか？

MusicBotはMITの下でライセンスされています。 変更したい場合は、変更できます。 これを行うためのサポートは提供しませんのでご注意ください。 Pythonで非同期コードを書く方法がわからない場合は、これを試みないでください。

#### ボットの応答を変更できますか？

ボットの応答を変更したい場合、おそらくユーザーの母国語が異なるため、ボットのソースコードを編集しなくても可能です。 JSONの基本を理解している限り、新しいi18nファイルを作成できます。 `config/i18n`フォルダーを開き、`en.json`を `whatever.json`にコピーしてから、コードエディター（Notepad ++、Atom、Visual Studio Codeなど）で開きます。

こんな感じになります:

```json
{
    "cmd-resetplaylist-response": "The server's autoplaylist has been reset.",
    "cmd-help-invalid": "No such command",
    ...
}
```

次に、値（各行のコロンの後）を好きなように変更できます。 ボットが自動的に挿入できるように、 `{0}`や `%s`のような変数を保持してください。

最後に、[JSONLint](https://jsonlint.com/)などのツールに貼り付けて、JSONが正しくフォーマットされ、有効であることを確認してから、構成ファイルのオプション `i18nFile`を` config/i18n.en.json `などとなるように変更します。。 ボットを起動して、始めましょう！ ファイルを読み込めない場合、ボットはデフォルト（ `en.json`）にフォールバックしようとします。 それができない場合は、エラーがスローされます。
