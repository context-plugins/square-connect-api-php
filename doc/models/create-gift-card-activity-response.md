
# Create Gift Card Activity Response

A response that contains a `GiftCardActivity` that was created.
The response might contain a set of `Error` objects if the request resulted in errors.

## Structure

`CreateGiftCardActivityResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `giftCardActivity` | [`?GiftCardActivity`](../../doc/models/gift-card-activity.md) | Optional | Represents an action performed on a gift card that affects its state or balance. | getGiftCardActivity(): ?GiftCardActivity | setGiftCardActivity(?GiftCardActivity giftCardActivity): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateGiftCardActivityResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\GiftCardActivityActivateBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustDecrementBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustIncrementBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityBlockBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityClearBalanceBuilder;

$createGiftCardActivityResponse = CreateGiftCardActivityResponseBuilder::init()
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
    ->giftCardActivity(
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
                    ->buyerPaymentInstrumentIds(
                        [
                            'buyer_payment_instrument_ids6',
                            'buyer_payment_instrument_ids7'
                        ]
                    )
                    ->lineItemUid('eIWl7X0nMuO9Ewbh0ChIx')
                    ->orderId('jJNGHm4gLI6XkFbwtiSLqK72KkAZY')
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
            ->createdAt('2021-05-20T22:26:54.000Z')
            ->giftCardBalanceMoney(
                MoneyBuilder::init()
                    ->amount(1000)
                    ->currency('USD')
                    ->build()
            )
            ->giftCardGan('7783320002929081')
            ->giftCardId('gftc:6d55a72470d940c6ba09c0ab8ad08d20')
            ->id('gcact_c8f8cbf1f24b448d8ecf39ed03f97864')
            ->build()
    )
    ->build();
```

