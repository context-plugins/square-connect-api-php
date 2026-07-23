
# Create Loyalty Reward Response

A response that includes the loyalty reward created.

## Structure

`CreateLoyaltyRewardResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `reward` | [`?LoyaltyReward`](../../doc/models/loyalty-reward.md) | Optional | Represents a contract to redeem loyalty points for a [reward tier](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgramRewardTier) discount. Loyalty rewards can be in an ISSUED, REDEEMED, or DELETED state. For more information, see [Redeem loyalty rewards](https://developer.squareup.com/docs/loyalty-api/overview#redeem-loyalty-rewards). | getReward(): ?LoyaltyReward | setReward(?LoyaltyReward reward): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateLoyaltyRewardResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyRewardBuilder;

$createLoyaltyRewardResponse = CreateLoyaltyRewardResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build(),
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->reward(
        LoyaltyRewardBuilder::init(
            '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
            'e1b39225-9da5-43d1-a5db-782cdd8ad94f'
        )
            ->createdAt('2020-05-01T21:49:54Z')
            ->id('a8f43ebe-2ad6-3001-bdd5-7d7c2da08943')
            ->orderId('RFZfrdtm3mhO1oGzf5Cx7fEMsmGZY')
            ->points(10)
            ->redeemedAt('redeemed_at2')
            ->status('ISSUED')
            ->updatedAt('2020-05-01T21:49:54Z')
            ->build()
    )
    ->build();
```

