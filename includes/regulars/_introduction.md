# Regulars

The regulars endpoints allow you to view, add, edit, and remove channel regulars. Nightbot Regulars adds another userlevel to the chat. Regulars can be granted extra permission for commands and spam protection.

## Regular Resource

<table>
	<thead>
		<tr>
			<th style="width: 100px;">Fields</th>
			<th>Type</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><code>_id</code></td>
			<td>string</td>
			<td>Regular id</td>
		</tr>
		<tr>
			<td><code>createdAt</code></td>
			<td>date</td>
			<td>The time the regular was added</td>
		</tr>
		<tr>
			<td><code>displayName</code></td>
			<td>string</td>
			<td>User display name</td>
		</tr>
		<tr>
			<td><code>name</code></td>
			<td>string</td>
			<td>User unique name</td>
		</tr>
		<tr>
			<td><code>provider</code></td>
			<td>enum</td>
			<td>The auth provider for the regular (<code>twitch</code>, <code>youtube</code>, <code>trovo</code>, <code>soop</code>)</td>
		</tr>
		<tr>
			<td><code>providerId</code></td>
			<td>string</td>
			<td>The unique id for this user at the auth provider</td>
		</tr>
		<tr>
			<td><code>updatedAt</code></td>
			<td>date</td>
			<td>The last time the regular was updated</td>
		</tr>
	</tbody>
</table>
