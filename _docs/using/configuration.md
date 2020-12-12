---
title: Configuration
category: Using the bot
order: 1
---

ボットの構成は比較的簡単です。 まず、ボットフォルダーを開き、次にその中の `config`フォルダーを開きます。 `example_options.ini`を` options.ini`にコピーします。 これは、構成を保存するファイルになります。 Notepad ++、Atom、Visual StudioCodeなどのコードエディターで開きます。

> メモ帳またはワードパッドを使用して構成ファイルを編集すると、ファイルが奇妙な形式で保存され、.iniファイルを編集するように設計されていないため、問題が発生します。

#### Credentials

<img class="doc-img" src="{{ site.baseurl }}/images/token.png" alt="Token" style="width: 500px;"/>

- `Token` - *これはボットを実行するために必要な唯一のオプションです。* Discordボットアカウントのトークンを提供する必要があります。 ボットアカウントを作成するには、[アプリケーションページ](https://discordapp.com/developers/applications/me)にアクセスし(プロンプトが表示されたらログイン)、この[10秒のビデオ](https://drive.google.com/file/d/1wZG_TBVfjQfj0CEYaRTzS60D-cbfeeYZ/view)。 それを完全に実行した場合は、トークンを公開して、構成ファイルにコピーできるようになっているはずです。

ボットアカウントを作成したら、アプリケーションページの[Generate OAuth2 URL]ボタンをクリックし、ボックス内のURLをアドレスバーにコピーしてEnterキーを押すことにより、ボットをサーバーに追加する必要があります。 次に、追加するサーバーを選択できます。
{: .info }

- `Spotify_ClientID` - SpotifyアプリケーションのクライアントID。 ボットの[Spotify integration]({{site.baseurl}}/using/spotify)に必要です。
- `Spotify_ClientSecret` - Spotifyアプリケーションのクライアントシークレット。 ボットの[Spotify integration]({{site.baseurl}}/using/spotify)に必要です。

#### Permissions

> このセクションでは、options.iniの構成オプションについて説明します。 実際のアクセス許可ファイルのヘルプについては、[ここ]({{ site.baseurl }}/using/permissions)を参照してください。

- `OwnerID` - ボットの完全な権限を取得するDiscordユーザーのID。 これが `auto`に設定されている場合、ボットはボットアカウントを作成した所有者を自動的に決定します
- `DevIDs` - 開発者コマンドを取得したいすべてのDiscordユーザーのID。 これらのコマンドは危険であり、任意のコードの実行を許可します。 何をしているのかわからない場合は、ここにIDを追加しないでください

#### Chat

- `CommandPrefix` - すべてのコマンドの前に使用されるプレフィックス。たとえば、プレフィックスが `!`の場合、 `!play`を使用して曲をキューに入れます。
- `BindToChannels` - ここにテキストチャネルIDを（スペースで区切って）入力して、ボットがそれらのチャネルでのみ応答できるようにすることができます
- `AutojoinChannels` - ここに音声チャネルIDを（スペースで区切って）入力して、起動時にボットをそれらのチャネルに強制的に参加させることができます（サーバーごとに1つ）

#### MusicBot

- `DefaultVolume` - ボットが起動されたときに開始するボリューム( `0.01`～` 1.0` )。 推奨: `0.15`
- <span class="badge warn">非推奨</span> `WhiteListCheck` - 有効にすると、ボットはIDが `whitelist.txt`にあるユーザーのみが使用できます。
- `SkipsRequired` & `SkipsRatio` - スキップする前にスキップするために必要な投票の量/比率。 2つのうち低い方の値が使用されます。 参加していないユーザーと所有者は比率にカウントされません
- `SaveVideos` - ビデオが再びキューに入れられる場合に備えて、ビデオをディスクに保存する必要があるかどうか。 ディスク容量が気になる場合は、これを無効にしてください
- `NowPlayingMentions` - 曲の再生開始時に曲をリクエストしたユーザーについて言及するかどうか
- `AutoSummon` - ボットが起動時に所有者の音声チャネルに自動的に接続する必要があるかどうか。 これは `AutojoinChannels`よりも優先されます
- `UseAutoPlaylist` - 音声チャンネルに参加するとき、および何もキューに入れられていないときに、 `autoplaylist.txt`から音楽を再生するかどうか
- `AutoPlaylistRandom` - 自動再生リストを有効にしたときに、音楽をランダムに再生するか、順番に再生するか
- `AutoPause` - 音声チャネルに誰もいない場合にボットを一時停止するかどうか
- `DeleteMessages` - ボットが短時間後にメッセージを削除する必要があるかどうか
- `DeleteInvoking` - ボットが短時間後にユーザーコマンドメッセージを削除する必要があるかどうか。 これも機能させるには、 `DeleteMessages`を有効にする必要があります
- `PersistentQueue` - ボットがキューを定期的にディスクに保存して、予期せずシャットダウンされた場合に回復できるようにするかどうか
- `DebugLevel` - ログに記録されるメッセージを決定します。 サポートを受けるときに変更するように求められない限り、これは通常変更する必要はありません。
- `StatusMessage` - ボットが提供する動的メッセージではなく、ボットのカスタム「再生中」ステータスメッセージをユーザーが指定できるようにします
- `WriteCurrentSong` - ボットが現在の曲をディスク上のテキストファイルに書き込む必要があるかどうか。このテキストファイルは、OBSまたは他のソフトウェアで使用できます。
- `AllowAuthorSkip` - `!skip f`を使用する場合、曲をキューに入れる人がすぐにスキップできるようにするかどうか
- `UseExperimentalEqualization` - ボットがトラックを均等化して、一定の音量で再生できるようにするかどうか
- `UseEmbeds` - ボットがメッセージを送信するときにDiscord埋め込みを使用する必要があるかどうか
- `QueueLength` - `!queue`コマンドに表示する曲の数
- `RemoveFromAPOnError` - エラーが発生した場合にボットが自動再生リストから曲を削除する必要があるかどうか
- `ShowConfigOnLaunch` - ボットが起動時に構成オプションを出力する必要があるかどうか
- `LegacySkip` - 従来のスキップ動作を使用するかどうか。デフォルトで `!skip`を使用してスキップを強制します。
- `LeaveServersWithoutOwner` - ボットが所有者が見つからないサーバーを離れるべきかどうか
- `UseAlias` - ボットが `aliases.json`で定義されたエイリアスを使用する必要があるかどうか
- <span class="badge major">レビュー版のみ</span> `CustomEmbedFooter` - 埋め込みで見つかったフッターテキストをデフォルトバージョンのフッターから変更します

#### Files

- `i18nFile` - ボットに使用する国際化ファイル (相対パスで記入する, e.g `config/i18n/en.json`)
