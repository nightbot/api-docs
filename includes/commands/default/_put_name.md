## Edit default command by name

```cURL
curl -X PUT "https://api.nightbot.tv/1/commands/default/commands" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "coolDown=6"

{
    "status": 200,
    "command": {
        "name": "!commands",
        "coolDown": 6,
        "enabled": true,
        "userLevel": "everyone",
        "_name": "commands",
        "_description": "Allows users to get a list of commands and moderators to manage commands",
        "_docs": "https://docs.nightbot.tv/commands/commands"
    }
}
```

Edits a default command by its name.

**HTTP Request**

`PUT https://api.nightbot.tv/1/commands/default/:name`

**Scope**

`commands_default`

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
			<td>coolDown</td>
			<td>number</td>
			<td>Optional</td>
			<td>The minimum amount of seconds between command usage (prevents spam).</td>
		</tr>
		<tr>
			<td>enabled</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>The status of the default command. If <code>true</code>, command is enabled. If <code>false</code>, the command is disabled and is nonfunctional.</td>
		</tr>
		<tr>
			<td>userLevel</td>
			<td>enum</td>
			<td>Optional</td>
			<td>The <a href="#userlevels">userlevel</a> required to use the command.</td>
		</tr>
	</tbody>
</table>