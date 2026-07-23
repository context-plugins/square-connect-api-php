
# Create Loyalty Reward Request

A request to create a loyalty reward.

## Structure

`CreateLoyaltyRewardRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `idempotencyKey` | `string` | Required | A unique string that identifies this `CreateLoyaltyReward` request.<br>Keys can be any valid string, but must be unique for every request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |
| `reward` | [`LoyaltyReward`](../../doc/models/loyalty-reward.md) | Required | Represents a contract to redeem loyalty points for a [reward tier](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgramRewardTier) discount. Loyalty rewards can be in an ISSUED, REDEEMED, or DELETED state. For more information, see [Redeem loyalty rewards](https://developer.squareup.com/docs/loyalty-api/overview#redeem-loyalty-rewards). | getReward(): LoyaltyReward | setReward(LoyaltyReward reward): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateLoyaltyRewardRequestBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyRewardBuilder;

$createLoyaltyRewardRequest = CreateLoyaltyRewardRequestBuilder::init(
    'idempotency_key2',
    LoyaltyRewardBuilder::init(
        'loyalty_account_id0',
        'reward_tier_id6'
    )
        ->createdAt('created_at8')
        ->id('id0')
        ->orderId('order_id4')
        ->points(222)
        ->redeemedAt('redeemed_at2')
        ->build()
)->build();
```

