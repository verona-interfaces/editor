# Metadata for Players

A editor is a html file. Some metadata should be placed at the beginning of the file. This enables users and developers to decide quickly whether this editor meets the needs or not. Some tools like verona registry or database can categorize the editors easily.

The application (host) using an editor as plug-in should not read these metadata. There are corresponding data as payload of the `voeReadyNotification`.

### Implementation
We use the `data-` syntax to place metadata into
the main html file:

```
    <meta name="application-name" content="iqb verona editor dan"
          data-version="2.0.6"
          data-repository-url="https://github.com/iqb-berlin/verona-editor-dan"
          data-api-version="2.0.0"
          data-not-supported-api-features="report-eager"
          [...]
    />
```

### Metadata in detail
* `content`: application name
* `data-version`: version of the editor
* `data-repository-url`: if published, the url of the code repository should be given to get further information
* `data-api-version`: version of the interface supported by the editor;  This information is also given via `voeReadyNotification`.
* `data-not-supported-api-features`: keys of not supported features separated by space (see below);  This information is also given via `voeReadyNotification`. BTW the documentation of hosts could use this way of declaration for missing features as well.
* `data-supported-unit-definition-types`: Space separated list of keys of unit definition formats supported by the editor. After a '@' char, a version might be added (semver-format, caret and tilde might be used). This information is also given via `voeReadyNotification`.

### List of not supported features
At the time of introduction of player metadata, the list of possibly missing features starts with verona player interface version 2.1:
* `report-eager`: the editor will send data only `on-demand`. So if the host likes to get all data at every change, it must send `voeGetDefinitionRequest`
