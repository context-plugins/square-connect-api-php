
# Subscription Status Enum

Possible subscription status values.

## Enumeration

`SubscriptionStatusEnum`

## Fields

| Name | Description |
|  --- | --- |
| `PENDING` | The subscription starts in the future. |
| `ACTIVE` | The subscription is active. |
| `CANCELED` | The subscription is canceled. |
| `DEACTIVATED` | The subscription is deactivated. |

## Example

```php
use SquareConnectAPILib\Models\SubscriptionStatusEnum;

$subscriptionStatus = SubscriptionStatusEnum::CANCELED;
```

