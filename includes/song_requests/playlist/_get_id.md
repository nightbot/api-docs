## Get playlist item by id

```cURL
curl -X GET "https://api.nightbot.tv/1/song_requests/playlist/567baac77aa5ea140225baf0" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

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

Looks up a song request playlist item by id

**HTTP Request**

`GET https://api.nightbot.tv/1/song_requests/playlist/:id`

**Scope**

`song_requests_playlist`
