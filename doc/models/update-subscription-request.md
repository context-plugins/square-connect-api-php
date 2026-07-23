
# Update Subscription Request

Defines parameters in a
[UpdateSubscription](https://developer.squareup.com/reference/square_2021-08-18/subscriptions-api/update-subscription) endpoint
request.

## Structure

`UpdateSubscriptionRequest`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `subscription` | [`?Subscription`](../../doc/models/subscription.md) | Optional | Represents a customer subscription to a subscription plan.<br>For an overview of the `Subscription` type, see<br>[Subscription object](https://developer.squareup.com/docs/subscriptions-api/overview#subscription-object-overview). | getSubscription(): ?Subscription | setSubscription(?Subscription subscription): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\UpdateSubscriptionRequestBuilder;
use SquareConnectAPILib\Models\Builders\SubscriptionBuilder;

$updateSubscriptionRequest = UpdateSubscriptionRequestBuilder::init()
    ->subscription(
        SubscriptionBuilder::init()
            ->canceledDate('canceled_date8')
            ->cardId('card_id0')
            ->chargedThroughDate('charged_through_date0')
            ->createdAt('created_at2')
            ->customerId('customer_id2')
            ->build()
    )
    ->build();
```

