## Get channel

```cURL
curl -X GET "https://api.nightbot.tv/1/channel" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "channel": {
        "_id": "567224fe9511a38f5114cae0",
        "createdAt": "2024-02-14T06:34:49.000Z",
        "updatedAt": "2024-03-23T03:17:27.568Z",
        "name": "testing",
        "displayName": "Testing",
        "avatar": "https://static-cdn.jtvnw.net/user-default-pictures-uv/dbdc9198-def8-11e9-8681-784f43822e80-profile_image-300x300.png",
        "provider": "twitch",
        "providerId": "12345678",
        "admin": false,
        "joined": true,
        "botId": "554eb4b73ee1bab94698bae7"
    }
}
```

Gets the current API user's channel information

**HTTP Request**

`GET https://api.nightbot.tv/1/channel`

**Scope**

`channel`
