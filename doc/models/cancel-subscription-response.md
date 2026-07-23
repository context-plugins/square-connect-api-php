
# Cancel Subscription Response

Defines fields that are included in a
[CancelSubscription](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/cancel-subscription) response.

## Structure

`CancelSubscriptionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `subscription` | [`?Subscription`](../../doc/models/subscription.md) | Optional | Represents a customer subscription to a subscription plan.<br>For an overview of the `Subscription` type, see<br>[Subscription object](https://developer.squareup.com/docs/subscriptions-api/overview#subscription-object-overview). | getSubscription(): ?Subscription | setSubscription(?Subscription subscription): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\CancelSubscriptionResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionBuilder;

$cancelSubscriptionResponse = CancelSubscriptionResponseBuilder::init()
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
    ->subscription(
        SubscriptionBuilder::init()
            ->canceledDate('2020-05-01')
            ->cardId('ccof:qy5x8hHGYsgLrp4Q4GB')
            ->chargedThroughDate('charged_through_date0')
            ->createdAt('2020-08-03T21:53:10Z')
            ->customerId('CHFGVKYY8RSV93M5KCYTG4PN0G')
            ->id('910afd30-464a-4e00-a8d8-2296eEXAMPLE')
            ->locationId('S8GWD5R9QB376')
            ->planId('6JHXF3B2CW3YKHDV4XEM674H')
            ->startDate('2020-04-24')
            ->status('ACTIVE')
            ->timezone('America/Los_Angeles')
            ->version(1594311617331)
            ->build()
    )
    ->build();
```

