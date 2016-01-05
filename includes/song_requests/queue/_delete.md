## Clear queue

```cURL
curl -X DELETE "https://api.nightbot.tv/1/song_requests/queue" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200
}
```

Deletes all queue items

**HTTP Request**

`DELETE https://api.nightbot.tv/1/song_requests/queue`

**Scope**

`song_requests_queue`