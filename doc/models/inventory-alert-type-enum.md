
# Inventory Alert Type Enum

Indicates whether Square should alert the merchant when the inventory quantity of a CatalogItemVariation is low.

## Enumeration

`InventoryAlertTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `NONE` | The variation does not display an alert. |
| `LOW_QUANTITY` | The variation generates an alert when its quantity is low. |

## Example

```php
use SquareConnectAPILib\Models\InventoryAlertTypeEnum;

$inventoryAlertType = InventoryAlertTypeEnum::NONE;
```

