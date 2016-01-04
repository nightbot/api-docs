## Get timers

```cURL
curl -X GET "https://api.nightbot.tv/1/timers" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "_total": 1,
    "status": 200,
    "timers": [
        {
            "_id": "568a4d15df4510b03deb65fc",
            "createdAt": "2016-01-04T10:44:37.440Z",
            "updatedAt": "2016-01-04T10:44:37.440Z",
            "name": "test",
            "message": "test",
            "interval": "*/15 * * * *",
            "nextRunAt": "1970-01-01T00:00:00.000Z",
            "lines": 2,
            "enabled": true
        },
        ...
    ]
}
```

Gets the current API user's timers list

**HTTP Request**

`GET https://api.nightbot.tv/1/timers`

**Scope**

`timers`