## Basic Steps

All applications follow a basic pattern when accessing the Nightbot API using OAuth 2. At a high level, you follow four steps:

**1. Obtain OAuth 2 credentials from the Nightbot Control Panel.**

  Visit the Nightbot Control Panel's Account [Applications](https://beta.nightbot.tv/account/applications) page to obtain OAuth 2 credentials such as a client ID and client secret that are known to both Google and your application.

**2. Obtain an access token from the Nightbot API.**

  Before your application can access private data using the Nightbot API, it must obtain an access token that grants access to the API. A single access token can grant varying degrees of access to the API. A variable parameter called scope controls the set of operations that an access token permits. During the access-token request, your application sends one or more values in the scope parameter.

  There are several ways to make this request, and they vary based on the type of application you are building. For example, a server-side application might request an access token by exchanging a code redirected from our authorization endpoint, while a JavaScript application might request an access token using a browser redirect to our authorization endpoint.

  Some requests require an authentication step where the user logs in with their Nightbot account (if they are not previously logged in). After logging in, the user is asked whether they are willing to grant the permissions that your application is requesting. This process is called user consent.

  If the user grants the permission, the Nightbot API sends your application an access token (or an authorization code that your application can use to obtain an access token). If the user does not grant the permission, the server returns an error.

  It is generally a best practice to request scopes incrementally, at the time access is required, rather than up front.

**3. Send the access token to an API.**

  After an application obtains an access token, it sends the token to the Nightbot API in an HTTP authorization header. It is possible to send tokens as URI query-string parameters, but we don't recommend it, because URI parameters can end up in log files that are not completely secure. Also, it is good REST practice to avoid creating unnecessary URI parameter names.

  Access tokens are valid only for the set of operations and resources described in the scope of the token request.

**4. Refresh the access token, if necessary.**

  Access tokens have limited lifetimes. If your application needs access to the Nightbot API beyond the lifetime of a single access token, it can obtain a refresh token. A refresh token allows your application to obtain new access tokens.

<aside class="notice">
Note: Save refresh tokens in secure long-term storage and continue to use them as long as they remain valid. Limits apply to the number of refresh tokens that are issued per client-user combination, and per user across all clients, and these limits are different. If your application requests enough refresh tokens to go over one of the limits, older refresh tokens stop working.
</aside>
