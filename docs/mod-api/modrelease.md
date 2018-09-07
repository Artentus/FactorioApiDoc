# ModRelease JSON Object

Contains information about a mod release, including how to download it.

### Attributes

* **`version`**, Type: `Version`  
The version number of this release.  

* **`released_at`**, Type: `Date`  
The date this release was published, formatted in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601).

* **`info_json`**, Type: [`InfoFile`](../infofile)  
Contains select information taken from the mods `info.json` file.

* **`download_url`**, Type: `Uri`  
A relative url that points to the mod file.

* **`file_name`**, Type: `String`  
The name of the mod file.  
Saving the file under any other name than this one will cause Factorio to throw an error when trying to load the mod.

* **`sha1`**, Type: `160 bit Integer`  
Formatted in hexadecimal, the [SHA-1](https://en.wikipedia.org/wiki/SHA-1) checksum of the mod file.