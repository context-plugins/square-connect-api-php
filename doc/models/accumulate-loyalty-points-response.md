
# Accumulate Loyalty Points Response

A response containing the resulting loyalty event.

## Structure

`AccumulateLoyaltyPointsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `event` | [`?LoyaltyEvent`](../../doc/models/loyalty-event.md) | Optional | Provides information about a loyalty event.<br>For more information, see [Loyalty events](https://developer.squareup.com/docs/loyalty-api/overview/#loyalty-events). | getEvent(): ?LoyaltyEvent | setEvent(?LoyaltyEvent event): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AccumulateLoyaltyPointsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAccumulatePointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAdjustPointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventCreateRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDeleteRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventExpirePointsBuilder;

$accumulateLoyaltyPointsResponse = AccumulateLoyaltyPointsResponseBuilder::init()
    ->errors(
        [
            ErrorBuilder::init(
                'category8',
                'code8'
            )
                ->detail('detail6')
                ->field('field4')
                ->build()
        ]
    )
    ->event(
        LoyaltyEventBuilder::init(
            '2020-05-08T21:41:12Z',
            'ee46aafd-1af6-3695-a385-276e2ef0be26',
            '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
            'LOYALTY_API',
            'ACCUMULATE_POINTS'
        )
            ->accumulatePoints(
                LoyaltyEventAccumulatePointsBuilder::init()
                    ->loyaltyProgramId('d619f755-2d17-41f3-990d-c04ecedd64dd')
                    ->orderId('RFZfrdtm3mhO1oGzf5Cx7fEMsmGZY')
                    ->points(6)
                    ->build()
            )
            ->adjustPoints(
                LoyaltyEventAdjustPointsBuilder::init(
                    96
                )
                    ->loyaltyProgramId('loyalty_program_id2')
                    ->reason('reason2')
                    ->build()
            )
            ->createReward(
                LoyaltyEventCreateRewardBuilder::init(
                    'loyalty_program_id2',
                    0
                )
                    ->rewardId('reward_id6')
                    ->build()
            )
            ->deleteReward(
                LoyaltyEventDeleteRewardBuilder::init(
                    'loyalty_program_id4',
                    104
                )
                    ->rewardId('reward_id8')
                    ->build()
            )
            ->expirePoints(
                LoyaltyEventExpirePointsBuilder::init(
                    'loyalty_program_id2',
                    0
                )->build()
            )
            ->locationId('P034NEENMD09F')
            ->build()
    )
    ->build();
```

