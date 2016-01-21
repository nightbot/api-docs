## Add new queue item

```cURL
curl -X POST "https://api.nightbot.tv/1/song_requests/queue" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "q=https%3A%2F%2Fyoutu.be%2Fr9gz0Z9yV1k"

{
    "status": 200,
    "item": {
        "_id": "5688d2bdc93762323f402b9d",
        "createdAt": "2016-01-03T07:50:21.334Z",
        "updatedAt": "2016-01-03T07:50:21.334Z",
        "track": {
            "providerId": "r9gz0Z9yV1k",
            "provider": "youtube",
            "duration": 197,
            "title": "I'm Just a Kid - Simple Plan lyrics",
            "artist": "sabrina01021997",
            "url": "https://youtu.be/r9gz0Z9yV1k"
        },
        "user": {
            "name": "test_user_2",
            "displayName": "test_user_2",
            "providerId": "93854453",
            "provider": "twitch"
        },
        "_position": 1
    }
}
```

Adds a new queue item to the current user's channel.

**HTTP Request**

`POST https://api.nightbot.tv/1/song_requests/queue`

**Scope**

`song_requests_queue`

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
			<td>This is the song to add to the queue. It can be a URL for one of the supported song request providers or a song name to search for (closest match is chosen and search is performed on the channel's selected search provider)</td>
		</tr>
	</tbody>
</table>
