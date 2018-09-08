# Mod API Overview

The Mod API can be used to aquire various information about mods, as well as to download mods.
To be able to download a mod, being [logged in](../auth-api/#login-endpoint) is required and the
logged in user must own a Factorio license.

The domain to access the API is `https://mods.factorio.com/api`, all of the following paths are
relative to this domain.

### Mods Endpoint

A complete list of available mods can be `GET`-requested from `/mods`.

The following optional parameters can be specified when requesting the mod list:

* **`page_size`**, Type: `Integer`  
The number of mods on a single page. The default value is `25`.  
Note that instead of a numeric value, the special keyword `max` is also allowed,
which will cause the server to put all alvailable mods on one page.

* **`page`**, Type: `Integer`  
The 1-based index of the page you want to request. The default value is `1`.

<!--
Is this still available? Getting no results when trying.

* **`namelist`**, Type: `String[]`  
A list of keywords to filter the results by.

Kind of, try this: https://mods.factorio.com/api/mods?namelist=boblibrary.
It seems very similar to https://mods.factorio.com/api/mods/boblibrary.
I haven't figured out how to send an array though...
This doesn't really work:
https://mods.factorio.com/api/mods?namelist=boblibrary,boblogistics

I don't really see the point if you can't send an array honestly...
-->

A complete request URL could look like this:  
```
https://mods.factorio.com/api/mods?page_size=100&page=5
```

The server will return a JSON object of type [ModListPage](modlistpage.md).

### Single Mod Endpoint
 
To get more information about a mod, a `GET` request has to be sent to `/mods/{mod-name}` or `/mods/{mod-name}/full`.  
For example:  
```
https://mods.factorio.com/api/mods/rso-mod/full
```

The server will return a JSON object of type [ModInfo](modinfo.md).

### Mod Download Endpoint

A mod release can be downloaded by combining the base url with the `download_url` attribute
[specified by the release](modrelease.md) and sending a `GET` request to the resulting url.  
To be able to download a mod, being [authenticated](../auth-api) is required, and the account needs to own a Factorio license.

The following parameters must be specified:

* **`username`**, Type: `String`  
The name of the user to be logged in.

* **`token`**, Type: `128 bit Integer`  
The users login token, as aquired by authenticating earlier or found in the `player-data.json` file.

A complete download url might look like this:  
```
https://mods.factorio.com/download/rso-mod/5a5f1ae6adcc441024d73a0d?username=FactorioPlayer&token=152ae3e4c0ae57525c5d0c223b1b507d 
```

When successful, the server will send back the requested mod file.