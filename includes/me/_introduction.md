# Me

The me endpoint provides you with information about the authorized user

## Authorization Resource

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
			<td><code>userLevel</code></td>
			<td>enum</td>
			<td>Used internally. Always <code>owner</code> for oauth2.</td>
		</tr>
		<tr>
			<td><code>authType</code></td>
			<td>enum</td>
			<td>Used internally. Always <code>oauth2</code> for oauth2.</td>
		</tr>
		<tr>
			<td><code>credentials</code></td>
			<td>object</td>
			<td>Contains access token <code>expires</code> as a date and <code>client</code> id as a string (of the app the current access token belongs to)</td>
		</tr>
		<tr>
			<td><code>scopes</code></td>
			<td>array</td>
			<td>Array of scopes this authorization grants access to</td>
		</tr>
	</tbody>
</table>

## User Resource

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
			<td>User id</td>
		</tr>
		<tr>
			<td><code>admin</code></td>
			<td>boolean</td>
			<td>Whether or not the user is a Nightbot administrator</td>
		</tr>
		<tr>
			<td><code>avatar</code></td>
			<td>string</td>
			<td>User avatar link</td>
		</tr>
		<tr>
			<td><code>displayName</code></td>
			<td>string</td>
			<td>User display name</td>
		</tr>
		<tr>
			<td><code>name</code></td>
			<td>string</td>
			<td>User name</td>
		</tr>
		<tr>
			<td><code>provider</code></td>
			<td>enum</td>
			<td>The auth provider for the user account (<code>twitch</code>, <code>youtube</code>, <code>trovo</code>, <code>soop</code>)</td>
		</tr>
		<tr>
			<td><code>providerId</code></td>
			<td>string</td>
			<td>The unique id for this user at the auth provider</td>
		</tr>
	</tbody>
</table>
