
# Create Subscription Response

Defines the fields that are included in the response from the
[CreateSubscription](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/create-subscription) endpoint.

## Structure

`CreateSubscriptionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `subscription` | [`?Subscription`](../../doc/models/subscription.md) | Optional | Represents a customer subscription to a subscription plan.<br>For an overview of the `Subscription` type, see<br>[Subscription object](https://developer.squareup.com/docs/subscriptions-api/overview#subscription-object-overview). | getSubscription(): ?Subscription | setSubscription(?Subscription subscription): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CreateSubscriptionResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$createSubscriptionResponse = CreateSubscriptionResponseBuilder::init()
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
            ->cardId('ccof:qy5x8hHGYsgLrp4Q4GB')
            ->chargedThroughDate('charged_through_date0')
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
            ->build()
    )
    ->build();
```

