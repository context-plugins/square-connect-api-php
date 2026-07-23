
# Loyalty Event Redeem Reward

Provides metadata when the event `type` is `REDEEM_REWARD`.

## Structure

`LoyaltyEventRedeemReward`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `loyaltyProgramId` | `string` | Required | The ID of the [loyalty program](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgram).<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getLoyaltyProgramId(): string | setLoyaltyProgramId(string loyaltyProgramId): void |
| `orderId` | `?string` | Optional | The ID of the [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) that redeemed the reward.<br>This field is returned only if the Orders API is used to process orders. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `rewardId` | `?string` | Optional | The ID of the redeemed [loyalty reward](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyReward).<br>This field is returned only if the event source is `LOYALTY_API`.<br><br>**Constraints**: *Maximum Length*: `36` | getRewardId(): ?string | setRewardId(?string rewardId): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyEventRedeemRewardBuilder;

$loyaltyEventRedeemReward = LoyaltyEventRedeemRewardBuilder::init(
    'loyalty_program_id0'
)
    ->orderId('order_id4')
    ->rewardId('reward_id4')
    ->build();
```

