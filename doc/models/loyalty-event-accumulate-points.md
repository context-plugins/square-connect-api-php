
# Loyalty Event Accumulate Points

Provides metadata when the event `type` is `ACCUMULATE_POINTS`.

## Structure

`LoyaltyEventAccumulatePoints`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyProgramId` | `?string` | Optional | The ID of the [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram).<br><br>**Constraints**: *Maximum Length*: `36` | getLoyaltyProgramId(): ?string | setLoyaltyProgramId(?string loyaltyProgramId): void |
| `orderId` | `?string` | Optional | The ID of the [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) for which the buyer accumulated the points.<br>This field is returned only if the Orders API is used to process orders. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `points` | `?int` | Optional | The number of points accumulated by the event.<br><br>**Constraints**: `>= 1` | getPoints(): ?int | setPoints(?int points): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventAccumulatePointsBuilder;

$loyaltyEventAccumulatePoints = LoyaltyEventAccumulatePointsBuilder::init()
    ->loyaltyProgramId('loyalty_program_id0')
    ->orderId('order_id4')
    ->points(170)
    ->build();
```

