
# Order Updated

## Structure

`OrderUpdated`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp for when the order was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `locationId` | `?string` | Optional | The ID of the seller location that this order is associated with. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `orderId` | `?string` | Optional | The order's unique ID. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `state` | `?string` | Optional | The state of the order. | getState(): ?string | setState(?string state): void |
| `updatedAt` | `?string` | Optional | The timestamp for when the order was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |
| `version` | `?int` | Optional | The version number, which is incremented each time an update is committed to the order.<br>Orders that were not created through the API do not include a version number and<br>therefore cannot be updated.<br><br>[Read more about working with versions.](https://developer.squareup.com/docs/orders-api/manage-orders#update-orders) | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderUpdatedBuilder;

$orderUpdated = OrderUpdatedBuilder::init()
    ->createdAt('created_at0')
    ->locationId('location_id6')
    ->orderId('order_id4')
    ->state('state2')
    ->updatedAt('updated_at2')
    ->build();
```

