## Add new subscriber

```cURL
curl -X POST "https://api.nightbot.tv/1/subscribers" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "name=test_user"

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

Adds a new subscriber to the current user's channel

**HTTP Request**

`POST https://api.nightbot.tv/1/subscribers`

**Scope**

`subscribers`

**Body Parameters**

The following parameters can be sent as a URL encoded string or JSON (using the appropriate `Content-Type` header).

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
			<td>name</td>
			<td>string</td>
			<td>Required</td>
			<td>This is the username of the person you wish to add as a subscriber. In the case of YouTube, it would be the user's YouTube channel URL.</td>
		</tr>
	</tbody>
</table>
