## Revoking Tokens

```cURL
curl -X POST "https://api.nightbot.tv/oauth2/token/revoke" \
  -d "token=cfbdb83aaa4d5c2534c23329de35301a"
```

In some cases a user may wish to revoke access given to an application. A user can revoke access by visiting [Account Applications](https://nightbot.tv/account/applications). It is also possible for an application to programmatically revoke the access given to it. Programmatic revocation is important in instances where a user unsubscribes or removes an application. In other words, part of the removal process can include an API request to ensure the permissions granted to the application are removed.

To revoke an access or refresh token, pass the token in a **POST** request to the revocation endpoint:

  `https://api.nightbot.tv/oauth2/token/revoke`

The request must include the following parameters:

<table>
  <thead>
    <tr>
      <th style="width: 100px;">Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code><span>token</span></code></td>
      <td>The access or refresh token being revoked.</td>
    </tr>
  </tbody>
</table>
