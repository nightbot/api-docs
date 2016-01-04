## Get filters

```cURL
curl -X GET "https://api.nightbot.tv/1/spam_protection" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "filters": [
        {
            "enabled": true,
            "length": 600,
            "blacklist": "◕_◕*\nᴘɪᴢᴢᴀ\nˢʷᵉᵃʳ",
            "message": "",
            "silent": false,
            "exemptUserLevel": "subscriber",
            "_type": "blacklist",
            "_name": "Blacklist Words/Phrases",
            "_description": "This filter allows you to timeout custom words, phrases, and patterns.",
            "_docs": "https://docs.nightbot.tv/spam-protection/blacklist"
        },
        ...
    ]
}
```

Gets the current API user's spam protection filters list

**HTTP Request**

`GET https://api.nightbot.tv/1/spam_protection`

**Scope**

`spam_protection`