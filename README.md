[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
![GitHub package.json version](https://img.shields.io/github/package-json/v/verona-interfaces/editor)

# Verona Interfaces: Specification for Editor

In order to understand Verona Interfaces, please go
to [Verona Interfaces Introduction](https://github.com/verona-interfaces/introduction)!

A Verona Editor is a Html-file to be loaded into an iframe element of a web application. We call the web application "host". This specification describes the asynchronous communication between a host and the editor.

Read the spec here:
* [Html-Document](https://verona-interfaces.github.io/editor)
* [Markdown-Document](docs/asyncapi.md)
* [AsyncApi source yaml](api/editorapi.yaml)

The editor file must contain of one script tag for metadata as json-ld. The syntax and elements are described [here](https://github.com/verona-interfaces/metadata).

## release notes
### 4.0
* the editor should send always full payload; in case of performance issues, the editor should use strategies like buffer/delay/debounce; therefor, `voeGetDefinitionRequest` and `definitionReportPolicy` property of `editorConfig` in `voeStartCommand` are removed
* added `directDownloadUrl` in `editorConfig` to enable download of additional code or data by the editor

### 3.0
* specify metadata as json-ld as described [here](https://github.com/verona-interfaces/metadata/#readme); changed `voeReadyNotification` to send this `metadata` instead of `apiVersion`, `notSupportedApiFeatures` and `supportedUnitDefinitionTypes`
* add variable data to `voeDefinitionChangedNotification` to support coding scheme

### 2.0
* almost all operation ids renamed
* metadata introduced
* eager reporting added

## For Contributors
The api is written as [async api](https://www.asyncapi.com) yaml file. After editing, we create markdown and html files for better reading.

To ease that post processing, we use [node.js](https://nodejs.org). The repo contains a package.json. By running `npm install` you get the tool `@asyncapi/generator` and two templates. Run `npm run ag` to recreate html and markdown representations of the api.
