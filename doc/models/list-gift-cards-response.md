
# List Gift Cards Response

A response that contains one or more `GiftCard`. The response might contain a set of `Error`
objects if the request resulted in errors.

## Structure

`ListGiftCardsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | When a response is truncated, it includes a cursor that you can use in a<br>subsequent request to fetch the next set of gift cards. If empty, this is<br>the final response. | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Any errors that occurred during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `giftCards` | [`?(GiftCard[])`](../../doc/models/gift-card.md) | Optional | Gift cards retrieved. | getGiftCards(): ?array | setGiftCards(?array giftCards): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ListGiftCardsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\GiftCardBuilder;
use SquareConnectAPILib\ApiHelper;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$listGiftCardsResponse = ListGiftCardsResponseBuilder::init()
    ->cursor('JbFmyvUpaNKsfC1hoLSA4WlqkgkZXTWeKuStajR5BkP7OE0ETAbeWSi6U6u7sH')
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
    ->giftCards(
        [
            GiftCardBuilder::init(
                ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
            )
                ->balanceMoney(
                    MoneyBuilder::init()
                        ->amount(3900)
                        ->currency('USD')
                        ->build()
                )
                ->createdAt('2021-06-09T22:26:54.000Z')
                ->customerIds(
                    [
                        'customer_ids1',
                        'customer_ids2'
                    ]
                )
                ->gan('7783320008524605')
                ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->id('gftc:00113070ba5745f0b2377c1b9570cb03')
                ->state(ApiHelper::deserialize('"ACTIVE"'))
                ->build(),
            GiftCardBuilder::init(
                ApiHelper::deserialize('{"key1":"val1","key2":"val2"}')
            )
                ->balanceMoney(
                    MoneyBuilder::init()
                        ->amount(2000)
                        ->currency('USD')
                        ->build()
                )
                ->createdAt('2021-05-20T22:26:54.000Z')
                ->customerIds(
                    [
                        'customer_ids1',
                        'customer_ids2'
                    ]
                )
                ->gan('7783320002692465')
                ->ganSource(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
                ->id('gftc:00128a12725b41e58e0de1d20497a9dd')
                ->state(ApiHelper::deserialize('"ACTIVE"'))
                ->build()
        ]
    )
    ->build();
```

