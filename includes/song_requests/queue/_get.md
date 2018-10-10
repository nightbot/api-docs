## Get queue

```cURL
curl -X GET "https://api.nightbot.tv/1/song_requests/queue" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
  "_total": 1,
  "_currentSong": {
    "_id": "56888945f788ea622d320c38",
    "createdAt": "2016-01-03T02:36:53.141Z",
    "updatedAt": "2016-01-05T07:39:10.710Z",
    "track": {
      "providerId": "v4Za061pQac",
      "provider": "youtube",
      "duration": 191,
      "title": "Alex Skrindo - Jumbo [NCS Release]",
      "artist": "NoCopyrightSounds",
      "url": "https://youtu.be/v4Za061pQac"
    },
    "user": {
      "name": "test_user_1",
      "displayName": "test_user_1",
      "providerId": "94385764",
      "provider": "twitch"
    }
  },
  "_requestsEnabled": true,
  "_searchProvider": "youtube",
  "status": 200,
  "queue": [
    {
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
  ]
}
```

Gets the current API user's song request queue

**HTTP Request**

`GET https://api.nightbot.tv/1/song_requests/queue`

**Scope**

`song_requests_queue`
