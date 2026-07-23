
# Search Subscriptions Response

Defines the fields that are included in the response from the
[SearchSubscriptions](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/search-subscriptions) endpoint.

## Structure

`SearchSubscriptionsResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `cursor` | `?string` | Optional | When a response is truncated, it includes a cursor that you can<br>use in a subsequent request to fetch the next set of subscriptions.<br>If empty, this is the final response.<br><br>For more information, see [Pagination](https://developer.squareup.com/docs/working-with-apis/pagination). | getCursor(): ?string | setCursor(?string cursor): void |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `subscriptions` | [`?(Subscription[])`](../../doc/models/subscription.md) | Optional | The search result. | getSubscriptions(): ?array | setSubscriptions(?array subscriptions): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SearchSubscriptionsResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$searchSubscriptionsResponse = SearchSubscriptionsResponseBuilder::init()
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
    ->subscriptions(
        [
            SubscriptionBuilder::init()
                ->canceledDate('2020-04-14')
                ->cardId('ccof:mueUsvgajChmjEbp4GB')
                ->chargedThroughDate('2020-05-14')
                ->createdAt('2020-08-03T21:53:10Z')
                ->customerId('CHFGVKYY8RSV93M5KCYTG4PN0G')
                ->id('de86fc96-8664-474b-af1a-abbe59cacf0e')
                ->locationId('S8GWD5R9QB376')
                ->planId('L3TJVDHVBEQEGQDEZL2JJM7R')
                ->startDate('2020-04-14')
                ->status('CANCELED')
                ->timezone('UTC')
                ->build(),
            SubscriptionBuilder::init()
                ->canceledDate('canceled_date0')
                ->cardId('card_id2')
                ->chargedThroughDate('charged_through_date2')
                ->createdAt('2020-08-03T21:53:10Z')
                ->customerId('CHFGVKYY8RSV93M5KCYTG4PN0G')
                ->id('56214fb2-cc85-47a1-93bc-44f3766bb56f')
                ->locationId('S8GWD5R9QB376')
                ->planId('6JHXF3B2CW3YKHDV4XEM674H')
                ->priceOverrideMoney(
                    MoneyBuilder::init()
                        ->amount(100)
                        ->currency('USD')
                        ->build()
                )
                ->startDate('2020-08-01')
                ->status('PENDING')
                ->taxPercentage('5')
                ->timezone('America/Los_Angeles')
                ->version(1594155459464)
                ->build(),
            SubscriptionBuilder::init()
                ->canceledDate('canceled_date0')
                ->cardId('card_id2')
                ->chargedThroughDate('2020-06-11')
                ->createdAt('2020-08-03T21:53:10Z')
                ->customerId('CHFGVKYY8RSV93M5KCYTG4PN0G')
                ->id('8151fc89-da15-4eb9-a685-1a70883cebfc')
                ->invoiceIds(
                    [
                        'grebK0Q_l8H4fqoMMVvt-Q',
                        'rcX_i3sNmHTGKhI4W2mceA'
                    ]
                )
                ->locationId('S8GWD5R9QB376')
                ->planId('6JHXF3B2CW3YKHDV4XEM674H')
                ->priceOverrideMoney(
                    MoneyBuilder::init()
                        ->amount(1000)
                        ->currency('USD')
                        ->build()
                )
                ->startDate('2020-05-11')
                ->status('ACTIVE')
                ->timezone('America/Los_Angeles')
                ->build()
        ]
    )
    ->build();
```

