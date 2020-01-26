## Send channel message

```cURL
curl -X POST "https://api.nightbot.tv/1/channel/send" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "message=test%20message"

{
    "status": 200
}
```

Makes Nightbot send a message to the channel

**HTTP Request**

`POST https://api.nightbot.tv/1/channel/send`

**Scope**

`channel_send`

**Rate Limit**

This endpoint is rate limited to 1 request per 5 seconds. If exceeded a HTTP 429 "Too Many Requests" response is returned.

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
			<td>message</td>
			<td>string</td>
			<td>Required</td>
			<td>The message to send to chat. Maximum length: 400 characters</td>
		</tr>
		<tr>
			<td>chatId</td>
			<td>string</td>
			<td>Optional</td>
			<td>The chat ID to send chat to. When not provided the message is sent to all chat rooms for this channel. This is only useful for YouTube channels with multiple concurrent chat rooms.</td>
		</tr>
	</tbody>
</table>
