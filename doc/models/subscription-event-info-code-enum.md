
# Subscription Event Info Code Enum

The possible subscription event info codes.

## Enumeration

`SubscriptionEventInfoCodeEnum`

## Fields

| Name | Description |
|  --- | --- |
| `LOCATION_NOT_ACTIVE` | The location is not active. |
| `LOCATION_CANNOT_ACCEPT_PAYMENT` | The location cannot accept payments. |
| `CUSTOMER_DELETED` | The customer has been deleted. |
| `CUSTOMER_NO_EMAIL` | The customer doesn't have an email. |
| `CUSTOMER_NO_NAME` | The customer doesn't have a name. |

## Example

```php
use SquareConnectAPILib\Models\SubscriptionEventInfoCodeEnum;

$subscriptionEventInfoCode = SubscriptionEventInfoCodeEnum::LOCATION_CANNOT_ACCEPT_PAYMENT;
```

