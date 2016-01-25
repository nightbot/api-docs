## Get subscribers

```cURL
curl -X GET "https://api.nightbot.tv/1/subscribers" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

{
    "_total": 30,
    "status": 200,
    "subscribers": [
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

Gets the current API user's subscribers list

**HTTP Request**

`GET https://api.nightbot.tv/1/subscribers`

**Scope**

`subscribers`

**Query String Parameters**

<table>
    <thead>
        <tr>
            <th>Parameter</th>
            <th>Type</th>
            <th>Required</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>limit</td>
            <td>number</td>
            <td>Optional</td>
            <td>The is the maximum amount of regulars to return in the request (minimum 1, maximum 100)</td>
        </tr>
        <tr>
            <td>offset</td>
            <td>number</td>
            <td>Optional</td>
            <td>This is the regular offset count that is used for pagination</td>
        </tr>
        <tr>
            <td>q</td>
            <td>string</td>
            <td>Optional</td>
            <td>A <code>displayName</code> to search for (case insensitive)</td>
        </tr>
    </tbody>
</table>