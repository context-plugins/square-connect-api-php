
# Resume Subscription Response

Defines parameters in a
[ResumeSubscription](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/resume-subscription) endpoint
response.

## Structure

`ResumeSubscriptionResponse`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `errors` | [`?(Error[])`](../../doc/models/error.md) | Optional | Information about errors encountered during the request. | getErrors(): ?array | setErrors(?array errors): void |
| `subscription` | [`?Subscription`](../../doc/models/subscription.md) | Optional | Represents a customer subscription to a subscription plan.<br>For an overview of the `Subscription` type, see<br>[Subscription object](https://developer.squareup.com/docs/subscriptions-api/overview#subscription-object-overview). | getSubscription(): ?Subscription | setSubscription(?Subscription subscription): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\ResumeSubscriptionResponseBuilder;
use SquareConnectAPILib\Models\Builders\ErrorBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionBuilder;
use SquareConnectAPILib\Models\Builders\MoneyBuilder;

$resumeSubscriptionResponse = ResumeSubscriptionResponseBuilder::init()
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
            ->chargedThroughDate('charged_through_date0')
            ->createdAt('2020-08-03T21:53:10Z')
            ->customerId('CHFGVKYY8RSV93M5KCYTG4PN0G')
            ->id('9ba40961-995a-4a3d-8c53-048c40cafc13')
            ->locationId('S8GWD5R9QB376')
            ->planId('6JHXF3B2CW3YKHDV4XEM674H')
            ->priceOverrideMoney(
                MoneyBuilder::init()
                    ->amount(2000)
                    ->currency('USD')
                    ->build()
            )
            ->status('ACTIVE')
            ->timezone('America/Los_Angeles')
            ->version(1594311617331)
            ->build()
    )
    ->build();
```

