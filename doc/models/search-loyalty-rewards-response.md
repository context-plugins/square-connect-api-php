
# Search Loyalty Rewards Response

A response that includes the loyalty rewards satisfying the search criteria.

## Structure

`SearchLoyaltyRewardsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent<br>request. If empty, this is the final response. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `rewards` | [`?(LoyaltyReward[])`](../../doc/models/loyalty-reward.md) | Optional | The loyalty rewards that satisfy the search criteria.<br>These are returned in descending order by `updated_at`. | getRewards(): ?array | setRewards(?array rewards): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyRewardsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyRewardBuilder;

$searchLoyaltyRewardsResponse = SearchLoyaltyRewardsResponseBuilder::init()
    ->cursor('cursor2')
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
                ->build()
        ]
    )
    ->rewards(
        [
            LoyaltyRewardBuilder::init(
                '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
                'e1b39225-9da5-43d1-a5db-782cdd8ad94f'
            )
                ->createdAt('2020-05-08T22:00:44Z')
                ->id('d03f79f4-815f-3500-b851-cc1e68a457f9')
                ->orderId('PyATxhYLfsMqpVkcKJITPydgEYfZY')
                ->points(10)
                ->redeemedAt('2020-05-08T22:01:17Z')
                ->status('REDEEMED')
                ->updatedAt('2020-05-08T22:01:17Z')
                ->build(),
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
                ->build(),
            LoyaltyRewardBuilder::init(
                '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
                'e1b39225-9da5-43d1-a5db-782cdd8ad94f'
            )
                ->createdAt('2020-05-01T21:49:54Z')
                ->id('a8f43ebe-2ad6-3001-bdd5-7d7c2da08943')
                ->orderId('5NB69ZNh3FbsOs1ox43bh1xrli6YY')
                ->points(10)
                ->redeemedAt('redeemed_at2')
                ->status('DELETED')
                ->updatedAt('2020-05-08T21:55:10Z')
                ->build(),
            LoyaltyRewardBuilder::init(
                '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
                'e1b39225-9da5-43d1-a5db-782cdd8ad94f'
            )
                ->createdAt('2020-05-01T20:20:37Z')
                ->id('a051254c-f840-3b45-8cf1-50bcd38ff92a')
                ->orderId('LQQ16znvi2VIUKPVhUfJefzr1eEZY')
                ->points(10)
                ->redeemedAt('redeemed_at2')
                ->status('ISSUED')
                ->updatedAt('2020-05-01T20:20:40Z')
                ->build()
        ]
    )
    ->build();
```

