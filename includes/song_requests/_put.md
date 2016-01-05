## Edit song request settings

```cURL
curl -X PUT "https://api.nightbot.tv/1/song_requests" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "enabled=false"

{
    "status": 200,
    "settings": {
        "youtube": {
            "limitToMusic": false,
            "limitToLikedVideos": true
        },
        "searchProvider": "soundcloud",
        "userLevel": "everyone",
        "playlist": "channel",
        "providers": ["soundcloud", "youtube"],
        "enabled": false,
        "volume": 59,
        "limits": {
            "queue": 20,
            "user": 10,
            "playlistOnly": false,
            "exemptUserLevel": "moderator"
        }
    },
    "providers": {
        "soundcloud": "SoundCloud",
        "youtube": "YouTube"
    },
    "playlists": {
        "channel": "Channel",
        "monstercat": "Monstercat",
        "twitch_music_library": "Twitch Music Library"
    }
}
```

Edits the song request settings

**HTTP Request**

`PUT https://api.nightbot.tv/1/song_requests`

**Scope**

`song_requests`

**Body Parameters**

The following parameters can be sent as a URL encoded string or JSON (using the appropriate `Content-Type` header). `PUT` requests usually require the entire model to be included in the request, but we allow partial updates.

<table>
	<thead>
		<tr>
			<th>Parameter</th>
			<th>Type</th>
			<th>Required</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>enabled</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>The status of song requests. If <code>true</code>, song requests are enabled and songs can be requested by users. If <code>false</code>, song requests are disabled and are nonfunctional.</td>
		</tr>
		<tr>
			<td>limits<br>.queue</td>
			<td>number</td>
			<td>Optional</td>
			<td>The maximum number of songs in the queue (minimum 1, maximum 100)</td>
		</tr>
		<tr>
			<td>limits<br>.user</td>
			<td>number</td>
			<td>Optional</td>
			<td>The maximum number of songs a user can request at a time (minimum 1, maximum 100)</td>
		</tr>
		<tr>
			<td>limits<br>.playlistOnly</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>If <code>true</code>, song requests will be limited to the configured <code>playlist</code>. If <code>false</code>, requests can be made from any listed <code>providers</code></td>
		</tr>
		<tr>
			<td>limits<br>.playlistOnly</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>If <code>true</code>, song requests will be limited to the configured <code>playlist</code>. If <code>false</code>, requests can be made from any listed <code>providers</code></td>
		</tr>
		<tr>
			<td>limits<br>.exemptUserLevel</td>
			<td>enum</td>
			<td>Optional</td>
			<td>The <a href="#userlevels">userlevel</a> required to be exempt from the limits</td>
		</tr>
		<tr>
			<td>playlist</td>
			<td>enum</td>
			<td>Optional</td>
			<td>The playlist AutoDJ will source from when the queue is empty. If <code>limits.playlistOnly</code> is <code>true</code> all requested songs must be on this playlist. Available playlists are listed in the song request settings GET endpoint as <code>playlists</code>.</td>
		</tr>
		<tr>
			<td>providers</td>
			<td>array</td>
			<td>Optional</td>
			<td>An array of enums for the enabled song request providers. Providers are the services which we support pulling songs from. Available providers are listed in the song request settings GET endpoint as <code>providers</code>.</td>
		</tr>
		<tr>
			<td>searchProvider</td>
			<td>enum</td>
			<td>Optional</td>
			<td>Instead of requiring users to request songs with a URL or ID, users can search for the closest match to request a song. This controls where that search is performed. Available providers are listed in the song request settings GET endpoint as <code>providers</code>.</td>
		</tr>
		<tr>
			<td>userLevel</td>
			<td>enum</td>
			<td>Optional</td>
			<td>The <a href="#userlevels">userlevel</a> required to be able to request songs</td>
		</tr>
		<tr>
			<td>volume</td>
			<td>number</td>
			<td>Optional</td>
			<td>The volume that the AutoDJ player runs at (minimum 0, maximum 100)</td>
		</tr>
		<tr>
			<td>youtube<br>.limitToMusic</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>To reduce non-music videos from being requested, you can limit to just the music category by setting this to <code>true</code>. If set to <code>false</code>, videos are not restricted to just the music category.</td>
		</tr>
		<tr>
			<td>youtube<br>.limitToLikedVideos</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>To reduce bad videos from being requested, you can limit to videos with more likes than dislikes by setting this to <code>true</code>. If set to <code>false</code>, videos with more dislikes than likes are able to be requested. Defaults to <code>true</code></td>
		</tr>
	</tbody>
</table>