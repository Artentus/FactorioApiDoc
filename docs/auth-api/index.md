# Authentication API Overview

The Authentication API is used to log in on the official Factorio servers.  
Being logged in is required to download mods and to access the [Matchmaking API](../matchmaking-api/index.md).

The domain to access the API is `https://auth.factorio.com`, all of the following paths are relative to this domain.

### Login Endpoint

To log in, a HTTP POST request has to be sent to `/api-login`.

The following parameters have to be sent in `application/x-www-form-urlencoded` form:

* `username`, Type: `String`  
The name of the user to be logged in.  
Instead of the name, the e-mail can also be used.
However, note that this is actually the only place where the e-mail is a valid replacement for the name.

* `password`, Type: `String`  
The users password.

In addition, the following parameters are optional:

* `require_game_ownership`, Type: `Boolean`  
The default value when not specified is `False`.  
If `True` is specified, the request will only succeed if the user has bought a Factorio license (required to download mods).

* `api_version`, Type: `Integer`  
The version of the API to use.  
At the time of writing this the most recent version is `2`, which is also the default value when not specified.

As an example, a complete request string could look like this:
```
username=FactorioPlayer&password=SuperSecretPassword&require_game_ownership=true&api_version=2
```

If the credentials were invalid or `require_game_ownership=true` is specified and the account does not own a Factorio license, a code `401` is returned.  
If the login was successful, a code `200` is returned with an [AuthenticationResult](authresult.md) JSON object as response.