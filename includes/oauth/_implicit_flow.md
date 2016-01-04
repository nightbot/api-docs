## Implicit Flow

**1. Register an app**

  First you need to register an OAuth application on the [applications page](https://beta.nightbot.tv/account/applications) of your account area. Name your app and specify a URL users should be redirected to after authorizing your app. Because this is a client-side flow, you do not need to generate or use a client secret.

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
      <td><code><span>response_type</span></code></td>
      <td><code>token</code></td>
      <td>Determines whether the OAuth 2 endpoint returns a token in the fragment of the redirect url.</td>
    </tr>
    <tr>
      <td><code><span>client_type</span></code></td>
      <td>The client ID for the app</td>
      <td>Identifies the client that is making the request. The value passed in this parameter must exactly match the value for the app.</td>
    </tr>
    <tr>
      <td><code><span>redirect_uri</span></code></td>
      <td>One of the redirect url values listed for the app</td>
      <td>Determines where the response is sent. The value of this parameter must exactly match one of the values listed for this app (including the http or https scheme and casing).</td>
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

    `https://api.nightbot.tv/oauth2/authorize?response_type=token&client_id=d3cfa25e47c9c18e51220e4757d8e57a&redirect_uri=https%3A%2F%2Ftesting.com%2Fcallback&scope=commands%20timers`

**3. From the URL above users can choose to allow or deny your application access. Users will then be sent back to your application with an access token.**

Successful Response Example:

    `https://your_redirect_uri#access_token=cfbdb83aaa4d5c2534c23329de35301a&expires_in=2592000&token_type=bearer`

Unsuccessful Response Example:

    `https://your_redirect_uri#error=access_denied`

**5. The access token can then be used to access the Nightbot API. Access tokens last 30 days and then must be replaced by reauthorizing the user with OAuth. Refresh tokens are not issued for implicit authorizations, so it is not possible to refresh the access token with this implementation.**

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
