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

> This section is about the config options in options.ini. For help with the actual permissions file, see [here]({{ site.baseurl }}/using/permissions).

- `OwnerID` - The ID of your Discord user, who will gain full permissions for the bot. If this is set to `auto`, the bot will automatically determine its owner from who created the bot account
- `DevIDs` - The IDs of every Discord user that you would like to gain developer commands. These commands are dangerous and allow execution of arbitrary code. If you don't know what you're doing, don't add any IDs here

#### Chat

- `CommandPrefix` - The prefix that will be used before every command, e.g if my prefix is `!`, I would use `!play` to queue a song
- `BindToChannels` - You can enter text channel IDs in here (seperated by spaces) to only allow the bot to respond in those channels
- `AutojoinChannels` - You can enter voice channel IDs in here (seperated by spaces) to force the bot to join those channels on launch (one per server)

#### MusicBot

- `DefaultVolume` - The volume that your bot starts at when launched, between `0.01` and `1.0`. Recommended: `0.15`
- <span class="badge warn">deprecated</span> `WhiteListCheck` - If enabled, the bot can only be used by users whose IDs are in `whitelist.txt`.
- `SkipsRequired` & `SkipsRatio` - The required amount/ratio of votes to skip before skipping. The lower value of the two is used. Deafened users and the owner does not count towards the ratio
- `SaveVideos` - Whether videos should be saved to the disk for if they are queued again. If you care about disk space, keep this disabled
- `NowPlayingMentions` - Whether to mention the user that requested a song when their song starts playing
- `AutoSummon` - Whether the bot should automatically connect to the owner's voice channel on startup. This takes precendence over `AutojoinChannels`
- `UseAutoPlaylist` - Whether to play music from `autoplaylist.txt` when joining a voice channel and when nothing is queued
- `AutoPlaylistRandom` - Whether the autoplaylist should play music randomly or sequentially when it is enabled
- `AutoPause` - Whether the bot should pause if nobody is in the voice channel
- `DeleteMessages` - Whether the bot should delete its messages after a short period of time
- `DeleteInvoking` - Whether the bot should delete user command messages after a short period of time. `DeleteMessages` must be enabled for this to work too
- `PersistentQueue` - Whether the bot should save the queue to the disk regularly so it can recover if it is unexpectedly shutdown
- `DebugLevel` - Determines what messages are logged. This is generally not needed to be changed unless you are asked to do so when receiving support
- `StatusMessage` - Allows users to specify a custom "Playing" status message for the bot, rather than the dynamic ones the bot provides
- `WriteCurrentSong` - Whether the bot should write the current song to a text file on the disk, which can then be used in OBS or other software
- `AllowAuthorSkip` - Whether the person who queues a song should be allowed to instantly skip it if they use `!skip f`
- `UseExperimentalEqualization` - Whether the bot should try to equalize tracks to ensure they play at a consistent volume
- `UseEmbeds` - Whether the bot should use Discord embeds when sending messages
- `QueueLength` - How many songs should appear in the `queue` command
- `RemoveFromAPOnError` - Whether the bot should remove songs from the autoplaylist if there is an error
- `ShowConfigOnLaunch` - Whether the bot should print the configuration options when it starts
- `LegacySkip` - Whether to use legacy skip behavior, defaulting `!skip` to force skip
- `LeaveServersWithoutOwner` - Whether the bot should leave servers that the owner is not found in
- `UseAlias` - Whether the bot should use aliases defined in `aliases.json`
- <span class="badge major">review only</span> `CustomEmbedFooter` - Changes the footer text found in embeds from the default version footer

#### Files

- `i18nFile` - The internationalization file to use for the bot (relative path, e.g `config/i18n/en.json`)
