
# Order Fulfillment Type Enum

The type of fulfillment.

## Enumeration

`OrderFulfillmentTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PICKUP` | A fulfillment to be picked up from a physical [location](https://developer.squareup.com/reference/square_2021-08-18/objects/Location)<br>by a recipient. |
| `SHIPMENT` | A fulfillment to be shipped by a shipping carrier. |

## Example

```php
use SquareConnectAPILib\Models\OrderFulfillmentTypeEnum;

$orderFulfillmentType = OrderFulfillmentTypeEnum::PICKUP;
```

