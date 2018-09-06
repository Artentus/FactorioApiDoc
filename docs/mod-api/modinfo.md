# ModInfo JSON Object

A `ModInfo` object contains information about a mod.  
It is returned either directly by [requesting info about a mod](../#single-mod-endpoint)
or in a list by [requesting a list of mods](../#mods-endpoint).

### Attributes

Depending on which endpoint was used, a `ModInfo` object can contain different attributes:

| Key                 | Type                                        | Description                                           | /mods | /mods/{mod-name} | /mod/{mod-name}/full |
|:--------------------|:--------------------------------------------|:------------------------------------------------------|:------|:-----------------|:---------------------|
|                     |                                             |                                                       | ✓     | ✓                | ✓                    |