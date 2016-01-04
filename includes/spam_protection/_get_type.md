## Get filter by type

```cURL
curl -X GET "https://api.nightbot.tv/1/spam_protection/blacklist" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "filter": {
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
    }
}
```

Looks up a spam protection filter by type

**HTTP Request**

`GET https://api.nightbot.tv/1/spam_protection/:type`

**Scope**

`spam_protection`