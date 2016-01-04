## Get default command by name

```cURL
curl -X GET "https://api.nightbot.tv/1/commands/default/commands" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200,
    "command": {
        "name": "!commands",
        "coolDown": 5,
        "enabled": true,
        "userLevel": "everyone",
        "_name": "commands",
        "_description": "Allows users to get a list of commands and moderators to manage commands",
        "_docs": "https://docs.nightbot.tv/commands/commands"
    }
}
```

Looks up a default command by name

**HTTP Request**

`GET https://api.nightbot.tv/1/commands/default/:name`

**Scope**

`commands_default`