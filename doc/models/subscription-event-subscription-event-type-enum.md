
# Subscription Event Subscription Event Type Enum

The possible subscription event types.

## Enumeration

`SubscriptionEventSubscriptionEventTypeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `START_SUBSCRIPTION` | The subscription started. |
| `PLAN_CHANGE` | The subscription plan changed. |
| `STOP_SUBSCRIPTION` | The subscription stopped. |
| `DEACTIVATE_SUBSCRIPTION` | The subscription deactivated |
| `RESUME_SUBSCRIPTION` | The subscription resumed. |

## Example

```php
use SquareConnectAPILib\Models\SubscriptionEventSubscriptionEventTypeEnum;

$subscriptionEventSubscriptionEventType = SubscriptionEventSubscriptionEventTypeEnum::DEACTIVATE_SUBSCRIPTION;
```

