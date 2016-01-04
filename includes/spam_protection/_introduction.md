# Spam Protection

The spam protection endpoints allow you to view, edit, enable, and disable spam protection filters.

## Filter Resource

<table>
	<thead>
		<tr>
			<th style="width: 120px;">Fields</th>
			<th>Type</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><code>_limitMin</code></td>
			<td>number, optional</td>
			<td>If the filter contains a limit option, this defines its minimum value</td>
		</tr>
		<tr>
			<td><code>_limitMax</code></td>
			<td>number, optional</td>
			<td>If the filter contains a limit option, this defines its maximum value</td>
		</tr>
		<tr>
			<td><code>_name</code></td>
			<td>string</td>
			<td>The spam protection filter name</td>
		</tr>
		<tr>
			<td><code>_type</code></td>
			<td>enum</td>
			<td>The spam protection filter type</td>
		</tr>
		<tr>
			<td><code>blacklist</code></td>
			<td>string, optional</td>
			<td>New-line delimited list of blacklisted phrases. Wildcards can be used.</td>
		</tr>
		<tr>
			<td><code>enabled</code></td>
			<td>boolean</td>
			<td>The status of the filter. If <code>true</code>, the filter is enabled. If <code>false</code>, the filter is disabled and is nonfunctional.</td>
		</tr>
		<tr>
			<td><code>exemptUserLevel</code></td>
			<td>enum</td>
			<td>The <a href="#userlevels">userlevel</a> required to exempt from the filter</td>
		</tr>
		<tr>
			<td><code>length</code></td>
			<td>number</td>
			<td>The length of time in seconds that Nightbot will timeout users for if detected by the filter</td>
		</tr>
		<tr>
			<td><code>message</code></td>
			<td>string</td>
			<td>The timeout message given to a user when they are timed out (if filter is not silenced). If empty string, defaults to Duke Nukem quotes.</td>
		</tr>
		<tr>
			<td><code>silent</code></td>
			<td>boolean</td>
			<td>If <code>true</code>, the filter will not emit a message to chat telling to user why they were timed out. If <code>false</code>, the filter is will emit a message.</td>
		</tr>
		<tr>
			<td><code>whitelist</code></td>
			<td>string, optional</td>
			<td>New-line delimited list of whitelisted phrases.</td>
		</tr>
	</tbody>
</table>