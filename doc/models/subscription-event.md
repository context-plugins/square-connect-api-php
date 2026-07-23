
# Subscription Event

Describes changes to subscription and billing states.

## Structure

`SubscriptionEvent`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `effectiveDate` | `string` | Required | The date, in YYYY-MM-DD format (for<br>example, 2013-01-15), when the subscription event went into effect. | getEffectiveDate(): string | setEffectiveDate(string effectiveDate): void |
| `id` | `string` | Required | The ID of the subscription event. | getId(): string | setId(string id): void |
| `info` | `?array` | Optional | - | getInfo(): ?array | setInfo(?array info): void |
| `planId` | `string` | Required | The ID of the subscription plan associated with the subscription. | getPlanId(): string | setPlanId(string planId): void |
| `subscriptionEventType` | `string` | Required | Type of the subscription event. | getSubscriptionEventType(): string | setSubscriptionEventType(string subscriptionEventType): void |

## Example

```php
use SquareConnectAPILib\Models\Builders\SubscriptionEventBuilder;
use SquareConnectAPILib\ApiHelper;

$subscriptionEvent = SubscriptionEventBuilder::init(
    'effective_date4',
    'id6',
    'plan_id8',
    'subscription_event_type6'
)
    ->info(ApiHelper::deserialize('{"key1":"val1","key2":"val2"}'))
    ->build();
```

