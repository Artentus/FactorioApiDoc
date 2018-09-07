# InfoFile JSON Object

Represents an `info.json` file as found inside a mod file.

### Attributes

* **`factorio_version`**, Type: `Version`  
The version of Factorio the release is compatible with.

* **`dependencies`**, Type: `String[]`  
A list of dependencies for this release.  
This attribute is only present if the release was requested using the `/full` [endpoint](../#single-mod-endpoint).