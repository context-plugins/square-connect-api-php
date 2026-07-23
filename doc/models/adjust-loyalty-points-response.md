
# Adjust Loyalty Points Response

A response that includes the loyalty event that
resulted from the successful API call.

## Structure

`AdjustLoyaltyPointsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `event` | [`?LoyaltyEvent`](../../doc/models/loyalty-event.md) | Optional | Provides information about a loyalty event.<br>For more information, see [Loyalty events](https://developer.squareup.com/docs/loyalty-api/overview/#loyalty-events). | getEvent(): ?LoyaltyEvent | setEvent(?LoyaltyEvent event): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\AdjustLoyaltyPointsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAccumulatePointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAdjustPointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventCreateRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDeleteRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventExpirePointsBuilder;

$adjustLoyaltyPointsResponse = AdjustLoyaltyPointsResponseBuilder::init()
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
    ->event(
        LoyaltyEventBuilder::init(
            '2020-05-08T21:42:32Z',
            '613a6fca-8d67-39d0-bad2-3b4bc45c8637',
            '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
            'LOYALTY_API',
            'ADJUST_POINTS'
        )
            ->accumulatePoints(
                LoyaltyEventAccumulatePointsBuilder::init()
                    ->loyaltyProgramId('loyalty_program_id8')
                    ->orderId('order_id8')
                    ->points(118)
                    ->build()
            )
            ->adjustPoints(
                LoyaltyEventAdjustPointsBuilder::init(
                    10
                )
                    ->loyaltyProgramId('d619f755-2d17-41f3-990d-c04ecedd64dd')
                    ->reason('Complimentary points')
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
            )->build()
    )->build();
```

