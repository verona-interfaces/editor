[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
# Verona Interfaces: Specification for Editor

In order to understand Verona Interfaces, please go
to [Verona Interfaces Introduction](https://github.com/verona-interfaces/introduction)!

**Editor** in the context of Verona Interfaces is a module for 
authoring a unit. It is used in applications like task pools or item banks.

Texts about Editor API:
* API
  * [markdown](docs/asyncapi.md)
  * [shiny html](https://verona-interfaces.github.io/editor)
* see also: [editor metadata](api/editor-metadata.md)


## release notes
### 2.0
* almost all operation ids renamed
* metadata introduced
* eager reporting added

## For Contributors
The api is written as [async api](https://www.asyncapi.com) yaml file. After editing, we create markdown and html files for better reading.

To ease that post processing, we use [node.js](https://nodejs.org). The repo contains a package.json. By running `npm install` you get the tool `@asyncapi/generator` and two templates. Run `npm run ag` to recreate html and markdown representations of the api.
