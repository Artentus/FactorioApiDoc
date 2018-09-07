# Mod API Overview

The `Mod API` can be used to aquire various information about mods, as well as to download mods.
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

The server will return a JSON object of type [ModInfo](modinfo.md).
