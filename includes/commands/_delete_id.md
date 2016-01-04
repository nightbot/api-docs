## Delete custom command by id

```cURL
curl -X DELETE "https://api.nightbot.tv/1/commands/56739fb5d0c250946ed6746e" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200
}
```

Deletes a custom command by id

**HTTP Request**

`DELETE https://api.nightbot.tv/1/commands/:id`

**Scope**

`commands`