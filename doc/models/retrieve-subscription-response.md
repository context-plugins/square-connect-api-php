
# Retrieve Subscription Response

Defines the fields that are included in the response from the
[RetrieveSubscription](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/retrieve-subscription) endpoint.

## Structure

`RetrieveSubscriptionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `subscription` | [`?Subscription`](../../doc/models/subscription.md) | Optional | Represents a customer subscription to a subscription plan.<br>For an overview of the `Subscription` type, see<br>[Subscription object](https://developer.squareup.com/docs/subscriptions-api/overview#subscription-object-overview). | getSubscription(): ?Subscription | setSubscription(?Subscription subscription): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\RetrieveSubscriptionResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$retrieveSubscriptionResponse = RetrieveSubscriptionResponseBuilder::init()
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
    ->subscription(
        SubscriptionBuilder::init()
            ->canceledDate('canceled_date8')
            ->cardId('card_id0')
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
    )
    ->build();
```

