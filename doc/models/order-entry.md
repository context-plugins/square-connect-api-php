
# Order Entry

A lightweight description of an [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) that is returned when
`returned_entries` is `true` on a [SearchOrdersRequest](https://developer.squareup.com/reference/square_2021-08-18/orders-api/search-orders).

## Structure

`OrderEntry`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `locationId` | `?string` | Optional | The location ID the order belongs to. | getLocationId(): ?string | setLocationId(?string locationId): void |
| `orderId` | `?string` | Optional | The ID of the order. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `version` | `?int` | Optional | The version number, which is incremented each time an update is committed to the order.<br>Orders that were not created through the API do not include a version number and<br>therefore cannot be updated.<br><br>[Read more about working with versions.](https://developer.squareup.com/docs/orders-api/manage-orders#update-orders) | getVersion(): ?int | setVersion(?int version): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\OrderEntryBuilder;

$orderEntry = OrderEntryBuilder::init()
    ->locationId('location_id4')
    ->orderId('order_id4')
    ->version(86)
    ->build();
```

