
# Business Booking Profile Customer Timezone Choice Enum

Choices of customer-facing time zone used for bookings.

## Enumeration

`BusinessBookingProfileCustomerTimezoneChoiceEnum`

## Fields

| Name | Description |
|  --- | --- |
| `BUSINESS_LOCATION_TIMEZONE` | Use the time zone of the business location for bookings. |
| `CUSTOMER_CHOICE` | Use the customer-chosen time zone for bookings. |

## Example

```php
use SquareConnectAPILib\Models\BusinessBookingProfileCustomerTimezoneChoiceEnum;

$businessBookingProfileCustomerTimezoneChoice = BusinessBookingProfileCustomerTimezoneChoiceEnum::BUSINESS_LOCATION_TIMEZONE;
```

