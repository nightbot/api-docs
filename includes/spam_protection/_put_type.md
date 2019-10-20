## Edit filter by type

```cURL
curl -X PUT "https://api.nightbot.tv/1/spam_protection/blacklist" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23" \
  -d "message=testing"

{
    "status": 200,
    "filter": {
        "enabled": true,
        "length": 600,
        "blacklist": "◕_◕*\nᴘɪᴢᴢᴀ\nˢʷᵉᵃʳ",
        "message": "testing",
        "silent": false,
        "exemptUserLevel": "subscriber",
        "_type": "blacklist",
        "_name": "Blacklist Words/Phrases",
        "_description": "This filter allows you to timeout custom words, phrases, and patterns.",
        "_docs": "https://docs.nightbot.tv/spam-protection/blacklist"
    }
}
```

Edits a spam protection filter by its type.

**HTTP Request**

`PUT https://api.nightbot.tv/1/spam_protection/:type`

**Scope**

`spam_protection`

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
			<td>blacklist</td>
			<td>string</td>
			<td>Optional</td>
			<td>New-line delimited list of blacklisted phrases. Wildcards can be used (`*`). RegEx is also supported (`~/[pattern]/[flags]`). Only can be used with filters supporting a blacklist.</td>
		</tr>
		<tr>
			<td>enabled</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>The status of the filter. If <code>true</code>, the filter is enabled. If <code>false</code>, the filter is disabled and is nonfunctional.</td>
		</tr>
		<tr>
			<td>exemptUserLevel</td>
			<td>enum</td>
			<td>Optional</td>
			<td>The <a href="#userlevels">userlevel</a> required to exempt from the filter</td>
		</tr>
		<tr>
			<td>length</td>
			<td>number</td>
			<td>Optional</td>
			<td>The length of time in seconds that Nightbot will timeout users for if detected by the filter</td>
		</tr>
		<tr>
			<td>limit</td>
			<td>number</td>
			<td>Optional</td>
			<td>The barrier at which the filter should timeout users, should the filter have one. Only can be used with filters supporting a limit.</td>
		</tr>
		<tr>
			<td>message</td>
			<td>string</td>
			<td>Optional</td>
			<td>The timeout message given to a user when they are timed out (if filter is not silenced). If empty string, defaults to Duke Nukem quotes.</td>
		</tr>
		<tr>
			<td>silent</td>
			<td>boolean</td>
			<td>Optional</td>
			<td>If <code>true</code>, the filter will not emit a message to chat telling to user why they were timed out. If <code>false</code>, the filter is will emit a message.</td>
		</tr>
		<tr>
			<td>whitelist</td>
			<td>string</td>
			<td>Optional</td>
			<td>New-line delimited list of whitelisted phrases. For the link whitelist this parses hostnames (like `youtube.com` unless wildcards or regex is used). Wildcards can be used (`*`). RegEx is also supported (`~/[pattern]/[flags]`). Only can be used with filters supporting a whitelist.</td>
		</tr>
	</tbody>
</table>
