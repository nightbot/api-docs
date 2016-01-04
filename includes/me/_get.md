## Get current user

```cURL
curl -X GET "https://api.nightbot.tv/1/me" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
  "status": 200,
  "authorization": {
    "userLevel": "owner",
    "authType": "oauth2",
    "credentials": {
      "expires": "2016-02-02T20:32:36.129Z",
      "client": "d3cfa25e47c9c18e51220e4757d8e57a"
    },
    "scopes": [
      "channel",
      "channel_send",
      "commands",
      "commands_default",
      "logs",
      "regulars",
      "song_requests",
      "song_requests_queue",
      "song_requests_playlist",
      "spam_protection",
      "timers"
    ]
  },
  "user": {
    "_id": "567224fe9511a38f5114cae0",
    "name": "testing",
    "displayName": "Testing",
    "provider": "twitch",
    "providerId": "24895647",
    "avatar": "https://static-cdn.jtvnw.net/jtv_user_pictures/testing-profile_image-b209b2800a897689-300x300.png",
    "admin": false
  }
}
```

Gets the current API user's information

**HTTP Request**

`GET https://api.nightbot.tv/1/me`

**Scope**

none required