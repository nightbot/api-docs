## Get default commands

```cURL
curl -X GET "https://api.nightbot.tv/1/commands/default" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "_total": 8,
    "status": 200,
    "commands": [
        {
            "name": "!commands",
            "coolDown": 5,
            "enabled": true,
            "userLevel": "everyone",
            "_name": "commands",
            "_description": "Allows users to get a list of commands and moderators to manage commands",
            "_docs": "https://docs.nightbot.tv/commands/commands"
        },
        ...
    ]
}
```

Gets the current API user's default commands list

**HTTP Request**

`GET https://api.nightbot.tv/1/commands/default`

**Scope**

`commands_default`