
# Loyalty Event Order Filter

Filter events by the order associated with the event.

## Structure

`LoyaltyEventOrderFilter`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `orderId` | `string` | Required | The ID of the [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) associated with the event.<br><br>**Constraints**: *Minimum Length*: `1` | getOrderId(): string | setOrderId(string orderId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventOrderFilterBuilder;

$loyaltyEventOrderFilter = LoyaltyEventOrderFilterBuilder::init(
    'order_id2'
)->build();
```

