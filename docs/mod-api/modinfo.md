# ModInfo JSON Object

A `ModInfo` object contains information about a mod.  
It is returned either directly by [requesting info about a mod](../#single-mod-endpoint)
or in a list by [requesting a list of mods](../#mods-endpoint).

### Attributes

Depending on which endpoint was used, a `ModInfo` object can contain different attributes:

| Key             | Type                          | Description                                                                                    | /mods | /mods/{mod-name} | /mod/{mod-name}/full |
|:----------------|:------------------------------|:-----------------------------------------------------------------------------------------------|:------|:-----------------|:---------------------|
| name            | String                        | Unique name of the mod                                                                         | ✓     | ✓                | ✓                    |
| title           | String                        | Friendly name of the mod                                                                       | ✓     | ✓                | ✓                    |
| owner           | String                        | Author of the mod                                                                              | ✓     | ✓                | ✓                    |
| summary         | String                        | A short summary of the mod                                                                     | ✓     | ✓                | ✓                    |
| downloads_count | Integer                       | The number of times this mod has been downloaded                                               | ✓     | ✓                | ✓                    |
| latest_release  | [ModRelease](../modrelease)   | Latest release of the mod                                                                  | ✓     |                  |                      |
| releases        | [ModRelease[]](../modrelease) | An array of releases of the mod                                                                |       | ✓                | ✓                    |
| changelog       | String                        | Changelog of the mod, formatted in [Markdown](https://en.wikipedia.org/wiki/Markdown)          |       |                  | ✓                    |
| created_at      | String                        | Creation date of the mod, formatted in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)      |       |                  | ✓                    |
| description     | String                        | A long description of the mod, formatted in [Markdown](https://en.wikipedia.org/wiki/Markdown) |       |                  | ✓                    |
| faq             | String                        | Optional FAQ of the mod, formatted in [Markdown](https://en.wikipedia.org/wiki/Markdown)       |       |                  | ✓                    |
| github_path     | String                        | Path to the GitHub repository, relative to https://github.com/                                 |       |                  | ✓                    |
| homepage        | String                        | URL of the homepage of the mod                                                                 |       |                  | ✓                    |
| license         | [Licence](../license)         | License of the mod                                                                         |       |                  | ✓                    |
| tag             | [Tag](../tag)                 | Tag of the mod                                                                             |       |                  | ✓                    |
| updated_at      | String                        | Last update date of the mod, formatted in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)   |       |                  | ✓                    |
