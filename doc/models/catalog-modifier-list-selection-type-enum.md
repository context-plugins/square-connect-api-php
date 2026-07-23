
# Catalog Modifier List Selection Type Enum

Indicates whether a CatalogModifierList supports multiple selections.

## Enumeration

`CatalogModifierListSelectionTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SINGLE` | Indicates that a CatalogModifierList allows only a<br>single CatalogModifier to be selected. |
| `MULTIPLE` | Indicates that a CatalogModifierList allows multiple<br>CatalogModifier to be selected. |

## Example

```php
use SquareConnectAPILib\Models\CatalogModifierListSelectionTypeEnum;

$catalogModifierListSelectionType = CatalogModifierListSelectionTypeEnum::SINGLE;
```

