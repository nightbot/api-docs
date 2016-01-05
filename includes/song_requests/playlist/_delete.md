## Clear playlist

```cURL
curl -X DELETE "https://api.nightbot.tv/1/song_requests/playlist" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200
}
```

Deletes all playlist items

**HTTP Request**

`DELETE https://api.nightbot.tv/1/song_requests/playlist`

**Scope**

`song_requests_playlist`