
# Loyalty Event Create Reward

Provides metadata when the event `type` is `CREATE_REWARD`.

## Structure

`LoyaltyEventCreateReward`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyProgramId` | `string` | Required | The ID of the [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getLoyaltyProgramId(): string | setLoyaltyProgramId(string loyaltyProgramId): void |
| `points` | `int` | Required | The loyalty points used to create the reward.<br><br>**Constraints**: `<= 0` | getPoints(): int | setPoints(int points): void |
| `rewardId` | `?string` | Optional | The Square-assigned ID of the created [loyalty reward](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyReward).<br>This field is returned only if the event source is `LOYALTY_API`.<br><br>**Constraints**: *Maximum Length*: `36` | getRewardId(): ?string | setRewardId(?string rewardId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventCreateRewardBuilder;

$loyaltyEventCreateReward = LoyaltyEventCreateRewardBuilder::init(
    'loyalty_program_id2',
    0
)
    ->rewardId('reward_id6')
    ->build();
```

