## Edit timer by id

```cURL
curl -X PUT "https://api.nightbot.tv/1/timers/568a02834184d1a07660f380" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "name=testing"

{
    "status": 200,
    "timer": {
        "createdAt": "2016-01-04T05:26:27.593Z",
        "updatedAt": "2016-01-04T05:26:27.593Z",
        "name": "testing",
        "message": "test message",
        "_id": "568a02834184d1a07660f380",
        "interval": "*/15 * * * *",
        "nextRunAt": "1970-01-01T00:00:00.000Z",
        "lines": 2,
        "enabled": true
    }
}
```

Edits a timer by its id.

**HTTP Request**

`PUT https://api.nightbot.tv/1/timers/:id`

**Scope**

`timers`

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
			<td>enabled</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>The status of the timer. A value of <code>true</code> means the timer is enabled, while <code>false</code> means the timer is disabled and will not execute.</td>
		</tr>
		<tr>
			<td>interval</td>
			<td>string</td>
			<td>Optional</td>
			<td>The timer interval in cron syntax. Minimum interval is once per 5 minutes.</td>
		</tr>
		<tr>
			<td>lines</td>
			<td>number</td>
			<td>Optional</td>
			<td>This is the minimum amount of chat lines per 5 minutes required to activate the timer. This is useful in slow chats to prevent Nightbot from spamming in an empty channel.</td>
		</tr>
		<tr>
			<td>message</td>
			<td>string</td>
			<td>Optional</td>
			<td>The message to send to chat. It can contain <a href="https://docs.nightbot.tv/commands/variables" target="_blank">variables</a> for extra functionality. Maximum length: 400 characters</td>
		</tr>
		<tr>
			<td>name</td>
			<td>string</td>
			<td>Optional</td>
			<td>The timer name (has no real significance but gives you a quick reference to what the timer does)</td>
		</tr>
	</tbody>
</table>