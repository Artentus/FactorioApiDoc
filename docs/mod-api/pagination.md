# Pagination JSON Object

Contains information about a page and its associated pages.

### Attributes

* **`count`**, Type: `Integer`  
The total number of mods.

* **`page`**, Type: `Integer`  
The `1`-based index of the page.

* **`page_count`**, Type: `Integer`  
The total number of pages.

* **`page_size`**, Type: `Integer`  
The number of mods on the page.

* **`links`**, Type: [`PageLinks`](../pagelinks)  
Links to associated pages.