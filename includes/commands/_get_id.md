## Get custom command by id

```cURL
curl -X GET "https://api.nightbot.tv/1/commands/56739fb5d0c250946ed6746e" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "command": {
        "_id": "56739fb5d0c250946ed6746e",
        "createdAt": "2015-12-18T05:55:01.735Z",
        "updatedAt": "2015-12-18T05:55:01.735Z",
        "name": "!testing",
        "message": "this is a test message",
        "coolDown": 30,
        "count": 0,
        "userLevel": "everyone"
    }
}
```

Looks up a custom command by id

**HTTP Request**

`GET https://api.nightbot.tv/1/commands/:id`

**Scope**

`commands`