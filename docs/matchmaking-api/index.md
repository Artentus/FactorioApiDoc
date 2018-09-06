# Matchmaking API Overview

The Matchmaking API is used for server owners to advertise their servers.
To access most of the Matchmaking API endpoints, [authentication](../auth-api/index.md) is required.

The domain to access the API is `https://multiplayer.factorio.com`, all of the following paths are relative to this domain.



### Get Games Endpoint

To get a list of servers one can join, a GET request must be sent to `/get-games`.  
The following parameters have to be sent:

* `username`, Type: `String`  
The name of the user to be logged in.  
Note that the e-mail can not be used here.

* `token`, Type: `128 bit Integer`  
The token that can be acquired using the [Authentication API](../auth-api/index.md).  
Alternatively, you can get the token from a file called `player-data.json`, located in the user data folder of the game, provided you are logged in inside the game.

If the credentials are correct, an array of [ServerDescription](./serverdescription.md) objects will be returned.

### Get Game Details Endpoint

To get more details about a server, one can send a GET request to `/get-game-details/{game_id}` where game_id is the server's game_id found in the response of the `/get-games` endpoint.
This endpoint does not require authentication.

If the credentials are correct, a [ServerDescription](./serverdescription.md) object with additional information will be returned.

### Create Game Endpoint

TODO

### Post Game Heartbeat Endpoint

TODO

### Remove Game Endpoint

TODO
