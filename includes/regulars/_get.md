## Get regulars

```cURL
curl -X GET "https://api.nightbot.tv/1/regulars" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "_total": 30,
    "status": 200,
    "commands": [
        {
            "_id": "56739fb5d0c250946ed67448",
            "createdAt": "2015-12-18T05:55:01.458Z",
            "updatedAt": "2015-12-18T05:55:01.458Z",
            "provider": "twitch",
            "providerId": "96837452",
            "name": "test_user",
            "displayName": "Test_User"
        },
        ...
    ]
}
```

Gets the current API user's regulars list

**HTTP Request**

`GET https://api.nightbot.tv/1/regulars`

**Scope**

`regulars`