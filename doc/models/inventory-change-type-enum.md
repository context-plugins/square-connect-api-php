
# Inventory Change Type Enum

Indicates how the inventory change was applied to a tracked product quantity.

## Enumeration

`InventoryChangeTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PHYSICAL_COUNT` | The change occurred as part of a physical count update. |
| `ADJUSTMENT` | The change occurred as part of the normal lifecycle of goods<br>(e.g., as an inventory adjustment). |
| `TRANSFER` | The change occurred as part of an inventory transfer. |

## Example

```php
use SquareConnectAPILib\Models\InventoryChangeTypeEnum;

$inventoryChangeType = InventoryChangeTypeEnum::ADJUSTMENT;
```

