# Timers

The timers endpoints allow you to view, add, edit, and remove channel timers.

## Timer Resource

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
			<td>The timer's unique ID</td>
		</tr>
		<tr>
			<td><code>createdAt</code></td>
			<td>date</td>
			<td>The time the timer was created</td>
		</tr>
		<tr>
			<td><code>enabled</code></td>
			<td>boolean</td>
			<td>The status of the timer. A value of <code>true</code> means the timer is enabled, while <code>false</code> means the timer is disabled and will not execute.</td>
		</tr>
		<tr>
			<td><code>interval</code></td>
			<td>string</td>
			<td>The timer interval in cron syntax. Minimum interval is once per 5 minutes.</td>
		</tr>
		<tr>
			<td><code>lines</code></td>
			<td>number</td>
			<td>This is the minimum amount of chat lines per 5 minutes required to activate the timer. This is useful in slow chats to prevent Nightbot from spamming in an empty channel.</td>
		</tr>
		<tr>
			<td><code>message</code></td>
			<td>string</td>
			<td>The message Nightbot sends to chat when the command is called. It can contain <a href="https://docs.nightbot.tv/commands/variableslist" target="_blank">variables</a> for extra functionality.</td>
		</tr>
		<tr>
			<td><code>name</code></td>
			<td>string</td>
			<td>The timer name (has no real significance but gives you a quick reference to what the timer does)</td>
		</tr>
		<tr>
			<td><code>nextRunAt</code></td>
			<td>date</td>
			<td>The next scheduled time the timer will execute</td>
		</tr>
		<tr>
			<td><code>updatedAt</code></td>
			<td>date</td>
			<td>The last time the timer was updated</td>
		</tr>
	</tbody>
</table>
