# Update API Overview

The Update API can be used to manually download Factorio update packages that can then later be applied to a Factorio client or server.  
To access this API, [authentication](../auth-api/index.md) is required.

The domain to access the API is `https://updater.factorio.com`, all of the following paths are relative to this domain.

### Available Versions Endpoint

To get a complete list of available packages one can send a `GET` request to this endpoint located at `/get-available-versions`.

The following parameters must be specified:

* **`username`**, Type: `String`  
The name of the user to be logged in.

* **`token`**, Type: `128 bit Integer`  
The users login token, as aquired by authenticating earlier or found in the `player-data.json` file.

The following optional parameters can be specified:

* **`api_version`**, Type: `Integer`  
The version of the API to use.  
At the time of writing this the most recent version is `2`, which is also the default value when not specified.

If the request was successful, the server will return a JSON object of type [PackageList](packagelist.md).

### Download Endpoint

To download an update package, the download enpoint at `/get-download-link` can be used.

The following parameters must be specified:

* **`username`**, Type: `String`  
The name of the user to be logged in.

* **`token`**, Type: `128 bit Integer`  
The users login token, as aquired by authenticating earlier or found in the `player-data.json` file.

* **`package`**, Type: `String`  
One of the following strings, depending on which platform you are running Factorio on:  
`core-linux64`, `core-linux_headless64`, `core-mac`, `core-win64`, `core-linux32`, `core-win32`

* **`from`**, Type: `Version`  
The version of Factorio to be updated.

* **`to`**, Type: `Version`  
The target version you want to update to.

**Note:** Only such combinations of `from` and `to`are allowed that can be found in a [`Package`](package.md)
object in the [list](packagelist.md) corresponding to the `package` parameter.

The following optional parameters can also be specified:

* **`api_version`**, Type: `Integer`  
The version of the API to use.  
At the time of writing this the most recent version is `2`, which is also the default value when not specified.

This is an example of a valid request url:
```
https://updater.factorio.com/get-download-link?username=FactorioPlayer&token=152ae3e4c0ae57525c5d0c223b1b507d&package=core-win64&from=0.16.50&to=0.16.51
```

If the request was successful, the server will return a JSON `String`-array with a single entry, that being the download link.  
Example of a result:  
```
["https://eu3.factorio.com/updates/core-win64-0.16.50-0.16.51-update.zip?key=bvCb85QwBzUgzwEIliKw7Q&expires=1533955174"]
```
The generated link is only valid for a limited amount of time.

### Applying an Update Package

A downloaded update package can be applied by starting Factorio with the `--apply-update <package>` arguments.

On Windows this could for example look like this:  
```
factorio.exe --apply-update core-win64-0.16.50-0.16.51-update.zip
```
