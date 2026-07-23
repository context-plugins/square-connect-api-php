
# Catalog Quick Amount Type Enum

Determines the type of a specific Quick Amount.

## Enumeration

`CatalogQuickAmountTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `QUICK_AMOUNT_TYPE_MANUAL` | Quick Amount is created manually by the seller. |
| `QUICK_AMOUNT_TYPE_AUTO` | Quick Amount is generated automatically by machine learning algorithms. |

## Example

```php
use SquareConnectAPILib\Models\CatalogQuickAmountTypeEnum;

$catalogQuickAmountType = CatalogQuickAmountTypeEnum::QUICK_AMOUNT_TYPE_MANUAL;
```

