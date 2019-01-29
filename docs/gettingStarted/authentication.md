# Authentication

Before you can start using the Keeping API you need to authenticate the user. Authentication is done using the OAuth protocol.

## Registering your application

The first step to authentication is registering the application that will integrate the API. Registering only has to be done once. 

* To register your application log in to [Keeping](https://keeping.nl) 
* Click on the dropdown menu in the top right and select "my account"
* In the left menu click on "For developers"
* Click "Register application" in the top right and fill in the required information
* When done correctly your application should be in the list called "Your applications"

You should see the **OAuth cliend ID** and **OAuth Client Secret** in this list. These are required for later steps in the authentication process.

## Login and Authorize

The next step is to log into your keeping account and authorizing access to your application. To do so send a GET request to this URL: 

https://keeping.nl/oauth/login-and-authorize 

with the following headers:  

* **client_id** = your OAuth Client ID
* **redirect_uri** = the redirect_uri you entered while registering your application
* **response_type** = "code" 

Your code should be appended to the redirect_uri.

## Tokens

### Request

The last step to authentication requires you to do a POST request to the following URL:

https://keeping.nl/oauth/token

with the following body:

* **grant_type** : "authorization_code"
* **client_id** : your OAuth Client ID
* **client_secret** : your OAuth Client Secret
* **redirect_uri** : the redirect_uri you entered while registering your application
* **code** : the code you received in the previous step

### Response

If everything is done correctly you should receive the following response:

```JSON
{
    "token_type": "Bearer",
    "expires_in": 604799,
    "access_token": "...",
    "refresh_token": "..."
}
```

Whenever you want to do a request to the Keeping API you need to set the Authorization header in the request to the access token that you received preceeded by "Bearer ". For example:

**Authorization** = "Bearer eJFdjsklfdio..."

### Refreshing the Access Token

After the access token has expired it needs to be "refreshed" using the refresh token.
This can be done with the following POST request:

https://keeping.nl/oauth/token

with the following body:

* **grant_type** : "refresh_token"
* **refresh_token** : the refresh token  
* **client_id** : your OAuth Client ID
* **client_secret** : your OAuth Client Secret

You will get the same response as when originally requesting the tokens.