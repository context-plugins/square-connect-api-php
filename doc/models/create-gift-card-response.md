
# Create Gift Card Response

A response that contains a `GiftCard`. The response might contain a set of `Error` objects if the request
resulted in errors.

## Structure

`CreateGiftCardResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `giftCard` | [`?GiftCard`](../../doc/models/gift-card.md) | Optional | Represents a Square gift card. | getGiftCard(): ?GiftCard | setGiftCard(?GiftCard giftCard): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateGiftCardResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createGiftCardResponse = CreateGiftCardResponseBuilder::init()
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
    ->giftCard(
        GiftCardBuilder::init(
            ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
        )
            ->balanceMoney(
                MoneyBuilder::init()
                    ->amount(0)
                    ->currency('USD')
                    ->build()
            )
            ->createdAt('2021-05-20T22:26:54.000Z')
            ->customerIds(
                [
                    'customer_ids1'
                ]
            )
            ->gan('7783320006753271')
            ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->id('gftc:6cbacbb64cf54e2ca9f573d619038059')
            ->state(ApiHelper::deserialize('"PENDING"'))
            ->build()
    )
    ->build();
```

