
# Order Created Object

## Structure

`OrderCreatedObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderCreated` | [`?OrderCreated`](../../doc/models/order-created.md) | Optional | - | getOrderCreated(): ?OrderCreated | setOrderCreated(?OrderCreated orderCreated): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderCreatedObjectBuilder;
use SquareConnectAPILib\Models\Builders\OrderCreatedBuilder;

$orderCreatedObject = OrderCreatedObjectBuilder::init()
    ->orderCreated(
        OrderCreatedBuilder::init()
            ->createdAt('created_at2')
            ->locationId('location_id8')
            ->orderId('order_id8')
            ->state('state0')
            ->version(170)
            ->build()
    )
    ->build();
```

