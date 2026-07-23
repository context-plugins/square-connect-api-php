
# Catalog Custom Attribute Definition Type Enum

Defines the possible types for a custom attribute.

## Enumeration

`CatalogCustomAttributeDefinitionTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `STRING` | A free-form string containing up to 255 characters. |
| `BOOLEAN` | A `true` or `false` value. |
| `NUMBER` | A decimal string representation of a number. Can support up to 5 digits after the decimal point. |
| `SELECTION` | One or more choices from `allowed_selections`. |

## Example

```php
use SquareConnectAPILib\Models\CatalogCustomAttributeDefinitionTypeEnum;

$catalogCustomAttributeDefinitionType = CatalogCustomAttributeDefinitionTypeEnum::STRING;
```

