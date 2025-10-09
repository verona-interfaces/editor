Since version 4.6, every new release is published with a tag. This tag carries release notes, so there is no need to add release notes to the README.md anymore. The list below is the copy of old release notes.

### 4.5
* add `no-value`, `json` and `coded` to variable types (apply [variable-info](https://github.com/verona-interfaces/variable-info) v1.3)

### 4.4
* add `alias` to variable
* add `role` to `editorConfig`
* do not allow additional properties anymore

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