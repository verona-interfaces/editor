# Doc for some parameters of variable-list

## type

| Key       | Description             |
| :------------- |:------------------------|
| `string` | Text                    |
| `integer` | integer                 |
| `number` | float number / decimals |
| `boolean` | true / false |
| `attachment` | key to get a media file captured during the test as response |

## format

| Key       | Description                                                |
| :------------- |:-----------------------------------------------------------|
| `text-selection` | Used in IQB-Player aspect: `<start-pos>-<end-pos>-<color>` |
| `image` | image file                                                 |
| `capture-image` | image file, taken as picture by the test proctor           |
| `audio` | not specified yet |
| `ggb-file` | definition for GeoGebra |
| `ggb-variable` | extracted variable value from GeoGebra |
| `non-negative` | value >= 0 |
| `latex` | math formula as latex expression |
| `math-ml` | html with embedded math formula in MathML syntax |
| `math-table` |  Used in IQB-Player aspect: JSON object with multiple values |


