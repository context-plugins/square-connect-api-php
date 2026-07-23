
# Order State Enum

The state of the order.

## Enumeration

`OrderStateEnum`

## Fields

| Name | Description |
|  --- | --- |
| `OPEN` | Indicates that the order is open. Open orders can be updated. |
| `COMPLETED` | Indicates that the order is completed. Completed orders are fully paid. This is a terminal state. |
| `CANCELED` | Indicates that the order is canceled. Canceled orders are not paid. This is a terminal state. |

## Example

```php
use SquareConnectAPILib\Models\OrderStateEnum;

$orderState = OrderStateEnum::OPEN;
```

