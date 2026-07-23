
# Loyalty Event Expire Points

Provides metadata when the event `type` is `EXPIRE_POINTS`.

## Structure

`LoyaltyEventExpirePoints`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyProgramId` | `string` | Required | The Square-assigned ID of the [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getLoyaltyProgramId(): string | setLoyaltyProgramId(string loyaltyProgramId): void |
| `points` | `int` | Required | The number of points expired.<br><br>**Constraints**: `<= 0` | getPoints(): int | setPoints(int points): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventExpirePointsBuilder;

$loyaltyEventExpirePoints = LoyaltyEventExpirePointsBuilder::init(
    'loyalty_program_id8',
    0
)->build();
```

