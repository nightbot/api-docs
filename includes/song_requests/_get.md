## Get song request settings

```cURL
curl -X GET "https://api.nightbot.tv/1/song_requests" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "settings": {
        "limits": {
            "queue": 20,
            "user": 10,
            "playlistOnly": false,
            "exemptUserLevel": "moderator"
        },
        "volume": 59,
        "enabled": true,
        "providers": [
            "soundcloud",
            "youtube"
        ],
        "playlist": "channel",
        "userLevel": "everyone",
        "searchProvider": "soundcloud",
        "youtube": {
            "limitToMusic": false,
            "limitToLikedVideos": true
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

Gets the current API user's song request settings

**HTTP Request**

`GET https://api.nightbot.tv/1/song_requests`

**Scope**

`song_requests`