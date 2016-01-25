## Get subscriber by id

```cURL
curl -X GET "https://api.nightbot.tv/1/subscribers/56739fb5d0c250946ed67448" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "subscriber": {
        "_id": "56739fb5d0c250946ed67448",
        "createdAt": "2015-12-18T05:55:01.458Z",
        "updatedAt": "2015-12-18T05:55:01.458Z",
        "provider": "twitch",
        "providerId": "96837452",
        "name": "test_user",
        "displayName": "Test_User"
    }
}
```

Looks up a subscriber by id

**HTTP Request**

`GET https://api.nightbot.tv/1/subscribers/:id`

**Scope**

`subscribers`
