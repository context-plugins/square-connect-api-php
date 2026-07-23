
# Redeem Loyalty Reward Response

A response that includes the `LoyaltyEvent` published for redeeming the reward.

## Structure

`RedeemLoyaltyRewardResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `event` | [`?LoyaltyEvent`](../../doc/models/loyalty-event.md) | Optional | Provides information about a loyalty event.<br>For more information, see [Loyalty events](https://developer.squareup.com/docs/loyalty-api/overview/#loyalty-events). | getEvent(): ?LoyaltyEvent | setEvent(?LoyaltyEvent event): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RedeemLoyaltyRewardResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAccumulatePointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventAdjustPointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventCreateRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventDeleteRewardBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventExpirePointsBuilder;
use SquareConnectAPILib\Models\Builders\LoyaltyEventRedeemRewardBuilder;

$redeemLoyaltyRewardResponse = RedeemLoyaltyRewardResponseBuilder::init()
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
            '2020-05-08T21:56:00Z',
            '67377a6e-dbdc-369d-aa16-2e7ed422e71f',
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
                    ->rewardId('9f18ac21-233a-31c3-be77-b45840f5a810')
                    ->build()
            )
            ->build()
    )
    ->build();
```

