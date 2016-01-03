# Commands

The commands endpoints allow you to view, add, edit, and remove channel commands. Default commands can only be enabled and disabled, not removed.

## Custom Command Resource

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
			<td>The command's unique ID</td>
		</tr>
		<tr>
			<td><code>createdAt</code></td>
			<td>date</td>
			<td>The time the command was created</td>
		</tr>
		<tr>
			<td><code>updatedAt</code></td>
			<td>date</td>
			<td>The last time the command was updated</td>
		</tr>
		<tr>
			<td><code>name</code></td>
			<td>string</td>
			<td>The command name (usually prefixed with a !, but any prefix [or none] can be used)</td>
		</tr>
		<tr>
			<td><code>message</code></td>
			<td>string</td>
			<td>The message Nightbot sends to chat when the command is called. It can contain <a href="https://docs.nightbot.tv/commands/variables" target="_blank">variables</a> for extra functionality.</td>
		</tr>
		<tr>
			<td><code>coolDown</code></td>
			<td>number</td>
			<td>The minimum amount of seconds between command usage (prevents spam)</td>
		</tr>
		<tr>
			<td><code>count</code></td>
			<td>number</td>
			<td>The number of times a command has been used (only increments if the command uses the count variable)</td>
		</tr>
		<tr>
			<td><code>userLevel</code></td>
			<td>enum</td>
			<td>The <a href="#userlevels">userlevel</a> required to use the command</td>
		</tr>
	</tbody>
</table>

## Default Command Resource

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
			<td><code>_name</code></td>
			<td>string</td>
			<td>The command's unique name</td>
		</tr>
		<tr>
			<td><code>enabled</code></td>
			<td>boolean</td>
			<td>The status of the default command. If <code>true</code>, command is enabled. If <code>false</code>, the command is disabled and is nonfunctional.</td>
		</tr>
		<tr>
			<td><code>name</code></td>
			<td>string</td>
			<td>The command name (usually prefixed with a !, but any prefix [or none] can be used)</td>
		</tr>
		<tr>
			<td><code>coolDown</code></td>
			<td>number</td>
			<td>The minimum amount of seconds between command usage (prevents spam)</td>
		</tr>
		<tr>
			<td><code>userLevel</code></td>
			<td>enum</td>
			<td>The <a href="#userlevels">userlevel</a> required to use the command</td>
		</tr>
	</tbody>
</table>