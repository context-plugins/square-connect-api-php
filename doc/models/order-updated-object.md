
# Order Updated Object

## Structure

`OrderUpdatedObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderUpdated` | [`?OrderUpdated`](../../doc/models/order-updated.md) | Optional | - | getOrderUpdated(): ?OrderUpdated | setOrderUpdated(?OrderUpdated orderUpdated): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderUpdatedObjectBuilder;
use SquareConnectAPILib\Models\Builders\OrderUpdatedBuilder;

$orderUpdatedObject = OrderUpdatedObjectBuilder::init()
    ->orderUpdated(
        OrderUpdatedBuilder::init()
            ->createdAt('created_at2')
            ->locationId('location_id4')
            ->orderId('order_id6')
            ->state('state4')
            ->updatedAt('updated_at4')
            ->build()
    )
    ->build();
```

