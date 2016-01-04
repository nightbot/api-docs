## Get custom commands

```cURL
curl -X GET "https://api.nightbot.tv/1/commands" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "_total": 30,
    "status": 200,
    "commands": [
        {
            "_id": "56739fb5d0c250946ed6746e",
            "createdAt": "2015-12-18T05:55:01.735Z",
            "updatedAt": "2015-12-18T05:55:01.735Z",
            "name": "!testing",
            "message": "this is a test message",
            "coolDown": 30,
            "count": 0,
            "userLevel": "everyone"
        },
        ...
    ]
}
```

Gets the current API user's commands list

**HTTP Request**

`GET https://api.nightbot.tv/1/commands`

**Scope**

`commands`