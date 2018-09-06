# PageLinks JSON Object

Contains links to associated pages.

### Attributes

* **`first`**, Type: `Uri`  
A link to the first page.  
If the current page is already the first one, the value is `null`.

* **`last`**, Type: `Uri`  
A link to the last page.  
If the current page is already the last one, the value is `null`.

* **`next`**, Type: `Uri`  
A link to the next page.  
If the current page is the last page, the value is `null`.

* **`prev`**, Type: `Uri`  
A link to the previous page.  
If the current page is the first page, the value is `null`.