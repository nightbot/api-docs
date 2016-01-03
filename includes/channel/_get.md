## Get channel

```cURL
curl -X GET "https://api.nightbot.tv/1/channel" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "channel": {
        "_id": "567224fe9511a38f5114cae0",
        "name": "testing",
        "displayName": "Testing",
        "joined": true,
        "plan": "554eb4df3ee1bab94698bae8"
    }
}
```

Gets the current API user's channel information

**HTTP Request**

`GET https://api.nightbot.tv/1/channel`

**Scope**

`channel`