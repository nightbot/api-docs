## Authorization Code Flow

**1. Register an app**

  First you need to register an OAuth application on the [applications page](https://beta.nightbot.tv/account/applications) of your account area. Name your app and specify a URL users should be redirected to after authorizing your app. After creating an application, you need to generate a client secret. Click the edit button for your app on the apps page, and then click on the "New Secret" button.

<aside class="notice">
Be sure to keep your client secret confidential. It should only be kept server-side, and should not be embedded in client applications.
</aside>

**2. Once you have created an app, you can *302 redirect* users to our authorization endpoint:**

  `https://api.nightbot.tv/oauth2/authorize`

  with the following query string parameters:

<table>
  <thead>
    <tr>
      <th style="width: 100px;">Parameter</th>
      <th>Values</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code><span>client_id</span></code></td>
      <td>The client ID for the app</td>
      <td>Identifies the client that is making the request. The value passed in this parameter must exactly match the value for the app.</td>
    </tr>
    <tr>
      <td><code><span>redirect_uri</span></code></td>
      <td>One of the redirect url values listed for the app</td>
      <td>Determines where the response is sent. The value of this parameter must exactly match one of the values listed for this app (including the http or https scheme and casing).</td>
    </tr>
    <tr>
      <td><code><span>response_type</span></code></td>
      <td><code>code</code></td>
      <td>Determines whether the OAuth 2 endpoint returns an authorization code. Web server applications should use code.</td>
    </tr>
    <tr>
      <td><code><span>scope</span></code></td>
      <td>Space-delimited set of permissions that the application requests.</td>
      <td>Identifies the access that your application is requesting. The values passed in this parameter inform the consent screen that is shown to the user. There is an inverse relationship between the number of permissions requested and the likelihood of obtaining user consent. For information about available scopes, see <a href="#scopes">scopes</a>.</td>
    </tr>
    <tr>
      <td><code><span>state</span></code></td>
      <td>Any string</td>
      <td>Provides any state that might be useful to your application upon receipt of the response. The authorization server roundtrips this parameter, so your application receives the same value it sent. To mitigate against cross-site request forgery (CSRF), it is strongly recommended to include an anti-forgery token in the state, and confirm it in the response.</td>
    </tr>
  </tbody>
</table>

Example URL:

    `https://api.nightbot.tv/oauth2/authorize?response_type=code&client_id=d3cfa25e47c9c18e51220e4757d8e57a&redirect_uri=https%3A%2F%2Ftesting.com%2Fcallback&scope=commands%20timers`

**3. From the URL above users can choose to allow or deny your application access. Users will then be sent back to your application with a code.**

Successful Response Example:

    `https://your_redirect_uri?code=cfbdb83aaa4d5c2534c23329de35301a`

Unsuccessful Response Example:

    `https://your_redirect_uri?error=access_denied`

**4. With the authorization code sent back with the user, you can exchange it for an access token with a POST request to the following endpoint:**

  `https://api.nightbot.tv/oauth2/token`

```cURL
curl -X POST "https://api.nightbot.tv/oauth2/token" \
  -d "client_id=d3cfa25e47c9c18e51220e4757d8e57a" \
  -d "client_secret=50951bf21ec9639b210c7fda38665861" \
  -d "grant_type=authorization_code" \
  -d "redirect_uri=https%3A%2F%2Ftesting.com%2Fcallback" \
  -d "code=cfbdb83aaa4d5c2534c23329de35301a"

{
  "access_token": "4fb1fed8889ec9d1c319d5b3c9a54b23",
  "refresh_token": "b98dbbc2e64789532de2c9e7c69b0f89",
  "token_type": "bearer",
  "expires_in": 2592000,
  "scope": "commands timers"
}
```

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
      <td><code><span>client_id</span></code></td>
      <td>The client ID of the app.</td>
    </tr>
    <tr>
      <td><code><span>client_secret</span></code></td>
      <td>The client secret of the app.</td>
    </tr>
    <tr>
      <td><code><span>code</span></code></td>
      <td>The authorization code returned from the initial request.</td>
    </tr>
    <tr>
      <td><code><span>grant_type</span></code></td>
      <td>As defined in the OAuth 2 specification, this field must contain a
      value of <code><span>authorization_code</span></code>.</td>
    </tr>
    <tr>
      <td><code><span>redirect_uri</span></code></td>
      <td>One of the redirect URIs listed for the app.</td>
    </tr>
  </tbody>
</table>

A successful response from the token endpoint will return an access token and a refresh token.

<table>
  <thead>
    <tr>
      <th style="width: 100px;">Field</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code><span>access_token</span></code></td>
      <td>The token that can be sent to the Nightbot API.</td>
    </tr>
    <tr>
      <td><code><span>expires_in</span></code></td>
      <td>The remaining lifetime of the access token.</td>
    </tr>
    <tr>
      <td><code><span>refresh_token</span></code></td>
      <td>A token that may be used to obtain a new access token. Refresh tokens
      are valid until the user revokes access, they expire, or they are used.
    </tr>
    <tr>
      <td><code><span>token_type</span></code></td>
      <td>Identifies the type of token returned. At this time, this field will
      always have the value <code><span>bearer</span></code>.</td>
    </tr>
    <tr>
      <td><code><span>scope</span></code></td>
      <td>A space separated list of scopes attached to the token returned.
      This should be identical to scopes requested during authorization.</td>
    </tr>
  </tbody>
</table>

**5. The access token can then be used to access the Nightbot API. Access tokens last 30 days and then must be replaced either by using the refresh token flow or by reauthorizing the user with OAuth. Refresh tokens last 60 days, and a new one is issued by the refresh token flow should you choose to use it.**

```cURL
# Access the API via header
curl -X GET "https://api.nightbot.tv/1/me" \
  -H "Authorization: Bearer 4fb1fed8889ec9d1c319d5b3c9a54b23"

# Access the API via query string
curl -X GET "https://api.nightbot.tv/1/me?access_token=4fb1fed8889ec9d1c319d5b3c9a54b23"
```

**Accessing the API via header:**

<aside>
GET /1/me HTTP/1.1<br>
Authorization: Bearer <code>access_token</code><br>
Host: api.nightbot.tv
</aside>

**Accessing the API via query string:**

<aside>
GET /1/me?access_token=<code>access_token</code><br>
Host: api.nightbot.tv
</aside>
