
# Catalog Pricing Type Enum

Indicates whether the price of a CatalogItemVariation should be entered manually at the time of sale.

## Enumeration

`CatalogPricingTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `FIXED_PRICING` | The catalog item variation's price is fixed. |
| `VARIABLE_PRICING` | The catalog item variation's price is entered at the time of sale. |

## Example

```php
use SquareConnectAPILib\Models\CatalogPricingTypeEnum;

$catalogPricingType = CatalogPricingTypeEnum::FIXED_PRICING;
```

