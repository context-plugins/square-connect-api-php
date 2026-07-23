
# List Gift Card Activities Response

A response that contains one or more `GiftCardActivity`. The response might contain a set of `Error` objects
if the request resulted in errors.

## Structure

`ListGiftCardActivitiesResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | When a response is truncated, it includes a cursor that you can use in a<br>subsequent request to fetch the next set of activities. If empty, this is<br>the final response. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `giftCardActivities` | [`?(GiftCardActivity[])`](../../doc/models/gift-card-activity.md) | Optional | Gift card activities retrieved. | getGiftCardActivities(): ?array | setGiftCardActivities(?array giftCardActivities): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListGiftCardActivitiesResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\GiftCardActivityActivateBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustDecrementBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustIncrementBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityBlockBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityClearBalanceBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityRedeemBuilder;

$listGiftCardActivitiesResponse = ListGiftCardActivitiesResponseBuilder::init()
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
    ->giftCardActivities(
        [
            GiftCardActivityBuilder::init(
                '81FN9BNFZTKS4',
                ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
            )
                ->activateActivityDetails(
                    GiftCardActivityActivateBuilder::init()
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(186)
                                ->currency('currency8')
                                ->build()
                        )
                        ->buyerPaymentInstrumentIds(
                            [
                                'buyer_payment_instrument_ids6',
                                'buyer_payment_instrument_ids7'
                            ]
                        )
                        ->lineItemUid('line_item_uid0')
                        ->orderId('order_id4')
                        ->referenceId('reference_id8')
                        ->build()
                )
                ->adjustDecrementActivityDetails(
                    GiftCardActivityAdjustDecrementBuilder::init(
                        MoneyBuilder::init()
                            ->amount(186)
                            ->currency('currency8')
                            ->build(),
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->adjustIncrementActivityDetails(
                    GiftCardActivityAdjustIncrementBuilder::init(
                        MoneyBuilder::init()
                            ->amount(186)
                            ->currency('currency8')
                            ->build(),
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->blockActivityDetails(
                    GiftCardActivityBlockBuilder::init(
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->clearBalanceActivityDetails(
                    GiftCardActivityClearBalanceBuilder::init(
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->createdAt('2021-06-02T22:26:38.000Z')
                ->giftCardBalanceMoney(
                    MoneyBuilder::init()
                        ->amount(700)
                        ->currency('USD')
                        ->build()
                )
                ->giftCardGan('7783320002929081')
                ->giftCardId('gftc:6d55a72470d940c6ba09c0ab8ad08d20')
                ->id('gcact_897698f894b44b3db46c6147e26a0e19')
                ->redeemActivityDetails(
                    GiftCardActivityRedeemBuilder::init(
                        MoneyBuilder::init()
                            ->amount(300)
                            ->currency('USD')
                            ->build()
                    )->build()
                )->build(),
            GiftCardActivityBuilder::init(
                '81FN9BNFZTKS4',
                ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
            )
                ->activateActivityDetails(
                    GiftCardActivityActivateBuilder::init()
                        ->amountMoney(
                            MoneyBuilder::init()
                                ->amount(1000)
                                ->currency('USD')
                                ->build()
                        )
                        ->lineItemUid('eIWl7X0nMuO9Ewbh0ChIx')
                        ->orderId('jJNGHm4gLI6XkFbwtiSLqK72KkAZY')
                        ->build()
                )
                ->adjustDecrementActivityDetails(
                    GiftCardActivityAdjustDecrementBuilder::init(
                        MoneyBuilder::init()
                            ->amount(186)
                            ->currency('currency8')
                            ->build(),
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->adjustIncrementActivityDetails(
                    GiftCardActivityAdjustIncrementBuilder::init(
                        MoneyBuilder::init()
                            ->amount(186)
                            ->currency('currency8')
                            ->build(),
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->blockActivityDetails(
                    GiftCardActivityBlockBuilder::init(
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->clearBalanceActivityDetails(
                    GiftCardActivityClearBalanceBuilder::init(
                        ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
                    )->build()
                )
                ->createdAt('2021-05-20T22:26:54.000Z')
                ->giftCardBalanceMoney(
                    MoneyBuilder::init()
                        ->amount(1000)
                        ->currency('USD')
                        ->build()
                )
                ->giftCardGan('7783320002929081')
                ->giftCardId('gftc:6d55a72470d940c6ba09c0ab8ad08d20')
                ->id('gcact_b968ebfc7d46437b945be7b9e09123b4')
                ->build()
        ]
    )
    ->build();
```

