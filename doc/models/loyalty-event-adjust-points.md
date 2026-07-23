
# Loyalty Event Adjust Points

Provides metadata when the event `type` is `ADJUST_POINTS`.

## Structure

`LoyaltyEventAdjustPoints`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyProgramId` | `?string` | Optional | The Square-assigned ID of the [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram).<br><br>**Constraints**: *Maximum Length*: `36` | getLoyaltyProgramId(): ?string | setLoyaltyProgramId(?string loyaltyProgramId): void |
| `points` | `int` | Required | The number of points added or removed. | getPoints(): int | setPoints(int points): void |
| `reason` | `?string` | Optional | The reason for the adjustment of points. | getReason(): ?string | setReason(?string reason): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventAdjustPointsBuilder;

$loyaltyEventAdjustPoints = LoyaltyEventAdjustPointsBuilder::init(
    50
)
    ->loyaltyProgramId('loyalty_program_id8')
    ->reason('reason4')
    ->build();
```

