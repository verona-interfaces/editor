[![License: CC0-1.0](https://img.shields.io/badge/License-CC0%201.0-lightgrey.svg)](http://creativecommons.org/publicdomain/zero/1.0/)

# Verona Interfaces: Specification for Editor

In order to understand Verona Interfaces, please go
to [Verona Interfaces Introduction](https://verona-interfaces.github.io)!

A Verona Editor is a Html-file to be loaded into an iframe element of a web application. We call the web application "host". This specification describes the asynchronous communication between a host and the editor.

Read the spec here:
* [Html-Document](https://verona-interfaces.github.io/editor)
* [AsyncApi source yaml](editorapi.yaml)

The editor file must contain of one script tag for metadata as json-ld. The syntax and elements are described [here](https://github.com/verona-interfaces/metadata).

## release notes

### 4.3
* fix variables (must be an array)

### 4.2
* add more possible values of `format` property in `variable info`

### 4.1
* add page identifier to variable info; this might help to locate items
* change handling of variable-list: Separate json schema, tests added

### 4.0
* the editor should send always full payload; in case of performance issues, the editor should use strategies like buffer/delay/debounce; therefor, `voeGetDefinitionRequest` and `definitionReportPolicy` property of `editorConfig` in `voeStartCommand` are removed; properties `unitDefinition` and `unitDefinitionType` in `voeDefinitionChangedNotification` are now required
* added `directDownloadUrl` in `editorConfig` to enable download of additional code or data by the editor
* added dependencies `dependenciesToPlay` and `dependenciesToEdit` to play or to edit the unit in `voeDefinitionChangedNotification`

### 3.0
* specify metadata as json-ld as described [here](https://github.com/verona-interfaces/metadata/#readme); changed `voeReadyNotification` to send this `metadata` instead of `apiVersion`, `notSupportedApiFeatures` and `supportedUnitDefinitionTypes`
* add variable data to `voeDefinitionChangedNotification` to support coding scheme

### 2.0
* almost all operation ids renamed
* metadata introduced
* eager reporting added

## For Contributors
This api is written as [async api](https://www.asyncapi.com/de) yaml file. After committing to main branch, a GitHub action is triggered to build the html page. Don't forget to update the version and the release notes in `README.md`. Then, create an release.

If you like to check the html page before committing to main branch, 

* have an npm/node.js-environment installed
* check out the repo
* run `npm install`
* run the `generate` script in package.json.

After that, you can check `docs/index.html` in a browser. This file will be ignored by git.