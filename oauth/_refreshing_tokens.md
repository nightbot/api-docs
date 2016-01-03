## Refreshing Tokens

```cURL
curl -X POST "https://api.nightbot.tv/oauth2/token"
  -d "client_id=d3cfa25e47c9c18e51220e4757d8e57a"
  -d "client_secret=50951bf21ec9639b210c7fda38665861"
  -d "grant_type=refresh_token"
  -d "redirect_uri=https%3A%2F%2Ftesting.com%2Fcallback"
  -d "refresh_token=cfbdb83aaa4d5c2534c23329de35301a"

{
  "access_token": "4fb1fed8889ec9d1c319d5b3c9a54b23",
  "refresh_token": "b98dbbc2e64789532de2c9e7c69b0f89",
  "token_type": "bearer",
  "expires_in": 2592000
}
```

As indicated in the previous sections, a refresh token is obtained in the token exchange with an authorization code. In this case, your application may obtain a new access token by sending a refresh token to the token endpoint:

  `https://api.nightbot.tv/oauth2/token`

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
      <td><code><span>refresh_token</span></code></td>
      <td>The refresh token of the access token being refreshed.</td>
    </tr>
    <tr>
      <td><code><span>client_id</span></code></td>
      <td>The client ID of the app.</td>
    </tr>
    <tr>
      <td><code><span>client_secret</span></code></td>
      <td>The client secret of the app.</td>
    </tr>
    <tr>
      <td><code><span>redirect_uri</span></code></td>
      <td>One of the redirect URIs listed for the app.</td>
    </tr>
    <tr>
      <td><code><span>grant_type</span></code></td>
      <td>As defined in the OAuth 2 specification, this field must contain a
      value of <code><span>refresh_token</span></code>.</td>
    </tr>
  </tbody>
</table>

The new access token can then be used to access the Nightbot API. Access tokens last 30 days and then must be replaced either by using the **new** refresh token flow or by reauthorizing the user with OAuth. Refresh tokens last 60 days.
