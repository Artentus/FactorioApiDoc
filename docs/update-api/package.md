# Package JSON Object

An object containing information about an update package.

### Attributes

* **`from`**, Type: `Version`  
The version of Factorio that can be updated with this package.

* **`to`**, Type: `Version`  
The version this package will update Factorio to.

* **`stable`**, Type: `Version`  
The latest stable version of Factorio.  
This attribute will only be contained in a special `Package` object that only appears exactly once per list.
This special object does also not contain any of the other attributes.