## Import remote playlist

```cURL
curl -X POST "https://api.nightbot.tv/1/song_requests/playlist/import" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "url=https%3A%2F%2Fwww.youtube.com%2Fplaylist%3Flist%3DPLA11538113C16891A"

{
    "status": 200
}
```

Imports a remote playlist to the current user's channel.

**HTTP Request**

`POST https://api.nightbot.tv/1/song_requests/playlist/import`

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
			<td>url</td>
			<td>string</td>
			<td>Required</td>
			<td>This is the playlist to import. This is a playlist URL located at one of the supported song request providers</td>
		</tr>
	</tbody>
</table>
