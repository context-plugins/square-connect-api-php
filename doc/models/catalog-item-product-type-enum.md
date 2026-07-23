
# Catalog Item Product Type Enum

The type of a CatalogItem. Connect V2 only allows the creation of `REGULAR` or `APPOINTMENTS_SERVICE` items.

## Enumeration

`CatalogItemProductTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `REGULAR` | An ordinary item. |
| `GIFT_CARD` | A Square gift card. |
| `APPOINTMENTS_SERVICE` | A service that can be booked using the Square Appointments app. |

## Example

```php
use SquareConnectAPILib\Models\CatalogItemProductTypeEnum;

$catalogItemProductType = CatalogItemProductTypeEnum::REGULAR;
```

