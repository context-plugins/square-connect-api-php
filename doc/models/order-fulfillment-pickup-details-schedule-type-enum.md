
# Order Fulfillment Pickup Details Schedule Type Enum

The schedule type of the pickup fulfillment.

## Enumeration

`OrderFulfillmentPickupDetailsScheduleTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `SCHEDULED` | Indicates that the fulfillment will be picked up at a scheduled pickup time. |
| `ASAP` | Indicates that the fulfillment will be picked up as soon as possible and<br>should be prepared immediately. |

## Example

```php
use SquareConnectAPILib\Models\OrderFulfillmentPickupDetailsScheduleTypeEnum;

$orderFulfillmentPickupDetailsScheduleType = OrderFulfillmentPickupDetailsScheduleTypeEnum::SCHEDULED;
```

