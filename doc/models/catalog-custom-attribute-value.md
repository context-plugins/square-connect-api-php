
# Catalog Custom Attribute Value

An instance of a custom attribute. Custom attributes can be defined and
added to `ITEM` and `ITEM_VARIATION` type catalog objects.
[Read more about custom attributes](https://developer.squareup.com/docs/catalog-api/add-custom-attributes).

## Structure

`CatalogCustomAttributeValue`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `booleanValue` | `?bool` | Optional | A `true` or `false` value. Populated if `type` = `BOOLEAN`. | getBooleanValue(): ?bool | setBooleanValue(?bool booleanValue): void |
| `customAttributeDefinitionId` | `?string` | Optional | __Read-only.__ The id of the [CatalogCustomAttributeDefinition](https://developer.squareup.com/reference/square_2021-08-18/objects/CatalogCustomAttributeDefinition) this value belongs to. | getCustomAttributeDefinitionId(): ?string | setCustomAttributeDefinitionId(?string customAttributeDefinitionId): void |
| `key` | `?string` | Optional | __Read-only.__ A copy of key from the associated `CatalogCustomAttributeDefinition`. | getKey(): ?string | setKey(?string key): void |
| `name` | `?string` | Optional | The name of the custom attribute. | getName(): ?string | setName(?string name): void |
| `numberValue` | `?string` | Optional | Populated if `type` = `NUMBER`. Contains a string<br>representation of a decimal number, using a `.` as the decimal separator. | getNumberValue(): ?string | setNumberValue(?string numberValue): void |
| `selectionUidValues` | `?(string[])` | Optional | One or more choices from `allowed_selections`. Populated if `type` = `SELECTION`. | getSelectionUidValues(): ?array | setSelectionUidValues(?array selectionUidValues): void |
| `stringValue` | `?string` | Optional | The string value of the custom attribute.  Populated if `type` = `STRING`. | getStringValue(): ?string | setStringValue(?string stringValue): void |
| `type` | `?string` | Optional | __Read-only.__ A copy of type from the associated `CatalogCustomAttributeDefinition`. | getType(): ?string | setType(?string type): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CatalogCustomAttributeValueBuilder;

$catalogCustomAttributeValue = CatalogCustomAttributeValueBuilder::init()
    ->booleanValue(false)
    ->customAttributeDefinitionId('custom_attribute_definition_id4')
    ->key('key6')
    ->name('name6')
    ->numberValue('number_value6')
    ->build();
```

