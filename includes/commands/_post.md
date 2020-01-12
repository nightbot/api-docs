## Add new custom command

```cURL
curl -X POST "https://api.nightbot.tv/1/commands" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "message=test%20message" \
  -d "userLevel=everyone" \
  -d "coolDown=5" \
  -d "name=!test"

{
    "status": 200,
    "command": {
        "createdAt": "2016-01-04T05:26:27.593Z",
        "updatedAt": "2016-01-04T05:26:27.593Z",
        "name": "!test",
        "message": "test message",
        "_id": "568a02834184d1a07660f380",
        "coolDown": 5,
        "count": 0,
        "userLevel": "everyone"
    }
}
```

Adds a new custom command to the current user's channel

**HTTP Request**

`POST https://api.nightbot.tv/1/commands`

**Scope**

`commands`

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
			<td>coolDown</td>
			<td>number</td>
			<td>Required</td>
			<td>The minimum amount of seconds between command usage (prevents spam).</td>
		</tr>
		<tr>
			<td>message</td>
			<td>string</td>
			<td>Required</td>
			<td>The message to send to chat. It can contain <a href="https://docs.nightbot.tv/commands/variableslist" target="_blank">variables</a> for extra functionality. Maximum length: 400 characters</td>
		</tr>
		<tr>
			<td>name</td>
			<td>string</td>
			<td>Required</td>
			<td>The command name (usually prefixed with a !, but any prefix [or none] can be used)</td>
		</tr>
		<tr>
			<td>userLevel</td>
			<td>enum</td>
			<td>Required</td>
			<td>The <a href="#userlevels">userlevel</a> required to use the command.</td>
		</tr>
	</tbody>
</table>