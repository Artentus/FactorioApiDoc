# AuthenticationResult JSON Object

An `AuthenticationResult` object is returned from a successful request to the [login endpoint](../#login-endpoint).

### Attributes

* `token`, Type: `128 bit Integer`  
A login token unique to the authenticated user that can be used to access other APIs.  
The token is encoded in hexadecimal and is best stored as a `String`, as the number representation is not useful.

* `username`, Type: `String`  
The name of the authenticated user.  
This value is useful if authentication was done using an e-mail, as all other APIs require the use of the name and do not allow an e-mail.