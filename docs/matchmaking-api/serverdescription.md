# ServerDescription JSON Object

### Attributes

Depending on the type of request you made, the result may contain different attributes.

| Key                 | Type                                        | Description                                           | /get-games | /get-game-details |
|:--------------------|:--------------------------------------------|:------------------------------------------------------|:-----------|:------------------|
| game_id             | Interger                                    | A unique identifier of this game                      | ✓          | ✓                 |
| name                | String                                      | The name of this game                                 | ✓          | ✓                 |
| max_players         | Integer                                     | The maximum allowed amount of players on this server  | ✓          | ✓                 |
| application_version | [ApplicationVersion](./appversion.md) | An object with information about the server           | ✓          | ✓                 |
| game_time_elapsed   | String                                      | The time that has passed since the game started       | ✓          | ✓                 |
| has_password        | Boolean                                     | Whether the server has a password or not              | ✓          | ✓                 |
| server_id           | String                                      | A unique identifier for the server                    | ✓          | ✓                 |
| tags                | String[]                                    | An array of tags, can be anything                     | ✓          | ✓                 |
| last_heartbeat      | Integer                                     | A Unix timestamp of the time since the last heartbeat | ✓          | ✓                 |
| has_mods            | Boolean                                     | Whether this is a modded game or not                  | ✓          |                   |
| mod_count           | Integer                                     | The amount of mods used in the game                   | ✓          |                   |
| description         | String                                      | A description of the game                             |            | ✓                 |
| host_address        | String                                      | The ip-address of the host                            |            | ✓                 |
| mods                | String[]                                    | An array of mods being used in the game               |            | ✓                 |
| mods_crc            | Integer                                     | TODO: Find meaning of this key                        |            | ✓                 |