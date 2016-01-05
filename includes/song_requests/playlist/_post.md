## Add new playlist item

```cURL
curl -X POST "https://api.nightbot.tv/1/song_requests/playlist" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "q=https%3A%2F%2Fyoutu.be%2FN9qYF9DZPdw"

{
    "status": 200,
    "item": {
        "track": {
            "providerId": "N9qYF9DZPdw",
            "provider": "youtube",
            "duration": 171,
            "title": "\"Weird Al\" Yankovic - White & Nerdy (Official Video)",
            "artist": "alyankovicVEVO",
            "url": "https://youtu.be/N9qYF9DZPdw"
        },
        "_id": "567baac77aa5ea140225baf0",
        "createdAt": "2015-12-24T08:20:23.268Z",
        "updatedAt": "2015-12-24T08:20:23.268Z"
    }
}
```

Adds a new playlist item to the current user's channel.

**HTTP Request**

`POST https://api.nightbot.tv/1/song_requests/playlist`

**Scope**

`song_requests_playlist`

**Body Parameters**

The following parameters can be sent as a URL encoded string or JSON (using the appropriate `Content-Type` header).

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
			<td>q</td>
			<td>string</td>
			<td>Required</td>
			<td>This is the song to add to the playlist. It can be a URL for one of the supported song request providers or a song name to search for (closest match is chosen and search is performed on the channel's selected search provider)</td>
		</tr>
	</tbody>
</table>
