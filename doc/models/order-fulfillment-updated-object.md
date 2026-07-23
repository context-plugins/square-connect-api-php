
# Order Fulfillment Updated Object

## Structure

`OrderFulfillmentUpdatedObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderFulfillmentUpdated` | [`?OrderFulfillmentUpdated`](../../doc/models/order-fulfillment-updated.md) | Optional | - | getOrderFulfillmentUpdated(): ?OrderFulfillmentUpdated | setOrderFulfillmentUpdated(?OrderFulfillmentUpdated orderFulfillmentUpdated): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderFulfillmentUpdatedObjectBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentUpdatedBuilder;
use SquareConnectAPILib\Models\Builders\OrderFulfillmentUpdatedUpdateBuilder;

$orderFulfillmentUpdatedObject = OrderFulfillmentUpdatedObjectBuilder::init()
    ->orderFulfillmentUpdated(
        OrderFulfillmentUpdatedBuilder::init()
            ->createdAt('created_at2')
            ->fulfillmentUpdate(
                [
                    OrderFulfillmentUpdatedUpdateBuilder::init()
                        ->fulfillmentUid('fulfillment_uid2')
                        ->newState('new_state8')
                        ->oldState('old_state8')
                        ->build()
                ]
            )
            ->locationId('location_id8')
            ->orderId('order_id8')
            ->state('state0')
            ->build()
    )
    ->build();
```

