
# Unlink Customer from Gift Card Response

A response that contains one `GiftCard` that was unlinked. The response might contain a set of `Error`
objects if the request resulted in errors.

## Structure

`UnlinkCustomerFromGiftCardResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `giftCard` | [`?GiftCard`](../../doc/models/gift-card.md) | Optional | Represents a Square gift card. | getGiftCard(): ?GiftCard | setGiftCard(?GiftCard giftCard): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UnlinkCustomerFromGiftCardResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$unlinkCustomerFromGiftCardResponse = UnlinkCustomerFromGiftCardResponseBuilder::init()
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
    ->giftCard(
        GiftCardBuilder::init(
            ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
        )
            ->balanceMoney(
                MoneyBuilder::init()
                    ->amount(2500)
                    ->currency('USD')
                    ->build()
            )
            ->createdAt('2021-03-25T05:13:01Z')
            ->customerIds(
                [
                    'customer_ids1'
                ]
            )
            ->gan('7783320005440920')
            ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->id('gftc:71ea002277a34f8a945e284b04822edb')
            ->state(ApiHelper::deserialize('"ACTIVE"'))
            ->build()
    )
    ->build();
```

