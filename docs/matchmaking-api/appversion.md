# ApplicationVersion JSON Object

An object providing information about the platform the game is running on, as well as information about the version of the game.

### Attributes

* `build_mode`, Type: `String`  
The build version of the server.  
Possible values are `headless`, `alpha` and `steam`.

* `build_version`, Type: `Integer`  
The build number of the server.

* `game_version`, Type: `String`  
The version of the game used on the server.

* `platform`, Type: `String`  
The platform the server is running on.  
Usual values are `win64` and `linux64`.
