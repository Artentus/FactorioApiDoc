# ModInfo JSON Object

A `ModInfo` object contains information about a mod.  
It is returned either directly by [requesting info about a mod](../#single-mod-endpoint)
or in a list by [requesting a list of mods](../#mods-endpoint).

### Attributes

Depending on which endpoint was used, a `ModInfo` object can contain different attributes:

| Key             | Type                          | Description                                                       | /mods | /mods/{mod-name} | /mod/{mod-name}/full |
|:----------------|:------------------------------|:------------------------------------------------------------------|:------|:-----------------|:---------------------|
| name            | String                        | The name of the mod                                               | ✓     | ✓                | ✓                    |
| title           | String                        | A more human readable name of the mod                             | ✓     | ✓                | ✓                    |
| owner           | String                        | The author of the mod                                             | ✓     | ✓                | ✓                    |
| summary         | String                        | A short summary of the mod                                        | ✓     | ✓                | ✓                    |
| downloads_count | Integer                       | The number of times this mod has been downloaded                  | ✓     | ✓                | ✓                    |
| latest_release  | [ModRelease]('./modrelease)   | The latest release of the mod                                     | ✓     |                  |                      |
| releases        | [ModRelease[]]('./modrelease) | An array of releases of the mod                                   |       | ✓                | ✓                    |
| changelog       | String                        | Changelog of the mod                                              |       |                  | ✓                    |
| created_at      | String                        | ISO 8601 string for when the mod was created                      |       |                  | ✓                    |
| description     | String                        | A longer description of the mod                                   |       |                  | ✓                    |
| faq             | String                        | TODO: Frequently asked questions??? Appears to be null usually... |       |                  | ✓                    |
| github_path     | String                        | Path to the GitHub repository, relative to https://github.com/    |       |                  | ✓                    |
| homepage        | String                        | URL of the homepage of the mod                                    |       |                  | ✓                    |
| license         | [Licence]('./license')        | The license of the mod                                            |       |                  | ✓                    |
| tag             | [Tag]('./tag')                | The tag of the mod                                                |       |                  | ✓                    |
| updated_at      | String                        | ISO 6801 string for when the mod was updated                      |       |                  | ✓                    |
