
# Retrieve Loyalty Reward Response

A response that includes the loyalty reward.

## Structure

`RetrieveLoyaltyRewardResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `reward` | [`?LoyaltyReward`](../../doc/models/loyalty-reward.md) | Optional | Represents a contract to redeem loyalty points for a [reward tier](https://developer.squareup.com/reference/square_2021-08-18/objects/LoyaltyProgramRewardTier) discount. Loyalty rewards can be in an ISSUED, REDEEMED, or DELETED state. For more information, see [Redeem loyalty rewards](https://developer.squareup.com/docs/loyalty-api/overview#redeem-loyalty-rewards). | getReward(): ?LoyaltyReward | setReward(?LoyaltyReward reward): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveLoyaltyRewardResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyRewardBuilder;

$retrieveLoyaltyRewardResponse = RetrieveLoyaltyRewardResponseBuilder::init()
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
            ->createdAt('2020-05-08T21:55:42Z')
            ->id('9f18ac21-233a-31c3-be77-b45840f5a810')
            ->orderId('order_id4')
            ->points(10)
            ->redeemedAt('2020-05-08T21:56:00Z')
            ->status('REDEEMED')
            ->updatedAt('2020-05-08T21:56:00Z')
            ->build()
    )
    ->build();
```

