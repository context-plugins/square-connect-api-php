
# Order Fulfillment State Enum

The current state of this fulfillment.

## Enumeration

`OrderFulfillmentStateEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PROPOSED` | Indicates that the fulfillment has been proposed. |
| `RESERVED` | Indicates that the fulfillment has been reserved. |
| `PREPARED` | Indicates that the fulfillment has been prepared. |
| `COMPLETED` | Indicates that the fulfillment was successfully completed. |
| `CANCELED` | Indicates that the fulfillment was canceled. |
| `FAILED` | Indicates that the fulfillment failed to be completed, but was not explicitly<br>canceled. |

## Example

```php
use SquareConnectAPILib\Models\OrderFulfillmentStateEnum;

$orderFulfillmentState = OrderFulfillmentStateEnum::CANCELED;
```

