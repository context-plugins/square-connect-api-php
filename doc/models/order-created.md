
# Order Created

## Structure

`OrderCreated`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp for when the order was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `locationId` | `?string` | Optional | The ID of the seller location that this order is associated with. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `orderId` | `?string` | Optional | The order's unique ID. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `state` | `?string` | Optional | The state of the order. | getState(): ?string | setState(?string state): void |
| `version` | `?int` | Optional | The version number, which is incremented each time an update is committed to the order.<br>Orders that were not created through the API do not include a version number and<br>therefore cannot be updated.<br><br>[Read more about working with versions.](https://developer.squareup.com/docs/orders-api/manage-orders#update-orders) | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderCreatedBuilder;

$orderCreated = OrderCreatedBuilder::init()
    ->createdAt('created_at2')
    ->locationId('location_id8')
    ->orderId('order_id8')
    ->state('state0')
    ->version(230)
    ->build();
```

