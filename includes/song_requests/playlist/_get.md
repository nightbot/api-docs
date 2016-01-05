## Get playlist

```cURL
curl -X GET "https://api.nightbot.tv/1/song_requests/playlist" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "_sort": {
        "date": "asc"
    },
    "_limit": 25,
    "_offset": 0,
    "_total": 34,
    "playlist": [
        {
            "track": {
                "providerId": "njos57IJf-0",
                "provider": "youtube",
                "duration": 168,
                "title": "Steve Jobs vs Bill Gates.  Epic Rap Battles of History Season 2.",
                "artist": "ERB",
                "url": "https://youtu.be/njos57IJf-0"
            },
            "_id": "567baac77aa5ea140225baec",
            "createdAt": "2015-12-24T08:20:23.268Z",
            "updatedAt": "2015-12-24T08:20:23.268Z"
        },
        ...
    ]
}
```

Gets the current API user's song request playlist

**HTTP Request**

`GET https://api.nightbot.tv/1/song_requests/playlist`

**Scope**

`song_requests_playlist`

**Query String Parameters**

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
            <td>direction</td>
            <td>enum</td>
            <td>Optional</td>
            <td>This is the sorting direction. Values are <code>asc</code> or <code>desc</code></td>
        </tr>
        <tr>
            <td>limit</td>
            <td>number</td>
            <td>Optional</td>
            <td>The is the maximum amount of playlist items to return in the request (minimum 1, maximum 100)</td>
        </tr>
        <tr>
            <td>offset</td>
            <td>number</td>
            <td>Optional</td>
            <td>This is the playlist item offset count that is used for pagination</td>
        </tr>
        <tr>
            <td>q</td>
            <td>string</td>
            <td>Optional</td>
            <td>A term to search for (case insensitive)</td>
        </tr>
        <tr>
            <td>sort_by</td>
            <td>enum</td>
            <td>Optional</td>
            <td>This is the sorting selection. Values are <code>artist</code>, <code>date</code>, <code>random</code>, <code>title</code>. Defaults to <code>date</code>.</td>
        </tr>
    </tbody>
</table>