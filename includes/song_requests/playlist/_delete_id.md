## Delete playlist item by id

```cURL
curl -X DELETE "https://api.nightbot.tv/1/song_requests/playlist/567baac77aa5ea140225baf0" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200
}
```

Deletes a song requests playlist item by id

**HTTP Request**

`DELETE https://api.nightbot.tv/1/song_requests/playlist/:id`

**Scope**

`song_requests_playlist`