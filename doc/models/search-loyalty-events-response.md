
# Search Loyalty Events Response

A response that contains loyalty events that satisfy the search
criteria, in order by the `created_at` date.

## Structure

`SearchLoyaltyEventsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | The pagination cursor to be used in a subsequent<br>request. If empty, this is the final response.<br>For more information,<br>see [Pagination](https://developer.squareup.com/docs/basics/api101/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `events` | [`?(LoyaltyEvent[])`](../../doc/models/loyalty-event.md) | Optional | The loyalty events that satisfy the search criteria. | getEvents(): ?array | setEvents(?array events): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchLoyaltyEventsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAccumulatePointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAdjustPointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventCreateRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDeleteRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventExpirePointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventRedeemRewardBuilder;

$searchLoyaltyEventsResponse = SearchLoyaltyEventsResponseBuilder::init()
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
    ->events(
        [
            LoyaltyEventBuilder::init(
                '2020-05-08T22:01:30Z',
                'c27c8465-806e-36f2-b4b3-71f5887b5ba8',
                '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
                'LOYALTY_API',
                'ACCUMULATE_POINTS'
            )
                ->accumulatePoints(
                    LoyaltyEventAccumulatePointsBuilder::init()
                        ->loyaltyProgramId('d619f755-2d17-41f3-990d-c04ecedd64dd')
                        ->orderId('PyATxhYLfsMqpVkcKJITPydgEYfZY')
                        ->points(5)
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
                ->build(),
            LoyaltyEventBuilder::init(
                '2020-05-08T22:01:15Z',
                'e4a5cbc3-a4d0-3779-98e9-e578885d9430',
                '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
                'LOYALTY_API',
                'REDEEM_REWARD'
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
                ->redeemReward(
                    LoyaltyEventRedeemRewardBuilder::init(
                        'd619f755-2d17-41f3-990d-c04ecedd64dd'
                    )
                        ->orderId('PyATxhYLfsMqpVkcKJITPydgEYfZY')
                        ->rewardId('d03f79f4-815f-3500-b851-cc1e68a457f9')
                        ->build()
                )
                ->build(),
            LoyaltyEventBuilder::init(
                '2020-05-08T22:00:44Z',
                '5e127479-0b03-3671-ab1e-15faea8b7188',
                '5adcb100-07f1-4ee7-b8c6-6bb9ebc474bd',
                'LOYALTY_API',
                'CREATE_REWARD'
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
                        96
                    )
                        ->loyaltyProgramId('loyalty_program_id2')
                        ->reason('reason2')
                        ->build()
                )
                ->createReward(
                    LoyaltyEventCreateRewardBuilder::init(
                        'd619f755-2d17-41f3-990d-c04ecedd64dd',
                        -10
                    )
                        ->rewardId('d03f79f4-815f-3500-b851-cc1e68a457f9')
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
        ]
    )->build();
```

