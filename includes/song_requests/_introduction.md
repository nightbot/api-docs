# Song Requests

The song request endpoints allow you to view, add, edit, and delete song from the song request queue and playlist as well as modify the settings for song requests.

## Song Request Settings Resource

<table>
	<thead>
		<tr>
			<th style="width: 150px;">Fields</th>
			<th>Type</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><code>enabled</code></td>
			<td>boolean</td>
			<td>The status of song requests. If <code>true</code>, song requests are enabled and songs can be requested by users. If <code>false</code>, song requests are disabled and are nonfunctional.</td>
		</tr>
		<tr>
			<td><code>limits</code></td>
			<td>object</td>
			<td>Contains user-configurable song request limits</td>
		</tr>
		<tr>
			<td><code>limits</code><br><code>.queue</code></td>
			<td>number</td>
			<td>The maximum number of songs in the queue (minimum 1, maximum 100)</td>
		</tr>
		<tr>
			<td><code>limits</code><br><code>.user</code></td>
			<td>number</td>
			<td>The maximum number of songs a user can request at a time (minimum 1, maximum 100)</td>
		</tr>
		<tr>
			<td><code>limits</code><br><code>.playlistOnly</code></td>
			<td>boolean</td>
			<td>If <code>true</code>, song requests will be limited to the configured <code>playlist</code>. If <code>false</code>, requests can be made from any listed <code>providers</code></td>
		</tr>
		<tr>
			<td><code>limits</code><br><code>.playlistOnly</code></td>
			<td>boolean</td>
			<td>If <code>true</code>, song requests will be limited to the configured <code>playlist</code>. If <code>false</code>, requests can be made from any listed <code>providers</code></td>
		</tr>
		<tr>
			<td><code>limits</code><br><code>.exemptUserLevel</code></td>
			<td>enum</td>
			<td>The <a href="#userlevels">userlevel</a> required to be exempt from the limits</td>
		</tr>
		<tr>
			<td><code>playlist</code></td>
			<td>enum</td>
			<td>The playlist AutoDJ will source from when the queue is empty. If <code>limits.playlistOnly</code> is <code>true</code> all requested songs must be on this playlist. Available playlists are listed in the song request settings GET endpoint as <code>playlists</code>.</td>
		</tr>
		<tr>
			<td><code>providers</code></td>
			<td>array</td>
			<td>An array of enums for the enabled song request providers. Providers are the services which we support pulling songs from. Available providers are listed in the song request settings GET endpoint as <code>providers</code>.</td>
		</tr>
		<tr>
			<td><code>searchProvider</code></td>
			<td>enum</td>
			<td>Instead of requiring users to request songs with a URL or ID, users can search for the closest match to request a song. This controls where that search is performed. Available providers are listed in the song request settings GET endpoint as <code>providers</code>.</td>
		</tr>
		<tr>
			<td><code>userLevel</code></td>
			<td>enum</td>
			<td>The <a href="#userlevels">userlevel</a> required to be able to request songs</td>
		</tr>
		<tr>
			<td><code>volume</code></td>
			<td>number</td>
			<td>The volume that the AutoDJ player runs at (minimum 0, maximum 100)</td>
		</tr>
		<tr>
			<td><code>youtube</code></td>
			<td>object</td>
			<td>YouTube-specific song request settings</td>
		</tr>
		<tr>
			<td><code>youtube</code><br><code>.limitToMusic</code></td>
			<td>boolean</td>
			<td>To reduce non-music videos from being requested, you can limit to just the music category by setting this to <code>true</code>. If set to <code>false</code>, videos are not restricted to just the music category.</td>
		</tr>
		<tr>
			<td><code>youtube</code><br><code>.limitToLikedVideos</code></td>
			<td>boolean</td>
			<td>To reduce bad videos from being requested, you can limit to videos with more likes than dislikes by setting this to <code>true</code>. If set to <code>false</code>, videos with more dislikes than likes are able to be requested. Defaults to <code>true</code></td>
		</tr>
	</tbody>
</table>

## Playlist Item Resource

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
			<td><code>_id</code></td>
			<td>string</td>
			<td>The playlist item's unique id</td>
		</tr>
		<tr>
			<td><code>createdAt</code></td>
			<td>date</td>
			<td>The time the playlist item was created</td>
		</tr>
		<tr>
			<td><code>track</code></td>
			<td>object</td>
			<td>Track Information</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.artist</code></td>
			<td>string, optional</td>
			<td>Track Artist</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.duration</code></td>
			<td>number</td>
			<td>Track Duration (in seconds)</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.provider</code></td>
			<td>enum</td>
			<td>Track Provider (like "youtube" or "soundcloud")</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.providerId</code></td>
			<td>string</td>
			<td>Track Provider's unique id</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.title</code></td>
			<td>string</td>
			<td>Track Title</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.url</code></td>
			<td>string</td>
			<td>Track URL</td>
		</tr>
		<tr>
			<td><code>updatedAt</code></td>
			<td>date</td>
			<td>The last time the playlist item was updated</td>
		</tr>
	</tbody>
</table>

## Queue Item Resource

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
			<td><code>_position</code></td>
			<td>number</td>
			<td>The queue item's position in the queue</td>
		</tr>
		<tr>
			<td><code>_id</code></td>
			<td>string</td>
			<td>The queue item's unique id</td>
		</tr>
		<tr>
			<td><code>createdAt</code></td>
			<td>date</td>
			<td>The time the queue item was created</td>
		</tr>
		<tr>
			<td><code>track</code></td>
			<td>object</td>
			<td>Track Information</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.artist</code></td>
			<td>string, optional</td>
			<td>Track Artist</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.duration</code></td>
			<td>number</td>
			<td>Track Duration (in seconds)</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.provider</code></td>
			<td>enum</td>
			<td>Track Provider (like "youtube" or "soundcloud")</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.providerId</code></td>
			<td>string</td>
			<td>Track Provider's unique id</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.title</code></td>
			<td>string</td>
			<td>Track Title</td>
		</tr>
		<tr>
			<td><code>track</code><br><code>.url</code></td>
			<td>string</td>
			<td>Track URL</td>
		</tr>
		<tr>
			<td><code>user</code></td>
			<td>object</td>
			<td>Information about who the queue item belongs to</td>
		</tr>
		<tr>
			<td><code>user</code><br><code>.displayName</code></td>
			<td>string</td>
			<td>User display name</td>
		</tr>
		<tr>
			<td><code>user</code><br><code>.name</code></td>
			<td>string</td>
			<td>User unique name</td>
		</tr>
		<tr>
			<td><code>user</code><br><code>.provider</code></td>
			<td>enum</td>
			<td>User provider (like "twitch" or "youtube")</td>
		</tr>
		<tr>
			<td><code>user</code><br><code>.providerId</code></td>
			<td>string</td>
			<td>User provider's unique id</td>
		</tr>
		<tr>
			<td><code>updatedAt</code></td>
			<td>date</td>
			<td>The last time the queue item was updated</td>
		</tr>
	</tbody>
</table>
