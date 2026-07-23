
# Catalog Custom Attribute Definition Selection Config Custom Attribute Selection

A named selection for this `SELECTION`-type custom attribute definition.

## Structure

`CatalogCustomAttributeDefinitionSelectionConfigCustomAttributeSelection`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `name` | `string` | Required | Selection name, unique within `allowed_selections`.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `255` | getName(): string | setName(string name): void |
| `uid` | `?string` | Optional | Unique ID set by Square. | getUid(): ?string | setUid(?string uid): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeDefinitionSelectionConfigCustomAttributeSelectionBuilder;

$catalogCustomAttributeDefinitionSelectionConfigCustomAttributeSelection = CatalogCustomAttributeDefinitionSelectionConfigCustomAttributeSelectionBuilder::init(
    'name2'
)
    ->uid('uid2')
    ->build();
```

