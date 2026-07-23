
# Loyalty Reward

Represents a contract to redeem loyalty points for a [reward tier](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgramRewardTier) discount. Loyalty rewards can be in an ISSUED, REDEEMED, or DELETED state. For more information, see [Redeem loyalty rewards](https://developer.squareup.com/docs/loyalty-api/overview#redeem-loyalty-rewards).

## Structure

`LoyaltyReward`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `createdAt` | `?string` | Optional | The timestamp when the reward was created, in RFC 3339 format. | getCreatedAt(): ?string | setCreatedAt(?string createdAt): void |
| `id` | `?string` | Optional | The Square-assigned ID of the loyalty reward.<br><br>**Constraints**: *Maximum Length*: `36` | getId(): ?string | setId(?string id): void |
| `loyaltyAccountId` | `string` | Required | The Square-assigned ID of the [loyalty account](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyAccount) to which the reward belongs.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getLoyaltyAccountId(): string | setLoyaltyAccountId(string loyaltyAccountId): void |
| `orderId` | `?string` | Optional | The Square-assigned ID of the [order](https://developer.squareup.com/reference/square_2021-08-18/objects/Order) to which the reward is attached. | getOrderId(): ?string | setOrderId(?string orderId): void |
| `points` | `?int` | Optional | The number of loyalty points used for the reward.<br><br>**Constraints**: `>= 1` | getPoints(): ?int | setPoints(?int points): void |
| `redeemedAt` | `?string` | Optional | The timestamp when the reward was redeemed, in RFC 3339 format. | getRedeemedAt(): ?string | setRedeemedAt(?string redeemedAt): void |
| `rewardTierId` | `string` | Required | The Square-assigned ID of the [reward tier](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgramRewardTier) used to create the reward.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `36` | getRewardTierId(): string | setRewardTierId(string rewardTierId): void |
| `status` | `?string` | Optional | The status of a loyalty reward. | getStatus(): ?string | setStatus(?string status): void |
| `updatedAt` | `?string` | Optional | The timestamp when the reward was last updated, in RFC 3339 format. | getUpdatedAt(): ?string | setUpdatedAt(?string updatedAt): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\LoyaltyRewardBuilder;

$loyaltyReward = LoyaltyRewardBuilder::init(
    'loyalty_account_id8',
    'reward_tier_id8'
)
    ->createdAt('created_at0')
    ->id('id2')
    ->orderId('order_id6')
    ->points(8)
    ->redeemedAt('redeemed_at4')
    ->build();
```

