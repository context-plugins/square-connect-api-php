
# Create Gift Card Activity Request

A request to create a gift card activity.

## Structure

`CreateGiftCardActivityRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `giftCardActivity` | [`GiftCardActivity`](../../doc/models/gift-card-activity.md) | Required | Represents an action performed on a gift card that affects its state or balance. | getGiftCardActivity(): GiftCardActivity | setGiftCardActivity(GiftCardActivity giftCardActivity): void |
| `idempotencyKey` | `string` | Required | A unique string that identifies the `CreateGiftCardActivity` request.<br><br>**Constraints**: *Minimum Length*: `1`, *Maximum Length*: `128` | getIdempotencyKey(): string | setIdempotencyKey(string idempotencyKey): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateGiftCardActivityRequestBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\GiftCardActivityActivateBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustDecrementBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityAdjustIncrementBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityBlockBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardActivityClearBalanceBuilder;

$createGiftCardActivityRequest = CreateGiftCardActivityRequestBuilder::init(
    GiftCardActivityBuilder::init(
        'location_id0',
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
        )->build(),
    'idempotency_key2'
)->build();
```

