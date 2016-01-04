## Delete timer by id

```cURL
curl -X DELETE "https://api.nightbot.tv/1/timers/568a4d15df4510b03deb65fc" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "status": 200
}
```

Deletes a timer by id

**HTTP Request**

`DELETE https://api.nightbot.tv/1/timers/:id`

**Scope**

`timers`