# Subscribers

The subscribers endpoints allow you to view, add, edit, and remove channel subscribers. Subscribers can be granted extra permission for commands and spam protection.

This subscribers list complements any existing paid subscription service already existing. Twitch/YouTube only give paid subscription programs to some of the broadcasters, leaving many users without a subscription program. Other third party platforms may offer subscription services that offset the need for a subscription program for these affected users.

## Subscriber Resource

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
			<td>subscriber id</td>
		</tr>
		<tr>
			<td><code>createdAt</code></td>
			<td>date</td>
			<td>The time the subscriber was added</td>
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
			<td>The auth provider for the subscriber (<code>twitch</code>, <code>youtube</code>, <code>trovo</code>, <code>noice</code>, <code>soop</code>)</td>
		</tr>
		<tr>
			<td><code>providerId</code></td>
			<td>string</td>
			<td>The unique id for this user at the auth provider</td>
		</tr>
		<tr>
			<td><code>updatedAt</code></td>
			<td>date</td>
			<td>The last time the subscriber was updated</td>
		</tr>
	</tbody>
</table>
