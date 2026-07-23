
# Retrieve Gift Card Response

A response that contains a `GiftCard`. The response might contain a set of `Error` objects
if the request resulted in errors.

## Structure

`RetrieveGiftCardResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `giftCard` | [`?GiftCard`](../../doc/models/gift-card.md) | Optional | Represents a Square gift card. | getGiftCard(): ?GiftCard | setGiftCard(?GiftCard giftCard): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveGiftCardResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$retrieveGiftCardResponse = RetrieveGiftCardResponseBuilder::init()
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
    ->giftCard(
        GiftCardBuilder::init(
            ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
        )
            ->balanceMoney(
                MoneyBuilder::init()
                    ->amount(1000)
                    ->currency('USD')
                    ->build()
            )
            ->createdAt('2021-05-20T22:26:54.000Z')
            ->customerIds(
                [
                    'customer_ids1'
                ]
            )
            ->gan('7783320001001635')
            ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
            ->id('gftc:00113070ba5745f0b2377c1b9570cb03')
            ->state(ApiHelper::deserialize('"ACTIVE"'))
            ->build()
    )
    ->build();
```

