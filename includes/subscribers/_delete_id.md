## Delete subscriber by id

```cURL
curl -X DELETE "https://api.nightbot.tv/1/subscribers/56739fb5d0c250946ed67448" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200
}
```

Deletes a subscriber by id

**HTTP Request**

`DELETE https://api.nightbot.tv/1/subscribers/:id`

**Scope**

`subscribers`