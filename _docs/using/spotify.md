---
title: Spotify
category: Using the bot
order: 5
---

> Discordは、Spotifyを使用して友達と音楽を聴くことをネイティブでサポートしています。 友達とSpotifyの音楽を聴くためだけにボットを使用したい場合は、代わりにネイティブ機能を使用する必要があります。 詳細については、[spotifyヘルプページ](https://support.spotify.com/jp/using_spotify/app_integrations/discord/)を参照してください。
MusicBotはSpotifyとの統合が制限されており、SpotifyURIをYouTubeで最も近いものに自動的に変換します。 Spotifyでは利用規約に従ってフルトラックをストリーミングまたはダウンロードできないため、完全な統合は不可能ですが、これは合理的な代替手段です。

## Spotify統合の有効化

1. まず、新しい[Spotifyアプリケーション](https://beta.developer.spotify.com/dashboard/applications)を作成します。 Spotifyアカウントにログインするように求められます。 そうしてから、右上の[アプリの作成]をクリックし、商用統合を開発しているかどうかを尋ねられたら[いいえ]をクリックします。 好きな名前を付けて、簡単に説明してください。 3つのボックスすべてにチェックマークを付けてから、[作成]を押します。
2. 最後に、Spotifyアプリケーションページで取得できるSpotifyクライアントIDとクライアントシークレットを使用してボットを[configuration]({{ site.baseurl }}/using/configuration)に記入します。 ボットを再起動し、詳細に問題がなければ、 `！play`コマンドでSpotifyURIを使用できるようになります。

## サポートされているURI

* Tracks (e.g `spotify:track:5SE57ljOIUJ1ybL9U6CuBH`)
* Albums (e.g `spotify:album:4ONwe8mcjVjNrzk9QL4H2w`)
* User playlists (e.g `spotify:user:topsify:playlist:1QM1qz09ZzsAPiXphF1l4S`)

## URIを取得する方法
Spotifyアプリケーションでサポートされているメディアを右クリックし、[共有]、[SpotifyURIのコピー]の順に移動します。

<img class="doc-img" src="{{ site.baseurl }}/images/spotify-uri.png" alt="Spotify URI example" style="width: 500px;"/>
