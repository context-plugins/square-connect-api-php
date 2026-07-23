
# Business Booking Profile Booking Policy Enum

Policies for accepting bookings.

## Enumeration

`BusinessBookingProfileBookingPolicyEnum`

## Fields

| Name | Description |
|  --- | --- |
| `ACCEPT_ALL` | The seller accepts all booking requests automatically. |
| `REQUIRES_ACCEPTANCE` | The seller must accept requests to complete bookings. |

## Example

```php
use SquareConnectAPILib\Models\BusinessBookingProfileBookingPolicyEnum;

$businessBookingProfileBookingPolicy = BusinessBookingProfileBookingPolicyEnum::ACCEPT_ALL;
```

