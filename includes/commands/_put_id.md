## Edit custom command by id

```cURL
curl -X PUT "https://api.nightbot.tv/1/commands/568a02834184d1a07660f380" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "name=!testing"

{
    "status": 200,
    "command": {
        "createdAt": "2016-01-04T05:26:27.593Z",
        "updatedAt": "2016-01-04T05:26:27.593Z",
        "name": "!testing",
        "message": "test message",
        "_id": "568a02834184d1a07660f380",
        "coolDown": 5,
        "count": 0,
        "userLevel": "everyone"
    }
}
```

Edits a custom command by its id.

**HTTP Request**

`PUT https://api.nightbot.tv/1/commands/:id`

**Scope**

`commands`

**Body Parameters**

The following parameters can be sent as a URL encoded string or JSON (using the appropriate `Content-Type` header). `PUT` requests usually require the entire model to be included in the request, but we allow partial updates.

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
			<td>message</td>
			<td>string</td>
			<td>Required</td>
			<td>The message to send to chat. It can contain <a href="https://docs.nightbot.tv/commands/variables" target="_blank">variables</a> for extra functionality. Maximum length: 400 characters</td>
		</tr>
		<tr>
			<td>name</td>
			<td>string</td>
			<td>Required</td>
			<td>The command name (usually prefixed with a !, but any prefix [or none] can be used)</td>
		</tr>
		<tr>
			<td>coolDown</td>
			<td>number</td>
			<td>Optional</td>
			<td>The minimum amount of seconds between command usage (prevents spam). Defaults to <code>30</code></td>
		</tr>
		<tr>
			<td>count</td>
			<td>number</td>
			<td>Optional</td>
			<td>The number of times a command has been used (only increments if the command uses the count variable). Defaults to <code>0</code></td>
		</tr>
		<tr>
			<td>userLevel</td>
			<td>string</td>
			<td>Optional</td>
			<td>The <a href="#userlevels">userlevel</a> required to use the command. Defaults to <code>everyone</code></td>
		</tr>
	</tbody>
</table>